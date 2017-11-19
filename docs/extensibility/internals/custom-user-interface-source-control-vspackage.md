---
title: "Özel kullanıcı arabirimi (kaynak denetimi VSPackage) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user interface, source control packages
- source control packages, user interface
ms.assetid: f35ddb24-53bf-461e-b34f-7414f657c082
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6138ffcd0c56b87e9e29a316aa2ae0ad9f982e18
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="custom-user-interface-source-control-vspackage"></a>Özel kullanıcı arabirimi (kaynak denetimi VSPackage)
Bir VSPackage Visual Studio komut tablosu (.vsct) dosyası aracılığıyla kendi menü öğelerini ve varsayılan durumlarını bildirir. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Tümleşik geliştirme ortamı (IDE) VSPackage yüklenene kadar bu menü öğelerini varsayılan durumlarını görüntüler. Sonuç olarak, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi etkinleştirmek veya menü öğelerini devre dışı bırakmak için çağrılır.  
  
 Bir VSPackage VSPackage otomatik olarak bir komut kullanıcı arabirimi (UI) bağlamı bağlı olarak yüklenebilmesi için bir kayıt defteri anahtarı ayarlayabilirsiniz, genellikle bir kaynak denetim rağmen VSPackage yalnızca belirli bir kullanıcı Arabirimi bağlamına geçiş yerine isteğe bağlı yüklenecektir. AutoLoadPackages kayıt defteri anahtarı hakkında daha fazla bilgi için bkz: [yönetme VSPackages](../../extensibility/managing-vspackages.md).  
  
## <a name="vspackage-ui"></a>VSPackage kullanıcı Arabirimi  
 Kaynak denetimi paketi VSPackage uygulanır ve tüm kullanıcı Arabiriminden kullanmaz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Her kaynak denetimi VSPackage kendi kullanıcı Arabirimi öğeleri menü öğeleri, menü grupları, aracı windows, araç çubukları ve tüm gerekli UI gibi belirli kaynak denetimi VSPackage ayar seçenekleri için belirtmeniz gerekir. Bu kullanıcı Arabirimi öğeleri statik veya dinamik olarak etkinleştirilebilir. Statik kullanıcı Arabirimi öğeleri .vsct dosyasında tanımlanan ve VSPackage veya yüklü olup olmadığını görüntülenir. Dinamik kullanıcı Arabirimi öğeleri olabilir belirli komut UI bağlam bağlı olarak görünür gibi <xref:EnvDTE.Constants.vsContextNoSolution>, çağrı sonucu olarak veya <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi. Dinamik kullanıcı Arabirimi öğeleri görünürlüğünü VSPackages Gecikmeli yüklenmesini stratejisi karşılar.  
  
## <a name="ui-constraints-on-source-control-vspackages"></a>Kaynak denetimi VSPackages UI kısıtlamaları  
 Bunu yüklendikten sonra kaynak denetimi VSPackage IDE içinden kaldırılamadığından, VSPackage devre dışı bir durum girin kurabilmesi gerekir. Bir VSPackage artık etkin olduğunu bildirimi aldığında VSPackage kullanıcı Arabiriminde devre dışı bırakır ve dış IDE etkileşimi yok sayar. VSPackage'nın uyarlamasını <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> VSPackage etkin değilken, yöntemi komutları gizle.  
  
 Her kaynak denetimi VSPackage uygulanmalı `IVsSccProvider` arabirimi. İki yöntem arabirimde <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A>, VSPackage tarafından uygulanmalıdır.  
  
 VSPackage abone tarafından uygulanan çeşitli IDE olaylarına kaynak denetimi <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>ve benzeri. Ayrıca, VSPackage kayıt defteri etkin geri çağırma arabirimleri gibi uyguladık <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>. Bunlar tüm etkin olmadığında göz ardı edilebilir gerekir.  
  
 Aşağıdaki listede kaynak denetimi VSPackage etkin durumuna göre etkilenen arabirimler gösterilir:  
  
-   Proje belgeleri olayları izler.  
  
-   Çözüm olaylar.  
  
-   Çözüm Kalıcılık arabirimleri. Paketleri .sln ve .suo dosyaları yazamaz, etkin olmadığında.  
  
-   Özellik Extender'larının.  
  
 Gerekli <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, ve ayrıca kaynak denetimi ile ilişkilendirilmiş tüm isteğe bağlı arabirimler çağrılmaz VSPackage kaynak denetimi devre dışı olduğunda.  
  
 Zaman [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE başlar, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komutu UI bağlamı için geçerli varsayılan kaynak denetimi VSPackage kimliği Kimliğini ayarlar Bu, etkin kaynak denetimi VSPackage yüklemeden IDE içinde görünmesi VSPackage statik UI neden olur. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]duraklatır ile kaydetmek VSPackage için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aracılığıyla <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider> önce VSPackage yapılan her çağrı yapar.  
  
 Aşağıdaki tabloda belirli ayrıntılar hakkında nasıl açıklanmaktadır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE farklı kullanıcı Arabirimi öğeleri gizler.  
  
|Kullanıcı Arabirimi öğesi|Açıklama|  
|-------------|-----------------|  
|Menüleri ve araç çubukları|Kaynak denetimi paketi ilk menü ve araç çubuğu görünürlük durumlarını kaynak denetimi paket Kimliğini ayarlamalısınız [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) .vsct dosyasının bölümü. Böylece [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] menü öğelerini durumunu VSPackage yükleniyor ve uygulaması çağırma uygun şekilde ayarlamak için IDE <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi.|  
|Araç pencereleri|Kaynak denetimi VSPackage etkin olmayan yapıldığında sahip herhangi bir aracı windows gizler.|  
|Kaynak denetimi VSPackage özgü sayfaları seçenekleri|Kayıt defteri anahtarı HKLM\SOFTWARE\Microsoft\VisualStudio\X.Y\ToolsOptionsPages\VisibilityCmdUIContexts görüntülenecek kendi seçenekleri sayfalarını gerektiren bağlamları ayarlamak VSPackage olanak sağlar. Bu anahtar altındaki kayıt defteri girdisini kullanarak kimliği (SID) kaynak denetimi hizmeti, hizmet ve DWORD değerini 1 atama oluşturulması gerekir. UI olay VSPackage kayıtlı kaynak denetimi bir bağlamda oluştuğunda etkin olması durumunda VSPackage çağrılır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>   
 <xref:EnvDTE.Constants.vsContextNoSolution>   
 [VSPackages yönetme](../../extensibility/managing-vspackages.md)