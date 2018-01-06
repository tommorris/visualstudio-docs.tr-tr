---
title: "Visual Studio SDK olayları gösterme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Visual Studio], exposing
- automation [Visual Studio SDK], exposing events
ms.assetid: 70bbc258-c221-44f8-b0d7-94087d83b8fe
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 74a9ff54d14b6212d0fc484acd2bd25fad18bb87
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-events-in-the-visual-studio-sdk"></a>Visual Studio SDK olayları gösterme
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]sağlar Otomasyon kullanarak olayları kaynağı. Proje ve proje öğeleri için olayları kaynak öneririz.  
  
 Olaylar, Otomasyon tüketici tarafından alınır <xref:EnvDTE.DTEClass.Events%2A> nesne veya <xref:EnvDTE.DTEClass.GetObject%2A> ("EventObjectName"). Ortam çağrıları `IDispatch::Invoke` kullanarak `DISPATCH_METHOD` veya `DISPATCH_PROPERTYGET` bir olay döndürmek için bayrak.  
  
 Aşağıdaki işlem VSPackage özgü olaylar nasıl döndürülen açıklanmaktadır.  
  
1.  Ortam başlatır.  
  
2.  Tüm VSPackages Otomasyon, AutomationEvents ve AutomationProperties anahtarların altındaki tüm değer adları kayıt defterinden okur ve bu adlardan bir tabloda depolanır.  
  
3.  Bu örnekte, bir Otomasyon tüketici çağırır `DTE.Events.AutomationProjectsEvents` veya `DTE.Events.AutomationProjectItemsEvents`.  
  
4.  Ortam dize parametresi tabloda bulur ve karşılık gelen VSPackage yükler.  
  
5.  Ortam çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> adı kullanarak yöntemine geçirilen çağrısında; Bu örnekte, AutomationProjectsEvents veya AutomationProjectItemsEvents.  
  
6.  VSPackage yöntemleri gibi olan bir kök nesnesi oluşturur `get_AutomationProjectsEvents` ve `get_AutomationProjectItemEvents` ve ardından bir IDispatch işaretçisi nesneyi döndürür.  
  
7.  Ortam Otomasyon çağrısına iletilen adına göre uygun yöntemi çağırır.  
  
8.  `get_` Yöntemi her ikisi de uygulayan başka bir olay IDispatch tabanlı nesnesi oluşturur `IConnectionPointContainer` arabirimi ve `IConnectionPoint` arabirim ve bir IDispatchpointer nesneyi döndürür.  
  
 Otomasyon kullanarak bir olay kullanıma sunmak için yanıt gerekir <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> ve kayıt defterine ekleyin dizeleri izleme. Temel Proje örnekte, "BscProjectsEvents" ve "BscProjectItemsEvents" dizelerdir.  
  
## <a name="registry-entries-from-the-basic-project-sample"></a>Temel Proje örnek kayıt defteri girişleri  
 Bu bölümde nereye kayıt defterine Otomasyon olay değerleri ekleneceğini gösterir.  
  
 [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Packages\\< PkgGUID\>\AutomationEvents]  
  
 "AutomationProjectEvents nesnesi döndürür AutomationProjectEvents"=""  
  
 "AutomationProjectItemsEvents nesnesi döndürür AutomationProjectItemEvents"=""  
  
