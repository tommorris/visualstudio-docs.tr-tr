---
title: "Nasıl yapılır: Düzenleyici dosya türlerini kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - register file types
ms.assetid: 54846779-8290-48de-90ab-81011559d9a5
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 679223f21bd839a8d94b299319ad22c6701bc407
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-register-editor-file-types"></a>Nasıl yapılır: Düzenleyici dosya türlerini kaydetme
Düzenleyici dosya türlerini kaydetmek için kolay bir parçası olarak sağlanan kayıt öznitelikleri kullanarak yoludur [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] yönetilen paket framework (MPF) sınıfları. Yerel paketinizi uyguluyorsanız [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], ayrıca, düzenleyici ve ilişkili uzantıları kaydeden bir kayıt defteri komut dosyası yazabilirsiniz.  
  
## <a name="registration-using-mpf-classes"></a>Kayıt MPF sınıflarını kullanma  
  
#### <a name="to-register-editor-file-types-using-mpf-classes"></a>Düzenleyici dosya türlerini MPF sınıflarını kullanarak kaydetmek için  
  
1.  Sağlamak <xref:Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute> , VSPackage sınıfının düzenleyicinizde için uygun parametrelerle sınıfı.  
  
    ```  
    [Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute(typeof(EditorFactory), ".Sample", 32,   
         ProjectGuid = "{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3}",   
         TemplateDir = "..\\..\\Templates",   
         NameResourceID = 106)]  
    ```  
  
     Burada ". Bu düzenleyici için kayıtlı uzantısı örnek"ve"32"öncelik düzeyini şeklindedir.  
  
     `projectGuid` Tanımlanan çeşitli dosya türleri için GUID'dir <xref:Microsoft.VisualStudio.VSConstants.CLSID_MiscellaneousFilesProject>. Böylece ortaya çıkan dosya derleme işleminin bir parçası olacağını değil, çeşitli dosya türü sağlanır.  
  
     `TemplateDir`Yönetilen temel Düzenleyicisi örneği ile dahil şablon dosyalarını içeren klasörü temsil eder.  
  
     `NameResourceID`BasicEditorUI proje Resources.h dosyasında tanımlanan ve Düzenleyicisi "My Düzenleyicisi" olarak tanımlar.  
  
2.  Geçersiz kılma <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi.  
  
     Uygulamanızda <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi, çağrı <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> yöntemi ve düzenleyici üreteci olarak örneği gösterilen aşağıda geçirin.  
  
    ```  
    protected override void Initialize()  
    {  
        Trace.WriteLine (string.Format(CultureInfo.CurrentCulture,   
        "Entering Initialize() of: {0}", this.ToString()));  
        base.Initialize();  
           //Create Editor Factory  
        editorFactory = new EditorFactory(this);  
        base.RegisterEditorFactory(editorFactory);  
    }  
    ```  
  
     Bu adım, düzenleyici üreteci ve düzenleyici dosya uzantıları kaydeder.  
  
3.  Düzenleyici oluşturucuları kaydını silin.  
  
     VSPackage çıkarıldığından Düzenleyicisi oluşturucuları otomatik kaydı. Düzenleyici Üreteç nesnesi uyguluyorsa <xref:System.IDisposable> arabirimi, kendi `Dispose` Fabrika ile kaydı sonra yöntemi çağrıldığında [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="registration-using-a-registry-script"></a>Kayıt defteri komut dosyası kullanılarak kaydı  
 Yerel Düzenleyicisi oluşturucular ve dosya türlerini kaydetme [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] yapılır tarafından aşağıda gösterildiği gibi windows kayıt defterine yazmak için bir kayıt defteri komut dosyası kullanma.  
  
#### <a name="to-register-editor-file-types-using-a-registry-script"></a>Bir kayıt defteri komut dosyası kullanarak Düzenleyicisi dosya türlerini kaydetmek için  
  
1.  Kayıt defteri kodunuzu Düzenleyici üreteci ve düzenleyici üreteci GUID dize gösterildiği gibi tanımlayın `GUID_BscEditorFactory` aşağıdaki kayıt defteri komut dosyası bölümü. Ayrıca, uzantısı ve Düzenleyicisi uzantısı önceliğini tanımlayın:  
  
    ```  
  
          NoRemove Editors     {         %GUID_BscEditorFactory% = s 'RTF Editor'         {             val Package = s '%CLSID_Package%'             val DisplayName = s 'An RTF Editor'             val ExcludeDefTextEditor = d 1             val AcceptBinaryFiles = d 0  
  
            LogicalViews  
            {  
                val %LOGVIEWID_TextView% = s ''  
            }  
  
            OpenWithEntries  
            {  
            }  
  
            Extensions            {                val rtf = d 50            }  
        }  
    }  
    ```  
  
     Bu örnekte Düzenleyicisi dosya uzantısı ".rtf" tanımlanır ve önceliği "50" olur. GUID dizeleri Resource.h BscEdit örnek proje dosyasında tanımlanır.  
  
2.  VSPackage kaydedin.  
  
3.  Düzenleyici üreteci kaydettirir.  
  
     Düzenleyici üreteci kaydedilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> uygulaması.  
  
    ```  
    // create editor factory.  
    if (m_srpEdFact == NULL)   
    {  
        CComObject<CBscEditorFactory> *pEdFact = new CComObject<CBscEditorFactory>;  
        if (NULL == pEdFact)  
          return E_OUTOFMEMORY;  
  
        if (!pEdFact->FInit(this))  
          return E_UNEXPECTED;  
  
        m_srpEdFact = (IVsEditorFactory *) pEdFact;    // Note: assignment to a smart pointer does an AddRef()  
    }  
    // Query service for IVsRegisterEditors, register the editor factory  
    CComPtr<IVsRegisterEditors> srpRegEd;  
    if ((SUCCEEDED(m_srpPkgSiteSP->QueryService(SID_SVsRegisterEditors, IID_IVsRegisterEditors,(void **)&srpRegEd ))) && (srpRegEd != NULL))  
      {  
        ATLTRACE(TEXT(">> CVsPackage, registering editor factory.\n"));  
          if (FAILED(srpRegEd->RegisterEditor(GUID_BscEditorFactory,  
                      m_srpEdFact, &m_dwEditorCookie)))   
          {  
             ATLTRACE(TEXT(">> CVsPackage, RegisterEditor() failed.\n"));  
            return E_FAIL;  
          }  
      }  
        return S_OK;  
    }  
    ```  
  
     GUID dizeleri Resource.h BscEdit proje dosyasında tanımlanır.