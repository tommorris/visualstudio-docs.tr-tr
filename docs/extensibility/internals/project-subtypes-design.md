---
title: Proje Subtypes tasarım | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project subtypes, design
ms.assetid: 405488bb-1362-40ed-b0f1-04a57fc98c56
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a931d6509b5a8a90f371986f4ddb8955c64387d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133805"
---
# <a name="project-subtypes-design"></a>Proje Subtypes tasarım
Proje subtypes Microsoft Build Engine üzerinde (MSBuild) tabanlı projeleri genişletme VSPackages olanak tanır. Uygulanan yönetilen çekirdek proje sisteminin toplu yeniden toplama kullanımı sağlayan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] henüz hala belirli bir senaryo davranışını özelleştirebilirsiniz.  
  
 Aşağıdaki konular, temel tasarım ve uygulama projesi alt türlerinden birini vermektedir:  
  
-   Proje alt tasarım.  
  
-   Birden çok düzeyli toplama.  
  
-   Arabirimleri destekleme.  
  
## <a name="project-subtype-design"></a>Proje alt tasarım  
 Bir proje alt başlatma ana toplayarak elde edilen <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> nesneleri. Bu geçersiz kılma veya en temel proje özelliklerini geliştirmek bir proje alt olanaklı kılmaktadır. Proje subtypes alma kullanarak özelliklerini işlemek için ilk Fırsat <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, komutları kullanarak <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>ve proje öğesi Yönetimi'ni kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>. Proje subtypes da genişletebilirsiniz:  
  
-   Yapılandırma nesnelerini yansıtın.  
  
-   Yapılandırmaya bağlı nesneleri.  
  
-   Yapılandırma bağımsız Gözat nesneleri.  
  
-   Otomasyon nesneleri yansıtın.  
  
-   Proje Otomasyon özellik koleksiyonları.  
  
 Proje alt türler tarafından genişletilebilirlik hakkında daha fazla bilgi için bkz: [özellikleri ve yöntemleri genişletilmiş proje alt türler tarafından](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md).  
  
##### <a name="policy-files"></a>İlke dosyaları  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Ortamı ilke dosyaları uygulamaya bir proje alt türe sahip temel proje sistemini genişletme bir örnek sağlar. Bir ilke dosyası, şekillendirme verir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Solution Explorer dahil özelliklerini yönetme ortamında **Proje Ekle** iletişim kutusu, **Yeni Öğe Ekle** iletişim kutusu ve  **Özellikler** iletişim kutusu. İlke alt geçersiz kılar ve aracılığıyla bu özellikleri geliştirir <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg>, `IOleCommandTarget` ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> uygulamaları.  
  
##### <a name="aggregation-mechanism"></a>Toplama mekanizması  
 Ortam proje alt toplama mekanizması toplama, böylece daha fazla desteğimize proje flavoring uygulanması Gelişmiş bir alt türü sağlar birden çok düzeyi destekler. Ayrıca, bir projenin destekleyen nesneleri, gibi alt tür <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg>, katmanlama birden çok düzeyi sağlamak amacıyla tasarlanmıştır. COM ve COM kısıtlamaları mantığıyla toplama kuralları, proje subtypes ve temel projeleri işlevinizde iç alt türü veya temel projeyi düzgün yöntem çağrıları için temsilci seçme ve başvuru sayıları yönetme katılacak şekilde etkinleştirmek için programlanmış gerekir . Diğer bir deyişle, yaklaşık toplanacak proje toplama desteklemek için programlanmış gerekir.  
  
 Aşağıdaki çizimde, çok düzeyli proje alt toplama şematik gösterimi gösterir.  
  
 ![Visual Studio çok düzeyli projectflavor grafiği](../../extensibility/internals/media/vs_multilevelprojectflavor.gif "VS_MultilevelProjectFlavor")  
Çok düzeyli proje alt türü  
  
 Üç düzeyi, bir proje alt tarafından toplanan sonra daha gelişmiş proje alt tarafından toplanan temel bir projeyi, çok düzeyli proje alt toplama oluşur. Şekil bir parçası olarak sağlanan destekleyen arabirimleri bazıları odaklanır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] proje alt mimarisi.  
  
##### <a name="deployment-mechanisms"></a>Dağıtım mekanizmaları  
 Çoğu temel proje sistemi arasında dağıtım düzenekleri tarafından proje alt gelişmiş işlevler bulunur. Proje alt yapılandırma arabirimleri uygulayarak dağıtım düzenekleri etkiler (gibi <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>) üzerinde QueryInterface çağırarak alınır <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider>. Burada proje alt ve Gelişmiş proje alt eklemek farklı yapılandırma uygulamaları bir senaryoda, temel projesini çağıran `QueryInterface` Gelişmiş proje alt 's üzerinde `IUnknown`. İç proje alt temel proje için isteyen yapılandırma uygulanması içeriyorsa, iç proje alt tarafından sağlanan uygulama için Gelişmiş proje alt atar. Bir toplama düzeyi bir durumdan diğerine kalıcı hale getirmek için bir mekanizma proje alt düzeyde tüm uygulamanızı <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> XML veri proje dosyalarıyla ilgili derleme dışı kalır. Daha fazla bilgi için bkz: [kalıcı veri MSBuild proje dosyası içinde](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md). <xref:EnvDTE80.IInternalExtenderProvider> Otomasyon Extender'larının proje subtypes almak için bir mekanizma olarak uygulanır.  
  
 Aşağıdaki çizimde temel proje sistemini genişletmek için proje alt türleri tarafından kullanılan Otomasyon genişletici uygulaması, proje yapılandırma Gözat nesnesi özellikle odaklanır.  
  
 ![VS proje niteliği otomatik genişletici grafiği](../../extensibility/internals/media/vs_projectflavorautoextender.gif "VS_ProjectFlavorAutoExtender")  
