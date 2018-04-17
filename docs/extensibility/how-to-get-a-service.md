---
title: 'Nasıl yapılır: bir hizmet alma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, consuming
ms.assetid: 1f000020-8fb7-4e39-8e1e-2e38c7fec3d4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cdf5bd925a034a64d8605c675704a0e894308ea3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-get-a-service"></a>Nasıl yapılır: bir hizmeti Al
Genellikle, farklı özelliklere erişmek için Visual Studio Hizmetleri edinmeniz gerekir. Genel olarak, Visual Studio hizmet kullanabileceğiniz bir veya daha fazla arabirimleri sağlar. Çoğu Hizmetleri VSPackage elde edebilirsiniz.  
  
 Türetilen VSPackage <xref:Microsoft.VisualStudio.Shell.Package> ve, doğru tarihli için herhangi bir genel hizmeti sorabilirsiniz. Paket sınıfı uyguladığından <xref:System.IServiceProvider>, paketinden türetilen VSPackage ayrıca bir hizmet sağlayıcısı'dır.  
  
 Visual Studio yüklediğinde bir <xref:Microsoft.VisualStudio.Shell.Package>, bunu geçirir bir <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> nesnesine <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> başlatma sırasında yöntemi. Bu adlı *siting* VSPackage. Paket sınıfı bu hizmet sağlayıcı sarmalar ve sağlayan <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> Hizmetleri alma yöntemi.  
  
## <a name="getting-a-service-from-an-initialized-vspackage"></a>Başlatılmış bir VSPackage bir hizmet alma  
  
1.  Visual Studio uzantılarının uzantısı varlıklar yer alacağı VSIX dağıtım projesi ile başlar. Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adlı VSIX proje `GetServiceExtension`. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# > genişletilebilirlik**.  
  
2.  Şimdi adlı bir özel komut öğesi şablonu Ekle **GetServiceCommand**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# > genişletilebilirlik** seçip **özel komut**. İçinde **adı** alan penceresinin alt kısmında, komut dosyası adı Değiştir **GetServiceCommand.cs**. Özel bir komut oluşturma hakkında daha fazla bilgi için [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
3.  GetServiceCommand.cs, MenuItemCommand yönteminin gövdesi kaldırın ve aşağıdaki kodu ekleyin:  
  
    ```csharp  
    IVsActivityLog activityLog = ServiceProvider.GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (activityLog == null) return;  
    System.Windows.Forms.MessageBox.Show("Found the activity log service.");  
  
    ```  
  
     Bu kod bir SVsActivityLog hizmetini alır ve kendisine bıraktığı bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> etkinlik günlüğü yazmak için kullanılan arabirim. Bir örnek için bkz: [nasıl yapılır: etkinlik günlüğü kullanın](../extensibility/how-to-use-the-activity-log.md).  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
5.  Deneysel örneği Araçlar menüsünde Bul **çağırma GetServiceCommand** düğmesi. Bu düğmeye tıkladığınızda, bildiren bir ileti kutusu görmeniz gerekir **etkinlik günlüğü hizmeti bulunamadı.**  
  
## <a name="getting-a-service-from-a-tool-window-or-control-container"></a>Bir hizmeti bir aracı penceresi veya denetim kapsayıcısından alma  
 Bazen bir aracı penceresinden get bir hizmet ya da değil tarihli, aksi takdirde, istediğiniz hizmeti hakkında bilmez bir hizmet sağlayıcısı ile tarihli kapsayıcı denetimi gerekebilir. Örneğin, bir denetim içindeki etkinlik günlüğünden yazmak isteyebilirsiniz.  
  
 Statik <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> yöntemi kullanır herhangi VSPackage türetilen ilk kez başlatılan bir önbelleğe alınan hizmet sağlayıcısı <xref:Microsoft.VisualStudio.Shell.Package> tarihli.  
  
 VSPackage tarihli önce VSPackage Oluşturucusu çağrıldığı için küresel hizmetler içinde VSPackage Oluşturucusu genellikle gelen kullanılamaz. Bkz: [nasıl yapılır: sorun giderme Hizmetleri](../extensibility/how-to-troubleshoot-services.md) geçici bir çözüm için.  
  
 Bir hizmet bir araç penceresi veya diğer VSPackage olmayan öğe yolu bir örneği burada verilmiştir.  
  
```csharp  
IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;  
if (log == null) return;  
```  
  
## <a name="getting-a-service-from-the-dte-object"></a>Bir hizmet DTE nesnesinden alma  
 Ayrıca Hizmetleri'nden alabilir <xref:EnvDTE.DTEClass> nesnesi. Ancak, bir VSPackage veya statik çağırarak bir hizmet olarak DTE nesnesini almalısınız <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> yöntemi.  
  
 DTE nesne uygulayan <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>, kullanabileceğiniz kullanarak bir hizmet için Sorgulanacak <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A>.  
  
 Bir hizmet DTE nesnesinden alın bırakılır.  
  
```csharp  
// Start with the DTE object, for example:   
// using EnvDTE;  
// DTE dte = (DTE)GetService(typeof(DTE));  
  
ServiceProvider sp = new ServiceProvider((Microsoft.VisualStudio.OLE.Interop.IServiceProvider)dte);  
if (sp != null)  
{  
    IVsActivityLog log = sp.GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log != null)  
    {   
        System.Windows.Forms.MessageBox.Show("Found the activity log service.");  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir hizmet sağlar](../extensibility/how-to-provide-a-service.md)   
 [Kullanarak ve hizmetleri sağlar](../extensibility/using-and-providing-services.md)   
 [Hizmet Temel Bileşenleri](../extensibility/internals/service-essentials.md)