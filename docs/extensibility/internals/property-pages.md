---
title: "Özellik sayfaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration options, changing properties
- property pages
- property pages, changing configuration options
ms.assetid: b9b3e6e8-1e30-4c89-9862-330265dcf38c
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 484d53315f836117b69270a2f43b6b780733b9f7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="property-pages"></a>Özellik Sayfaları
Kullanıcıları görüntülemek ve özellik sayfalarını kullanarak proje yapılandırmaya bağlı ve - bağımsız özelliklerini değiştirin. A **özellik sayfaları** düğmesi etkinleşir **özellikleri** penceresi veya bir özellik sayfası görünümü seçili nesnenin sağlamak nesneleri için Çözüm Gezgini araç. Özellik sayfaları ortamı tarafından oluşturulan ve çözümler ve projeler için kullanılabilir. Ancak, aynı zamanda olabilirler olun proje öğeleri yapılandırmaya bağlı özelliklerini kullanmak için kullanılabilir. Projedeki dosyaları düzgün bir şekilde oluşturmak farklı derleyici anahtar ayarları gerektirdiğinde bu özellik kullanılabilir.  
  
## <a name="using-property-pages"></a>Özellik sayfalarını kullanma  
 Özellik sayfası zaten görüntüleniyor ve seçim (örneğin, bir proje çözüme) değişiklikleri, bilgi sayfaları yeni seçim özelliklerini görüntülemek için görüntülenen değişir. Özellik sayfaları destekleyen hiçbir nesne üzerindeki özellikleri olduğunda özellik sayfası boş olur.  
  
 Birden çok nesne seçtiyseniz, tüm seçili öğe için özellikler kesişimi özellik sayfasını görüntüler. Seçili öğeyi yapılandırmaya bağlı özellikleri içermiyorsa ve **özellik sayfaları** Çözüm Gezgini araç çubuğundaki düğmesine tıklandığında, odak için Özellikler penceresini değiştirir. Özellikler penceresi ve seçim işlemeyle ilgili daha fazla bilgi için bkz: [genişletme özellikleri](../../extensibility/internals/extending-properties.md).  
  
 Birden fazla nesne özellikleri görüntülenir ve bir değeri özellik sayfasında değiştirmek, tüm nesneler için değerleri başlangıçta farklı ve tek nesnenin özellikleri görüntülendiğinde sayfası boş olsa bile yeni değere ayarlanır.  
  
 İki genel tür vardır **ProjectProperty sayfaları** iletişim kutuları bulunan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Visual Basic projeleri için ilk Örneğin, özellik sayfaları bir alan biçimi kullanarak aşağıdaki ekran görüntüsünde gösterildiği gibi görüntülenir. İkinci, daha sonra bu bölümde, özellik sayfası ana bilgisayar özellikleri ızgara Özellikler penceresinde bulunan benzer gösterilir.  
  
 ![Visual Basic özellik sayfaları](../../extensibility/internals/media/vsvbproppages.gif "vsVBPropPages")  
Alan biçimi ve ağaç yapısı proje özellik sayfaları iletişim kutusu  
  
 Özellik sayfaları iletişim kutusu ağaç yapısında kullanarak yerleşik olmayan <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>. Ortam tarafından kendisine geçirilen düzeyi adı temel <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage> arabirimleri, onu oluşturur.  
  
 Yalnızca iki üst düzey kategori kullanılabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] özellik sayfaları:  
  
-   Ortak özellikler, seçili nesnenin veya nesnelerin bağımsız yapılandırma bilgilerini görüntüler. Ortak özellikleri alt kategorileri biri seçildiğinde, sonuç olarak, iletişim kutusunun üstündeki yapılandırma, Platform ve Configuration Manager seçenekler kullanılamaz.  
  
