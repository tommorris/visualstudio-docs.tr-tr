---
title: "Proje nesneleri gösterme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project objects, exposing
- extensibility, project objects
ms.assetid: 5bb24967-434a-4ef4-87a0-2f3250c9e22d
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f29ca84669f563da5733c8c07b219d498ccf6ded
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="exposing-project-objects"></a>Proje nesneleri gösterme
Özel proje türleri Otomasyon arabirimleri kullanarak proje erişmesine izin vermek için Otomasyon nesneleri sağlayabilir. Her proje türü standart sağlaması beklenir <xref:EnvDTE.Project> erişilen Otomasyon nesnesi <xref:EnvDTE.Solution>, IDE içinde açık olan tüm projeleri koleksiyonunu içerir. Proje içinde her öğe tarafından sunulan beklenen bir <xref:EnvDTE.ProjectItem> erişilen nesne `Project.ProjectItems`. Bu standart Otomasyon nesneleri ek olarak, projeye özgü Otomasyon nesneleri sunmak projeleri seçebilirsiniz.  
  
 Geç kök DTE nesne kullanımından bağlama erişebileceğiniz özel kök düzeyinde Otomasyon nesneleri oluşturabilirsiniz `DTE.<customeObjectName>` veya `DTE.GetObject("<customObjectName>")`. Örneğin, Visual C++ "DTE kullanarak erişebilirsiniz VCProjects" adlı C++ projesi özgü projesi koleksiyonu oluşturur. VCProjects veya DTE. GetObject("VCProjects"). Ayrıca, en çok türetilen nesne için ProjectItem.Object ve bir ProjectItem.FileCodeModel kullanıma sunan bir ProjectItem sorgulanabilir bir Project.CodeModel proje türü için benzersiz bir Project.Object oluşturabilirsiniz.  
  
 Bir özel, projeye özgü projesi koleksiyonu kullanıma sunmak projeleri için ortak bir kuraldır. Örneğin, [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] sonra kullanarak erişebileceğiniz bir C++ belirli projesi koleksiyonu oluşturur `DTE.VCProjects` veya `DTE.GetObject("VCProjects")`. De oluşturabilirsiniz bir `Project.Object`, proje türü için benzersiz olan bir `Project.CodeModel`, hangi sorgulanan, en çok türetilen nesne için bir `ProjectItem`, hangi çıkarır `ProjectItem.Object`ve bir `ProjectItem.FileCodeModel`.  
  
### <a name="to-contribute-a-vspackage-specific-object-for-a-project"></a>Bir proje için bir VSPackage özgü nesne katkıda bulunma  
  
1.  Uygun anahtarlara, VSPackage .pkgdef dosyasına ekleyin.  
  
     Örneğin, C++ dili projesinin .pkgdef ayarları şunlardır:  
  
    ```  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\Automation]  
    "VCProjects"=""  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\AutomationEvents]  
    "VCProjectEngineEventsObject"=""  
    ```  
  
2.  Koda uygulanması <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> aşağıdaki örnekteki gibi yöntemi.  
  
    ```cpp  
    STDMETHODIMP CVsPackage::GetAutomationObject(  
    /* [in]  */ LPCOLESTR       pszPropName,   
    /* [out] */ IDispatch **    ppIDispatch)  
    {  
    ExpectedPtrRet(pszPropName);  
    ExpectedPtrRet(ppIDispatch);  
    *ppIDispatch = NULL;  
  
        if (m_fZombie)  
            return E_UNEXPECTED;  
  
        if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0)  
        {  
            return GetAutomationProjects(ppIDispatch);  
        }  
        else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0)  
        {  
            return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
        }  
        else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0)  
        {  
            return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
        }  
        return E_INVALIDARG;  
    }   
    ```  
  
     Kodda, `g_wszAutomationProjects` projeniz adıdır. `GetAutomationProjects` Yöntemi uygulayan bir nesne oluşturur `Projects` arabirimi ve döndürür bir `IDispatch` aşağıdaki kod örneğinde gösterildiği gibi çağıran nesne işaretçisi.  
  
    ```cpp  
    HRESULT CVsPackage::GetAutomationProjects(/* [out] */ IDispatch ** ppIDispatch)  
    {  
        ExpectedPtrRet(ppIDispatch);  
        *ppIDispatch = NULL;  
  
        if (!m_srpAutomationProjects)  
        {  
            HRESULT hr = CACProjects::CreateInstance(&m_srpAutomationProjects);  
            IfFailRet(hr);  
            ExpectedExprRet(m_srpAutomationProjects != NULL);  
        }  
        return m_srpAutomationProjects.CopyTo(ppIDispatch);  
    }  
    ```  
  
     Otomasyon nesnesi için benzersiz bir ad seçmeniz gerekir. Ad çakışmaları öngörülemeyen ve birden çok proje türleri aynı adı kullanırsanız rasgele durum çakışan bir nesne adı çakışmaları neden olabilir. Şirket adınızı veya ürün adının Otomasyon nesnesi adına benzersiz bazı yönlerinin içermelidir.  
  
     Özel `Projects` koleksiyon nesnesi proje Otomasyon modelinizi kalan kısmı için bir kolaylık giriş noktasıdır. Proje nesnenizin da erişilebilir <xref:EnvDTE.Solution> projesi koleksiyonu. Tüketicilerine ile ilgili kod ve kayıt defteri girdileri oluşturduktan sonra `Projects` koleksiyonu nesneleri, uygulamanız, standart nesneleri proje modeli için kalan sağlamalıdır. Daha fazla bilgi için bkz: [modelleme projesi](../../extensibility/internals/project-modeling.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>