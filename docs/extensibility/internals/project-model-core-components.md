---
title: "Proje modeli çekirdek bileşenleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project models, objects and interfaces
- project models, services
ms.assetid: b2f572d3-b26d-4846-92d1-84055fac141a
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c7759a2394f2cda19f875a85a22c4a674fee8964
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="project-model-core-components"></a>Proje modeli çekirdek bileşenleri
Aşağıdaki tablolarda proje modeline genişletin. Tabloları kısa açıklamaları model ve arabirimleri ve belirli nesneler ile ilişkili hizmetler tanımlanan Hizmetleri ve arabirimleri sunar. Ayrıca, isteğe bağlı olarak proje oluşturma ve Bakım, belirli bir proje türü gereksinimlerine bağlı olarak diğer arabirimleri tabloları ayrıntılarını gösterir.  
  
 Daha fazla bilgi için bkz: [destekleyen simgenin tarama araçları](../../extensibility/internals/supporting-symbol-browsing-tools.md).  
  
### <a name="package-object"></a>Paket nesnesi  
  
|Arabirim|Açıklamalar|  
|---------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>|IDE içinde VSPackage başlatır ve sunduğu hizmetler IDE kullanılabilir hale getirir.|  
  
### <a name="project-factory-object"></a>Proje fabrikası nesnesi  
  
|Arabirim|Açıklamalar|  
|---------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|Yeni proje oluşturma ve mevcut projeleri açma yönetir.|  
  
### <a name="project-objects"></a>Proje nesneleri  
  
|Arabirimler|Açıklamalar|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>|Ekleme ve kaldırma proje öğelerinin yönetir, düzenleyiciler açar ve her belge ad arasında eşleme korur ve `VSITEMID`. Öğesinden devralınan `IVsProject` ve `IVsProject2`.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|Gezinti ve görüntü özelliklerini yönetir ve olayları sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>|Etkinleştirir komut yürütme benzer `IOleCommandTarget` yalnızca odağı Çözüm Gezgini'nde olduğunda geçerli kesme ve yeniden adlandırma gibi komutları için.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Bir proje hiyerarşisi için birincil komut hedefi arabirimi görev yapar. Komut durumu veya durumu ve çalıştırma komutları için nesneleri sorgulamak için standart arabirimidir. Proje penceresinde odaklı olmayan olduğunda kullanılabilir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|Proje durumu kalıcılığı düzenler. Genellikle, proje durumu bir proje dosyası olarak depolanır, ancak dosya tabanlı olmayan depolama sistemlerini uyarlanabilir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2>|Proje öğelerinden, dosyaları diskte veya diğer depolama sistemlerini nesneler olarak ya da kalıcılığı tüm yönlerini yönetmek proje sağlar. `IVsPeristHierarchyItem2` Arabirimini uygulamayan öğeleri için kullanılan <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> arabirimi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|Kaynak kodu denetimi ile etkileşim düzenler.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfgProvider>|Projeleri yapılandırma bilgilerini yönetmenizi sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>|Hata ayıklama/sürüm yapılandırmaları gibi proje yapılandırma nesneleri yönetir. Derleme, dağıtma ve hatalarını ayıklama işlemleri proje yapılandırma nesnelerde Eşgüdümlü.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler>|(Bozucu) delete denetlemek veya hiyerarşi öğeleri için (bozucu olmayan) seçenekleri kaldırmak için hiyerarşileri tarafından uygulanır. Sorgu arabirimi çağırmak `IVsHierarchyDeleteHandler` alanından arabirim `IVsHierarchy` arabirimi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsGetCfgProvider>|Destekleyen nesne sahip olmanın uygulama seçeneği sunar `IVsCfgProvider2` arabirimi uygulayan proje nesnenin daha farklı bir COM kimliğini `IVsHierarchy` arabirimi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectStartupServices>|Projenizi Genişletilebilir olmak için diğer geliştiriciler tarafından uygulanan isteğe bağlı bir arabirim. `IVsProjectStartupServices` Arabirim sağlayan proje dosyanıza kalıcı hale getirmek ve böylece projeniz yükleyen her zaman, üçüncü taraf hizmeti GUID proje dosyasını ve arama halinde yüklediğiniz bir GUID kaydetmek üçüncü taraf VSPackage `QueryService` GUID için.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierWinClipboardHelperEvents>|Kaynak hiyerarşileri tarafından uygulanan bir `UIHierarchy` kesme, kopyalama gibi Pano işlemleri koordine etmek ve yapıştırmak için penceresi. Kullanım `AdviseClipboardHelperEvents` Pano olaylarını kaydetmek için arabirim.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataSource2>|UI hiyerarşi penceresinde bir Sürükle ve bırak işlemi sırasında veri kaynağına göre sürüklenen öğenin hakkında bilgi sağlar. Çağrılır `IVsHierarchy` arabirimi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataTarget>|UI hiyerarşi penceresinde bir Sürükle ve bırak işlemi sırasında sürüklenen öğenin bırakma hedefine göre hakkında bilgi sağlar. Çağrılır `IVsHierarchy` arabirimi.|  
  