-   Yapılandırma özellikleri, proje ve çözüm için hata ayıklama, en iyi duruma getirme ve yapı parametreleri ilgili yapılandırma bağımlı bilgileri içerir.  
  
 Herhangi bir ek en üst düzey kategori oluşturamaz, ancak birini veya diğerini uygulamanızda görüntülememek seçtiğiniz `IVsPropertyPage`. Örneğin, bir nesne için görüntülenecek herhangi bir yapılandırma bağımsız özelliği yok, ortak özellikleri kategori görüntülememek seçebilirsiniz. Ortak özellikleri görüntülemek `ISpecifyPropertyPages` uyguladığınızda öğesi'nin gözatma nesnesini ve yapılandırma özelliklerini uygulanır `ISpecifyPropertyPages` yapılandırma nesnesindeki (nesne uygulama `IVsCfg`, `IVsProjectCfg`ve ilgili arabirimler).  
  
 Bir üst düzey kategori altında görüntülenen her kategori ayrı özellik sayfasını temsil eder. Kategori ve alt kategori girişleri kullanılabilir iletişim kutusunda, uygulamanız tarafından belirlenir `ISpecifyPropertyPages` ve `IVsPropertyPage`.  
  
 `IDispatch`özellik sayfaları uygulama üzerinde görüntülenecek özellikleri olan seçimi kapsayıcı öğeleri için nesnelerini `ISpecifyPropertyPages` sınıfı kimliklerinin listesini numaralandıramıyor. Sınıf kimlikleri için değişkenleri olarak geçirilir `ISpecifyPropertyPages` ve özellik sayfaları örneği oluşturmak için kullanılır. Sınıf kimlikleri listesini de geçirilir `IVsPropertyPage` iletişim kutusunun soldaki ağaç yapısı oluşturmak için. Özellik sayfaları sonra geçişi bilgi geri `IDispatch` uygulayan nesne `ISpecifyPropertyPages` ve her bir sayfa için bilgi doldurur.  
  
 Gözat nesnesinin özelliklerini kullanarak alınır `IDispatch` seçimi kapsayıcıdaki her nesne için.  
  
 Uygulama `Help::DisplayTopicFromF1Keyword` , VSPackage için Yardım düğmesini işlevsellik sağlar.  
  
 Daha fazla bilgi için bkz: `IDispatch` ve `ISpecifyPropertyPages`MSDN Kitaplığı'nda.  
  
 Özellik sayfaları ikinci türü örnekleri ana bilgisayarları aşağıdaki ekran görüntüsünde gösterildiği gibi bir form özellikleri kılavuzunun görüntülenir.  
  
 ![VC verilir sayfaları](../../extensibility/internals/media/vsvcproppages.gif "vsVCPropPages")  
Özellik sayfaları iletişim kutusu özellikler Kılavuzu  
  
 Arabirimler `IVSMDPropertyBrowser` ve `IVSMDPropertyGrid` (vsmanaged.h içinde bildirilen) oluşturmak ve özellikleri ızgara bir iletişim kutusu veya penceresi içinde doldurmak için kullanılır.  
  
 Projeleri mimarisini önceki sürümlerinden önemli ölçüde değişti [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Özellikle, hangi proje kavramı etkindir değişti. İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], etkin bir proje kavramı yoktur. Önceki geliştirme ortamlarında, yapı ve komutları dağıtan proje bağlam bağımsız olarak varsayılan etkin proje oluştu. Şimdi, çözüm denetler ve hangi derleme ve komutları dağıtma istemlerde hangi projeler için geçerlidir.  
  
 Daha önce etkin bir proje neydi artık üç farklı yollardan biriyle yakalanır.  
  
-   Başlangıç projesi  
  
     Bir proje veya kullanıcı F5 tuşuna bastığında ya da çalışma derle menüsünde seçer, başlatılacak çözümün özellik sayfasından projeleri belirtebilirsiniz. Bu, eski etkin proje adının kalın yazı tipiyle Çözüm Gezgini'nde görüntülenen algılama ile benzer bir şekilde çalışır.  
  
     Çağırarak otomasyon modeli özelliği olarak başlangıç projesi alabilir `DTE.Solution.SolutionBuild.StartupProjects`. Bir VSPackage içinde çağırırsınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> yöntemleri. `IVsSolutionBuildManager`bir hizmet olarak kullanılabilir `QueryService` SID_SVsSolutionBuildManager üzerinde. Daha fazla bilgi için bkz: [proje yapılandırma nesnesi](../../extensibility/internals/project-configuration-object.md) ve [çözüm yapılandırması](../../extensibility/internals/solution-configuration.md).  
  
-   Etkin çözüm yapı yapılandırması  
  
     [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]uygulayarak Otomasyon modelinde kullanılabilir bir etkin çözüm yapılandırmasına sahip `DTE.Solution.SolutionBuild.ActiveConfiguration`. (Her proje birden çok yapılandırmaları, farklı adlara sahip birden çok platformdaki olabilir) çözümüne için her bir proje yapılandırması içeren bir koleksiyon bir çözüm yapılandırmadır. Çözümün özellik sayfaları ile ilgili daha fazla bilgi için bkz: [çözüm yapılandırması](../../extensibility/internals/solution-configuration.md).  
  
-   Şu anda seçili proje  
  
     Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> proje hiyerarşisi ve proje öğesi veya seçili öğeleri alma yöntemi. DTE, kullanacağınız `SelectedItems.SelectedItem.Project` ve `SelectedItems.SelectedItem.ProjectItem` yöntemleri. Örnek kodu temel bu başlıklar altında [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] belgeleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage>   
 [Yapılandırma seçenekleri yönetme](../../extensibility/internals/managing-configuration-options.md)   
 [Proje yapılandırma nesnesi](../../extensibility/internals/project-configuration-object.md)   
 [Çözüm Yapılandırması](../../extensibility/internals/solution-configuration.md)