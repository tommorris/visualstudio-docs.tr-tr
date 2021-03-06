---
title: Özel kullanıcı arabirimi (kaynak denetimi VSPackage'ı) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user interface, source control packages
- source control packages, user interface
ms.assetid: f35ddb24-53bf-461e-b34f-7414f657c082
caps.latest.revision: 29
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9e544408f4cea3e9ec4e388ab76f4224abd7aa69
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630677"
---
# <a name="custom-user-interface-source-control-vspackage"></a>Özel Kullanıcı Arabirimi (Kaynak Denetimi VSPackage’ı)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [özel kullanıcı arabirimi (kaynak denetimi VSPackage'ı)](https://docs.microsoft.com/visualstudio/extensibility/internals/custom-user-interface-source-control-vspackage).  
  
VSPackage Visual Studio komut tablosu (.vsct) dosyası, menü öğelerini ve varsayılan durumlarına bildirir. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tümleşik geliştirme ortamı (IDE) VSPackage yüklenene kadar bu menü öğeleri varsayılan durumlarını görüntüler. Sonuç olarak, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> etkinleştirmek ya da menü öğelerini devre dışı yöntemi çağrılır.  
  
 VSPackage VSPackage bağlı olarak bir komut kullanıcı arabirimi (UI) bağlamı otomatik olarak yüklenebilmesi için kayıt defteri anahtarını ayarlayabilirsiniz, ancak genellikle bir kaynak denetimi VSPackage'ı yalnızca belirli bir kullanıcı Arabirimi bağlamına geçiş yerine isteğe bağlı yüklenecektir. AutoLoadPackages kayıt defteri anahtarı hakkında daha fazla bilgi için bkz. [yönetme VSPackages](../../extensibility/managing-vspackages.md).  
  
## <a name="vspackage-ui"></a>VSPackage kullanıcı Arabirimi  
 Paket kaynak denetimi VSPackage uygulanır ve herhangi bir UI kullanmaz [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Her kaynak denetimi VSPackage'ı seçenekler belirli kaynak denetimi VSPackage'ı ayarlamak için menü öğeleri, menü grupları, araç pencerelerini, araç çubukları ve gerekli herhangi bir UI gibi kendi kullanıcı Arabirimi öğeleri belirtmeniz gerekir. Bu kullanıcı Arabirimi öğeleri, statik veya dinamik olarak etkinleştirilebilir. Statik kullanıcı Arabirimi öğeleri .vsct dosyasında tanımlanan ve VSPackage'ı veya yüklü olup olmadığını görüntülenir. Dinamik kullanıcı Arabirimi öğeleri olabilir görünür bir komuta UI bağlama bağlı olarak gibi <xref:EnvDTE.Constants.vsContextNoSolution>, veya yapılan bir çağrının sonucu olarak <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi. Dinamik kullanıcı Arabirimi öğeleri görünürlüğünü VSPackages Gecikmeli yüklemeyi stratejisini ile uyumludur.  
  
## <a name="ui-constraints-on-source-control-vspackages"></a>Kaynak denetimi VSPackage'larını kısıtlamalar kullanıcı Arabirimi  
 Yüklendikten sonra IDE'den kaynak denetimi VSPackage'ı kaldırılamaz çünkü VSPackage etkin olmayan bir duruma girmeniz mümkün olması gerekir. VSPackage artık etkin olduğunu bildirimi aldığında, VSPackage kullanıcı arabirimini devre dışı bırakır ve dış IDE etkileşimi yok sayar. VSPackage'nın uygulaması <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi VSPackage etkin değilken komutları gizle.  
  
 Her kaynak denetimi VSPackage'ı uygulanmalı `IVsSccProvider` arabirimi. İki yöntem arabirimde <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A>, VSPackage'ı tarafından uygulanmalıdır.  
  
 Kaynak denetimi VSPackage'ı abone olduğunuz tarafından uygulanan çeşitli IDE olaylarına <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>ve benzeri. Ayrıca, VSPackage kayıt defteri etkin geri çağırma arabirimleri olarak uygulanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>. Bu tüm etkin olmadığında yoksayılmalıdır.  
  
 Aşağıdaki listede, bir kaynak denetimi VSPackage'ı etkin durumunu tarafından etkilenen arabirimler gösterilir:  
  
-   Proje belgelerini olayları izleyin.  
  
-   Çözüm olayları.  
  
-   Çözüm Kalıcılık arabirimleri. Paketleri .sln ve .suo dosyalara yazamazlar, etkin olmadığında.  
  
-   Özellik Genişleticileri.  
  
 Gerekli <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, ve ayrıca kaynak denetimiyle ilişkili herhangi bir isteğe bağlı arabirimi değil çağrılır kaynak denetimi VSPackage'ı devre dışı olduğunda.  
  
 Zaman [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE başlatıldığında [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] komut UI bağlamı için geçerli varsayılan kaynak denetimi VSPackage'ı kimliği Kimliğini ayarlar Bu, statik UI etkin kaynak denetimi VSPackage'ı yüklemeden IDE'de görünmesini VSPackage'ı neden olur. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSPackage'ı kaydetmek için duraklatır [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] aracılığıyla <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider> önce VSPackage yapılan her çağrı yapar.  
  
 Aşağıdaki tabloda belirli ayrıntıları hakkında nasıl açıklar [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE farklı kullanıcı Arabirimi öğeleri gizler.  
  
|Kullanıcı Arabirimi öğesi|Açıklama|  
|-------------|-----------------|  
|Menüleri ve araç çubukları|Kaynak Denetim paketi kaynak denetimi paket Kimliğini ilk menü ve araç çubuğu görünürlük durumlarını ayarlamalısınız [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) .vsct dosyası bölümünü. Böylece [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSPackage'ı yükleme ve uygulaması çağırma menü öğelerinin durumunu uygun şekilde ayarlamak için IDE <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi.|  
|Araç pencereleri|Kaynak denetimi VSPackage'ı devre dışı yapıldığında sahip olduğu tüm araç pencereleri gizler.|  
|Kaynak denetimi VSPackage'ı özgü seçenekler sayfaları|Kayıt defteri anahtarı HKLM\SOFTWARE\Microsoft\VisualStudio\X.Y\ToolsOptionsPages\VisibilityCmdUIContexts görüntülenecek seçenekler sayfalarını gerektiren bağlamları ayarlamak VSPackage olanak tanır. Bu anahtar altındaki bir kayıt defteri girişi, hizmet kimliği (SID), kaynak denetimi hizmetini kullanarak ve DWORD değerini 1 atama oluşturulması gerekir. Her bir kullanıcı Arabirimi olay kaynak denetimi VSPackage'ı ile kayıtlı bir bağlamda gerçekleştiğinde VSPackage etkin olursa çağrılır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>   
 <xref:EnvDTE.Constants.vsContextNoSolution>   
 [VSPackage’ları Yönetme](../../extensibility/managing-vspackages.md)