### <a name="configuration-object"></a>Yapılandırma nesnesi  
  
|Arabirimler|Açıklamalar|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg>|Bir yapılandırma hakkında bilgi sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2>|Projeleri yapılandırma bilgilerini yönetmenizi sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|Hata ayıklayıcı denetimi altında çalıştırılması için bir proje sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>|Diğer projeler için dağıtım işlemleri dağıtım projeleri tarafından uygulanır.|  
  
### <a name="configuration-builder-object"></a>Yapılandırma Oluşturucu nesnesi  
  
|Arabirimler|Açıklamalar|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>|Bir proje yapılandırmasının oluşturma işlemi yönetir.|  
  
### <a name="additional-project-objects"></a>Ek proje nesneler  
  
|Arabirimler|Açıklamalar|  
|----------------|--------------|  
|`IDispatch`<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages>|Görüntüler öğesi özelliklerinde **özellikleri** penceresi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs>|Dağıtım için çıktı görüntüler.|  
  
 Aşağıdaki tabloda kısa açıklamaları proje modelde tanımlanan hizmetleri sunar.  
  
### <a name="services"></a>Hizmetler  
  
|Hizmet|Açıklamalar|  
|-------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterProjectTypes>|Kullanıcıların proje Fabrika IDE ile var olduğunu kaydetmek için proje türleri uygulayan VSPackages tarafından kullanılır. VSPackage çağırmalısınız `QueryService` bu hizmet ve proje üreteci kaydettirir zaman `IVsPackage::SetSite` yöntemi çağrılır. Varsa `SetSite` yöntemi çağrılmazsa, projenizin örneği değil.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|IDE'nin iç, yerleşik kavramı projeleri listeleme, yeni projeler oluşturun, proje değişiklikleri duyuru gerçekleştirin ve benzeri yeteneği gibi geçerli çözüme erişim sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>|Kaynak denetiminde katılmak istiyor projeler tarafından çağrılır.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>|Bir veya daha fazla proje öğeleri zaten açık olup olmadığını belirlemek için açık belgeleri tablosu tutar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument>|Arabirimleri ve gerçekten standart Düzenleyicisi veya belirli bir düzenleyici kullanarak bir proje öğesi açmak için adlı yöntemler içerir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>|Bunlar eklediğinizde, kaldırmak veya kendi öğeleri yeniden adlandırmanız tüm projeler tarafından çağrılması için gereklidir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx>|Bir dosya veya dizin değişiklikleri yönetir ve seçilen dosyaları diskte değiştirilmiş istemcileri bildirir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>|Öğeleri kirli veya bunları kaydetmek için önce tüm projeleri ve düzenleyiciler tarafından çağrılması için gereklidir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionBuildManager>|Proje yapılandırmaları için derleme ve dağıtım işlemlerini sırasını yönetir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellDebugger>|Çoğu hata ayıklama denetimler için kullanılan alt düzey hata ayıklayıcı hizmetlerine erişim sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>|Geçerli seçimleri hakkında bilgi VSPackages erişmesini sağlar ve ile iletişimi sağlayan **özellikleri** penceresi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|Oluşturma ve aracı veya belge windows numaralandırmak için veya kullanıcıya hata raporlama özelliği gibi temel kullanıcı Arabirimi ile ilgili IDE işlevleri sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar>|IDE'nin durum çubuğu erişim sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibility3>|Otomasyon modeli uygulamak için kullanılır. Proje modelinizde, döndürülecek olanak sağlayan bir özellikler söz konusu nesne örneği oluşturur.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIHierWinClipboardHelper>|Hiyerarşideki proje nesnesinde Pano olayları gerçekleştirmek için kullanılır. `SVsUIHierWinClipboardHelper`doğru tanıtıcı kesme, kopyalama ve yapıştırma işlemlerine olanak sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [Denetim listesi: Yeni proje türleri oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Yapı içinde değil: Proje türü (C++) uygulamak için HierUtil7 proje sınıflarını kullanma](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [Simgenin tarama araçları destekleme](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [Proje modeli öğeleri](../../extensibility/internals/elements-of-a-project-model.md)