|Ad|Tür|Aralık|Açıklama|  
|----------|----------|-----------|-----------------|  
|Varsayılan (@)|REG_SZ|Kullanılmıyor|Kullanılmayan. Veri alanı için belgeleri kullanabilirsiniz.|  
|AutomationProjectsEvents|REG_SZ|Olay nesnesinin adı.|Yalnızca anahtar adı büyük/küçük harf geçerlidir. Veri alanı için belgeleri kullanabilirsiniz.<br /><br /> Bu örnek temel proje örnekten gelir.|  
|AutomationProjectItemEvents|REG_SZ|Olay nesnenin adı|Yalnızca anahtar adı büyük/küçük harf geçerlidir. Veri alanı için belgeleri kullanabilirsiniz.<br /><br /> Bu örnek temel proje örnekten gelir.|  
  
 Olay nesnelerden herhangi birini bir Otomasyon tüketici tarafından istendiğinde, VSPackage destekleyen herhangi bir olay için yöntemleri sahip bir kök nesnesi oluşturun. Ortam uygun çağırır `get_` bu nesne üzerinde yöntemi. Örneğin, varsa `DTE.Events.AutomationProjectsEvents` olarak adlandırılır, `get_AutomationProjectsEvents` kök nesnesi üzerinde yöntemi çağrılır.  
  
 ![Visual Studio Proje olayları](../../extensibility/internals/media/projectevents.gif "ProjectEvents")  
Olaylar için otomasyon modeli  
  
 Sınıf `CProjectEventsContainer` BscProjectsEvents için kaynak nesnesi temsil ederken `CProjectItemsEventsContainer` kaynak nesnesi için BscProjectItemsEvents temsil eder.  
  
 Çoğu durumda, çoğu olay nesneleri filtre nesnesi çünkü her olay istek için yeni bir nesne döndürmesi gerekir. Olay tetiklendiğinde olay işleyicisi çağrılmakta olduğunu doğrulamak için bu filtre denetleyin.  
  
 AutomationEvents.h ve AutomationEvents.cpp bildirimleri ve aşağıdaki tabloda sınıfların uygulamaları içerir.  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|`CAutomationEvents`|Kaynağından alınan bir olay kök nesnesi uygulayan `DTE.Events` nesnesi.|  
|`CProjectsEventsContainer`ve`CProjectItemsEventsContainer`|İlgili olaylar yangın olay kaynağı nesneleri uygulayın.|  
  
 Aşağıdaki kod örneği, bir olay nesnesi için bir istek için yanıt gösterilmektedir.  
  
```cpp  
STDMETHODIMP CVsPackage::GetAutomationObject(  
    /* [in]  */ LPCOLESTR       pszPropName,   
    /* [out] */ IDispatch **    ppIDispatch)  
{  
    ExpectedPtrRet(ppIDispatch);  
    *ppIDispatch = NULL;  
  
    if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0)   
        //Is the requested name our Projects object?  
    {  
        return GetAutomationProjects(ppIDispatch);  
        // Gets our Projects object.  
    }  
    else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0)  
        //Is the requested name our ProjectsEvents object?  
    {  
        return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
          // Gets our ProjectEvents object.  
    }  
    else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0)  //Is the requested name our ProjectsItemsEvents object?  
    {  
        return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
          // Gets our ProjectItemsEvents object.  
    }  
    return E_INVALIDARG;  
}  
```  
  
 Yukarıdaki kod `g_wszAutomationProjects` projeniz işareti ("FigProjects"), adı `g_wszAutomationProjectsEvents` ("FigProjectsEvents") ve `g_wszAutomationProjectItemsEvents` ("FigProjectItemEvents") proje olayların adları ve proje öğelerini alanından kaynaklanan olayları, VSPackage uygulaması.  
  
 Olay nesneleri aynı merkezi konumdan alınır `DTE.Events` nesnesi. Böylece son kullanıcı, belirli bir olay bulmak için tüm nesne modelini Gözat gerekmez. Bu şekilde tüm olay nesneleri birlikte gruplandırılır. Bu ayrıca, sistem genelinde olayları için kendi kodunuzu uygulamak gerektirmek yerine, belirli VSPackage nesneleri sağlamanıza olanak tanır. Ancak, son kullanıcı için kimin gerekir bulmak için bir olay, `ProjectItem` arabirimi, bu olay nesnesi burada alınır hemen NET olmadığı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>   
 [VSSDK örnekleri](http://aka.ms/vs2015sdksamples)