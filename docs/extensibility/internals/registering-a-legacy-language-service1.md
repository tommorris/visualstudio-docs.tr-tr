---
title: Eski dil Service1 kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services [managed package framework], registering
ms.assetid: d33b08af-09e0-4c79-87b2-5536b27fbacf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9e12e62e24d6a0a34884c245251a9bf2930f6b0b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135720"
---
# <a name="registering-a-legacy-language-service"></a>Eski dil hizmeti kaydetme
Yönetilen paket framework (MPF)'da, dil hizmeti tarafından VSPackage proffered (bkz [VSPackages](../../extensibility/internals/vspackages.md)) ve kayıtlı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kayıt defteri anahtarları ve girişleri ekleyerek düzenleyin. Bu kayıt işlemi kısmen yükleme sırasında ve çalışma zamanında kısmen içinde yapılır.  
  
## <a name="register-the-language-service-by-using-attributes"></a>Öznitelikleri kullanarak dil hizmet kaydı  
 Aşağıdaki öznitelikler dil hizmeti kaydetmek için kullanılır.  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute>  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideLanguageExtensionAttribute>  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute>  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideLanguageEditorOptionPageAttribute>  
  
 Bu öznitelikler aşağıda açıklanmıştır  
  
### <a name="provideserviceattribute"></a>ProvideServiceAttribute  
 Bu öznitelik dil hizmetiniz bir hizmet olarak kaydeder.  
  
### <a name="example"></a>Örnek  
  
```csharp  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideServiceAttribute(typeof(TestLanguageService),  
                             ServiceName = "Test Language Service")]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
### <a name="providelanguageserviceattribute"></a>ProvideLanguageServiceAttribute  
 Bu öznitelik dil hizmetinizi özellikle dil hizmet olarak kaydeder. Dil hizmetinizi sunar özellikleri belirtin seçenekleri ayarlamanıza olanak sağlar. Örnek bir alt kümesini dil hizmeti sağlayabilir seçeneklerini gösterir. Dil hizmeti seçenekleri tam kümesi için bkz: <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute>.  
  
### <a name="example"></a>Örnek  
  
```csharp  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideLanguageServiceAttribute(typeof(TestLanguageService),  
                             "Test Language",  
                             106,             // resource ID of localized language name  
                             CodeSense = true,             // Supports IntelliSense  
                             RequestStockColors = false,   // Supplies custom colors  
                             EnableCommenting = true,      // Supports commenting out code  
                             EnableAsyncCompletion = true  // Supports background parsing  
                             )]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
### <a name="providelanguageextensionattribute"></a>ProvideLanguageExtensionAttribute  
 Bu öznitelik, bir dosya uzantısına sahip dil hizmetinizi ilişkilendirir. Her uzantıya sahip bir dosya yüklendiğinde, herhangi bir projede dil hizmetinin başlatıldığından ve dosyanın içeriğini görüntülemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  
```csharp  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideLanguageExtensionAttribute(typeof(TestLanguageService),  
                                       ".Testext")]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
### <a name="providelanguagecodeexpansionattribute"></a>ProvideLanguageCodeExpansionAttribute  
 Bu öznitelik, hangi koddan genişletme veya parçacığı şablonları elde edilen bir konuma kaydeder. Bu bilgileri tarafından kullanılan **kod parçacıkları tarayıcı** ve kaynak dosyasına bir kod parçacığı takıldığında Düzenleyicisi tarafından.  
  
### <a name="example"></a>Örnek  
  
```csharp  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideLanguageCodeExpansionAttribute(  
             typeof(TestLanguageService),  
             "Test Language", // Name of language used as registry key.  
             106,           // Resource ID of localized name of language service.  
             "testlanguage",  // language key used in snippet templates.  
             @"%InstallRoot%\Test Language\SnippetsIndex.xml",  // Path to snippets index  
             SearchPaths = @"%InstallRoot%\Test Language\Snippets\%LCID%\Snippets\;" +  
                           @"%TestDocs%\Code Snippets\Test Language\Test Code Snippets"  
             )]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
### <a name="providelanguageeditoroptionpageattribute"></a>ProvideLanguageEditorOptionPageAttribute  
 Bu öznitelik görüntülenmesini özellik sayfası kaydeder **seçenekleri** iletişim kutusunda altında **metin düzenleyici** kategorisi. Bu öznitelikler için her bir sayfa dil hizmetiniz için görüntülenecek kullanın. Sayfalarınıza bir ağaç yapısı içinde düzenlemek gerekiyorsa, her bir ağaç düğümü tanımlamak için ek öznitelikler kullanın.  
  
### <a name="example"></a>Örnek  
 Bu örnek, iki özellik sayfaları, gösterir **seçenekleri** ve **Indenting**ve ikinci özellik sayfası içeren bir düğüm.  
  