Proje alt Otomasyon genişletici.  
  
 Proje türlerinde, Otomasyon nesne modeli genişleterek temel proje sistemi daha fazla genişletebilirsiniz. Bunlar DTE Otomasyon nesnesinin bir parçası olarak tanımlanır ve proje nesnesi genişletmek için kullanılan `ProjectItem` nesne ve `Configuration` nesne. Daha fazla bilgi için [temel Project nesne modelini genişletme](../../extensibility/internals/extending-the-object-model-of-the-base-project.md).  
  
## <a name="multi-level-aggregation"></a>Birden çok düzeyli toplama  
 Alt düzey proje alt saran bir proje alt uygulaması işbirliği ile düzgün çalışması iç proje alt izin vermek için programlanmış gerekiyor. Sorumlulukları programlama listesini içerir:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> İç alt kaydırma proje alt uygulaması için temsilci seçme gerekir <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> iç proje alt uyarlamasını her ikisi için de <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Load%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Save%2A> yöntemleri.  
  
-   <xref:EnvDTE80.IInternalExtenderProvider> Uygulama sarmalayıcı proje alt, kendi iç proje alt temsilci gerekir. Özellikle, uygulanması <xref:EnvDTE80.IInternalExtenderProvider.GetExtenderNames%2A> iç proje alt türden adları dizisini almak ve ardından istediği Extender'larının eklenecek dizeyi birleştirmek gerekir.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider> Gerekir uygulama sarmalayıcı proje alt örneği <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg> kendi iç nesne alt proje ve temel projenin proje yapılandırma nesnesini doğrudan, bilir yalnızca özel bir temsilci olarak beri tutun sarmalayıcı Proje alt yapılandırma nesnesi yok. Dış Proje alt başlangıçta istediği doğrudan işlemek için yapılandırma arabirimleri seçin ve rest iç proje alt 's uygulaması için temsilci seçme <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg.get_CfgType%2A>.  
  
## <a name="supporting-interfaces"></a>Arabirimleri destekleme  
 Temel Proje uygulaması çeşitli yönlerini genişletmek için bir proje alt tarafından eklenen arabirimleri desteklemede çağrıları atar. Bu proje yapılandırma ve çeşitli özelliği tarayıcı nesneleri genişletme içerir. Bu arabirimleri çağırarak alınır `QueryInterface` üzerinde `punkOuter` (bir işaretçi `IUnknown`) en dıştaki proje alt Toplayıcısı'nın.  
  
|Arabirim|Proje alt türü|  
|---------------|---------------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg>|Proje alt sağlar:<br /><br /> -Uygulama sağlayın <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>.<br />-Hata ayıklayıcıyı başlatma kendi uygulamasını sağlamak üzere proje alt vererek kontrol <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>.<br />-Tasarım zamanı ifade değerlendirmesi uygun şekilde işleyerek devre dışı `DBGLAUNCH_DesignTimeExprEval` uygulamaya servis talebi <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.QueryDebugLaunch%2A>.|  
|<xref:EnvDTE80.IInternalExtenderProvider>|Proje alt sağlar:<br /><br /> -Genişletmek <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> eklemek veya yapılandırma bağımsız proje özelliklerini kaldırmak için projenin.<br />-Proje Otomasyon nesnesi genişletme (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>) projenin.<br /><br /> Özellik değerlerini yukarıdaki gerçekleştirilecek <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> numaralandırması.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>|Yeniden eşlemek proje alt verir <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> proje yapılandırma Gözat nesnesi verilen nesnesi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBrowseObject>|Yeniden eşlemek proje alt verir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> veya `VSITEMID` proje yapılandırma Gözat nesnesi verilen nesnesi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment>|Proje dosyası (.vbproj veya .csproj) için rasgele yapılandırılmış XML verilerini kalıcı hale getirmek proje alt sağlar. Bu veriler için MSBuild görünür değil.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>|Proje alt sağlar:<br /><br /> -Kalıcı olmasını yeni MSBuild özellikleri ekleyin.<br />-Gereksiz özellikleri MSBuild kaldırın.<br />-Sorgu için bir MSBuild özelliğinin geçerli değeri.<br />-Bir MSBuild özelliğinin geçerli değeri değiştirin.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>