```csharp  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideLanguageEditorOptionPageAttribute(  
             "Test Language",  // Registry key name for language  
             "Options",      // Registry key name for property page  
             "#242",         // Localized name of property page  
             OptionPageGuid = "{A2FE74E1-FFFF-3311-4342-123052450768}"  // GUID of property page  
             )]  
    [ProvideLanguageEditorOptionPageAttribute(  
             "Test Language",  // Registry key name for language  
             "Advanced",     // Registry key name for node  
             "#243",         // Localized name of node  
             )]  
    [ProvideLanguageEditorOptionPageAttribute(  
             "Test Language",  // Registry key name for language  
             @"Advanced\Indenting",     // Registry key name for property page  
             "#244",         // Localized name of property page  
             OptionPageGuid = "{A2FE74E2-FFFF-3311-4342-123052450768}"  // GUID of property page  
             )]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
## <a name="proffer-the-language-service-at-runtime"></a>Çalışma zamanında dil hizmeti proffer  
 Dil Paketi yüklendiğinde, söylemelisiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dil hizmetinizi hazırdır. Bunun için hizmet proffering tarafından. Bu yapılır <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi. Ayrıca, arka plan ayrıştırma gerçekleştirilebilir böylece dil hizmetinizi boşta dönemlerde çağırır süreölçer başlatmanız gerekir. Bu boşta Zamanlayıcı ayrıca aracılığıyla uyguladıysanız belge özelliklerini güncelleştirmek için kullanılan <xref:Microsoft.VisualStudio.Package.DocumentProperties> sınıfı. Süreölçer desteklemek için paketinizi uygulamalıdır <xref:Microsoft.VisualStudio.OLE.Interop.IOleComponent> arabirimi (yalnızca <xref:Microsoft.VisualStudio.OLE.Interop.IOleComponent.FDoIdle%2A> yöntemi tam olarak uygulanması gerekiyor; kalan yöntemleri varsayılan değerlerine döndürebilirsiniz).  
  
### <a name="example"></a>Örnek  
 Bu örnek, tipik bir yaklaşım hizmet proffering ve boş bir süreölçer sağladığını gösterir.  
  
```csharp  
  
using System;  
using System.Runtime.InteropServices;  
using System.ComponentModel.Design;  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.OLE.Interop;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    [Microsoft.VisualStudio.Shell.ProvideService(typeof(TestLanguageService))]  
    [Microsoft.VisualStudio.Shell.ProvideLanguageExtension(typeof(TestLanguageService), ".testext")]  
    [Microsoft.VisualStudio.Shell.ProvideLanguageService(typeof(TestLanguageService), "Test Language", 0,  
        AutoOutlining = true,  
        EnableCommenting = true,  
        MatchBraces = true,  
        ShowMatchingBrace = true)]  
    [Guid("00000000-0000-0000-0000-00000000000")] //provide a unique GUID for the package  
  
    public class TestLanguagePackage : Package, IOleComponent  
    {  
        private uint m_componentID;  
  
        protected override void Initialize()  
        {  
            base.Initialize();  // required  
  
            // Proffer the service.  
            IServiceContainer serviceContainer = this as IServiceContainer;  
            TestLanguageService langService      = new TestLanguageService();  
            langService.SetSite(this);  
            serviceContainer.AddService(typeof(TestLanguageService),  
                                        langService,  
                                        true);  
  
            // Register a timer to call our language service during  
            // idle periods.  
            IOleComponentManager mgr = GetService(typeof(SOleComponentManager))  
                                       as IOleComponentManager;  
            if (m_componentID == 0 && mgr != null)  
            {  
                OLECRINFO[] crinfo = new OLECRINFO[1];  
                crinfo[0].cbSize            = (uint)Marshal.SizeOf(typeof(OLECRINFO));  
                crinfo[0].grfcrf            = (uint)_OLECRF.olecrfNeedIdleTime |  
                                              (uint)_OLECRF.olecrfNeedPeriodicIdleTime;  
                crinfo[0].grfcadvf          = (uint)_OLECADVF.olecadvfModal     |  
                                              (uint)_OLECADVF.olecadvfRedrawOff |  
                                              (uint)_OLECADVF.olecadvfWarningsOff;  
                crinfo[0].uIdleTimeInterval = 1000;  
                int hr = mgr.FRegisterComponent(this, crinfo, out m_componentID);  
            }  
        }  
  
        protected override void Dispose(bool disposing)  
        {  
            if (m_componentID != 0)  
            {  
                IOleComponentManager mgr = GetService(typeof(SOleComponentManager))  
                                           as IOleComponentManager;  
                if (mgr != null)  
                {  
                    int hr = mgr.FRevokeComponent(m_componentID);  
                }  
                m_componentID = 0;  
            }  
  
            base.Dispose(disposing);  
        }  
  
        #region IOleComponent Members  
  
        public int FDoIdle(uint grfidlef)  
        {  
            bool bPeriodic = (grfidlef & (uint)_OLEIDLEF.oleidlefPeriodic) != 0;  
            // Use typeof(TestLanguageService) because we need to  
            // reference the GUID for our language service.  
            LanguageService service = GetService(typeof(TestLanguageService))  
                                      as LanguageService;  
            if (service != null)  
            {  
                service.OnIdle(bPeriodic);  
            }  
            return 0;  
        }  
  
        public int FContinueMessageLoop(uint uReason,  
                                        IntPtr pvLoopData,  
                                        MSG[] pMsgPeeked)  
        {  
            return 1;  
        }  
  
        public int FPreTranslateMessage(MSG[] pMsg)  
        {  
            return 0;  
        }  
  
        public int FQueryTerminate(int fPromptUser)  
        {  
            return 1;  
        }  
  
        public int FReserved1(uint dwReserved,  
                              uint message,  
                              IntPtr wParam,  
                              IntPtr lParam)  
        {  
            return 1;  
        }  
  
        public IntPtr HwndGetWindow(uint dwWhich, uint dwReserved)  
        {  
            return IntPtr.Zero;  
        }  
  
        public void OnActivationChange(IOleComponent pic,  
                                       int fSameComponent,  
                                       OLECRINFO[] pcrinfo,  
                                       int fHostIsActivating,  
                                       OLECHOSTINFO[] pchostinfo,  
                                       uint dwReserved)  
        {  
        }  
  
        public void OnAppActivate(int fActive, uint dwOtherThreadID)  
        {  
        }  
  
        public void OnEnterState(uint uStateID, int fEnter)  
        {  
        }  
  
        public void OnLoseActivation()  
        {  
        }  
  
        public void Terminate()  
        {  
        }  
  
        #endregion  
    }  
}   
```