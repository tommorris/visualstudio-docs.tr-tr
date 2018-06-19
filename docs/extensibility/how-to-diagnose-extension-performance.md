---
title: 'Nasıl yapılır: uzantı performans tanılama | Microsoft Docs'
ms.custom: ''
ms.date: 11/08/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 46b0a1e3-7e69-47c9-9d8d-a1815d6c3896
author: BertanAygun
ms.author: bertaygu
manager: douge
ms.workload:
- bertaygu
ms.openlocfilehash: 60a7d1c3178d0fd74983d3f1096d01e578a49a00
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133286"
---
# <a name="measuring-extension-impact-in-startup"></a>Başlangıç uzantısı etkileri ölçme

## <a name="focus-on-extension-performance-in-visual-studio-2017"></a>Visual Studio 2017 uzantısı performans odaklanmak

Müşteri geri bildirimi doğrultusunda, Visual Studio 2017 yayımı için odak alanlarına birini başlatma ve çözüm yük performans olmuştur. Visual Studio platform ekip olarak biz başlatma ve çözüm yükleme performansını genel iyileştirme üzerinde çalıştığınız sırada bizim telemetri yüklü uzantıları Ayrıca bu senaryoları hakkında önemli bir etkisi olabilir önerir.

Kullanıcıların bu etkiyi anlamasına yardımcı olmak için yeni bir özellik yavaş uzantıların kullanıcıları bilgilendirmek için Visual Studio'da eklediğimiz. Visual Studio çözümü yükleme veya başlatma aşağı yavaşlamasının yeni bir uzantı algıladığında, kullanıcıların yeni "Visual Studio performans Yönet" iletişim kutusuna işaret IDE içinde bir bildirim görürsünüz. Bu iletişim kutusunu ayrıca her zaman daha önce algılanan uzantıları göz atmak için Yardım menüsünden tarafından erişilebilir.

![Visual Studio performansı yönetme](media/manage-performance.png)

Uzantı etkisi nasıl hesaplanır ve nasıl yerel olarak uzantı uzantısı etkileyen bir performans gösterilebilir olmadığını sınamak için analiz edilmeden açıklayarak uzantısı geliştiricilere yardımcı olmak için bu belgenin amaçlar.

> [!NOTE]
> Bu belge başlatma ve çözüm yük uzantılarını etkisini odaklanır. UI yanıt vermemesine neden olursa uzantıları da Visual Studio performansını etkiler. Bu konu hakkında daha fazla bilgi için bkz: [nasıl yapılır: uzantıları tarafından kaynaklanan tanılamak UI gecikmeler](how-to-diagnose-ui-delays-caused-by-extensions.md).

## <a name="how-extensions-can-impact-startup"></a>Uzantıları başlangıç nasıl etkileyebileceğini

Başlangıç performansı etkileyen uzantıları için en yaygın yolları otomatik yük NoSolutionExists veya ShellInitialized gibi bilinen Başlangıç UI bağlamları birini seçerek biridir. Bu UI bağlamları başlatma sırasında etkinleştirilen ve bu içeriklerden kendi tanımıyla "ProvideAutoLoad" özniteliği dahil herhangi bir paket yüklendi ve o anda başlatıldı.

Biz uzantı etkisini ölçüyor, biz öncelikle otomatik yük yukarıdaki bağlamlarda tercih bu uzantıları tarafından harcanan süre odaklanır. Ölçülen süreleri dahil ancak bunlarla sınırlı değildir:

* Zaman uyumlu paketler için uzantı derlemeleri yükleme
* Paket sınıfı oluşturucuda zaman uyumlu paketler için harcanan süre
* Paket başlatma (veya SetSite) yönteminde zaman uyumlu paketler için harcanan süre
* Zaman uyumsuz paketler için yukarıdaki işlemleri arka plan iş parçacığında çalıştırmak ve bu nedenle izlemeden hariç tutulur
* Paket başlatma sırasında ana iş parçacığı üzerinde çalışmak üzere zamanlanmış herhangi bir zaman uyumsuz iş harcanan süre
* Olay işleyicileri, özellikle başlatılan Kabuk bağlam etkinleştirme veya kabuk henüz kaldırılmamış durumu değişikliği için harcanan süre
* Visual Studio 2017 güncelleştirme 3 ' başlayarak, biz de Kabuk başlatılmadan önce boşta çağrılarını harcadığı zamanı izleme başlayacak. Boşta işleyicileri uzun işlemlerinde ayrıca yanıt vermeyen IDE neden ve kullanıcı tarafından algılanan başlangıç zamanını katkıda bulunun.

Otomatik yükleme paketleri gereksinimini kaldırılmasına yardımcı, kullanıcıların bu uzantıyı kullanan veya yüklenirken bir uzantı etkisini azaltmak belirli daha olduğu daha özel durumları için kendi yük ertelemek için Visual Studio 2015 başlayarak birden çok özellik ekledik. otomatik olarak.

Aşağıdaki belgelerde bu özellikler hakkında daha fazla ayrıntı bulabilirsiniz:

[Kural kullanıcı Arabirimi bağlamları temel](how-to-use-rule-based-ui-context-for-visual-studio-extensions.md): kullanıcı Arabirimi bağlamları yerleşik daha zengin bir kurala dayalı altyapısı proje türleri, özellikleri ve yetenekleri dayalı özel bağlamları oluşturmanıza izin. Bu özel bağlamları başlangıç yerine belirli bir özellikle projeyle varlığını gibi daha belirli senaryoları sırasında bir paketi yüklemek için kullanılabilir; izin vermeyi veya [komutu için özel bir bağlam bağlanması için görünürlük](visibilityconstraints-element.md) bir komut durumu Sorgu işleyici kaydetmek için proje özellikleri veya böylece gereksinimini bir paketi yüklemek için kullanılabilir başka koşullar göre.

[Zaman uyumsuz paket Destek](how-to-use-asyncpackage-to-load-vspackages-in-the-background.md): paket yükleme otomatik yük öznitelik veya bir zaman uyumsuz hizmet sorgu tarafından istenmişse zaman uyumsuz olarak arka planda yüklenmesi için Visual Studio paketler Visual Studio 2015'te yeni AsyncPackage temel sınıf sağlar . Bu arka planda yükleme IDE uzantısı arka planda başlatılır ve kritik senaryolarda başlatma ve çözüm yük gibi etkilenen olmayacaktır yanıt verebilir durumda kalmasını sağlar.

[Zaman uyumsuz Hizmetleri](how-to-provide-an-asynchronous-visual-studio-service.md): zaman uyumsuz paket desteğiyle de Hizmetleri zaman uyumsuz olarak sorgulanıyor ve zaman uyumsuz Hizmetleri kaydettirebilir destek eklediğimiz. Çekirdek Visual Studio Hizmetleri zaman uyumsuz sorgu iş çoğunluğu arka plan iş parçacıkları oluşur zaman uyumsuz sorgu destekleyecek şekilde dönüştürme daha da önemlisi çalışıyoruz. SComponentModel (Visual Studio MEF ana bilgisayarı) şimdi tamamen zaman uyumsuz yüklenirken desteklemek uzantılarına izin vermek için zaman uyumsuz sorgu destekleyen ana Hizmetleri biridir.

## <a name="reducing-impact-of-auto-loaded-extensions"></a>Yüklenen uzantıları otomatik etkisini azaltma

Bir paket hala başlangıçta yüklenen otomatik olması gerekiyorsa, başlangıç etkileyen uzantısı olasılığını azaltmak için paket başlatma sırasında çalışmanın en aza indirmek önemlidir.

Paket başlatma masraflı olmaya neden olabilecek bazı örnekler şunlardır:

### <a name="use-of-synchronous-package-load-instead-of-asynchronous-package-load"></a>Zaman uyumsuz paket yük yerine zaman uyumlu paket yükleme kullanımı

Zaman uyumlu paketler ana iş parçacığı üzerinde varsayılan olarak yüklenen olduğundan, zaman uyumsuz paket temel sınıf daha önce belirtildiği gibi kullanmanız yüklenen otomatik paketleriniz varsa uzantısı sahipleri öneririz. Zaman uyumsuz yüklemesini desteklemek için bir otomatik yüklenen paket değiştirme de bunu aşağıdaki diğer sorunları çözmek kolaylaştırır.

### <a name="synchronous-filenetwork-io-requests"></a>Zaman uyumlu dosya/ağ g/ç isteği

İdeal olarak etkilerini makine durumuna bağlıdır ve bazı durumlarda uzun süreler için engelleyebilirsiniz eşzamanlı dosya veya ağ g/ç istek ana iş parçacığına da kaçınılmalıdır.

Zaman uyumsuz paketi yükleme ve zaman uyumsuz g/ç API'lerini kullanarak paket başlatma ana iş parçacığı bu gibi durumlarda engellemez ve kullanıcılar g/ç istekleri arka planda gerçekleşir ancak Visual Studio ile etkileşim kurmaya devam edebilir olmanız gerekir.

### <a name="early-initialization-of-services-components"></a>Hizmetleri, bileşenleri, erken başlatma

Paket başlatma ortak yaklaşımlar tarafından kullanılan ya da bu paketin paket Oluşturucusu veya Initialize yöntemi tarafından sağlanan hizmetleri başlatmak için biridir. Bu hizmetleri kullanılmaya hazır sağlar, ancak bu hizmetlerin hemen kullanılmasa yükleme paketini gereksiz maliyeti de ekleyebilirsiniz. Bunun yerine paket başlatma çalışmanın en aza indirmek için isteğe bağlı bu tür hizmetlerinin başlatılması.

Bir paket tarafından sağlanan küresel hizmetler için yalnızca bir bileşen tarafından istendiğinde gevşek hizmeti başlatmak için bir işlev alır AddService yöntemlerini kullanabilirsiniz. Paket içinde kullanılan hizmetler için Lazy kullanabilir<T> veya AsyncLazy<T> Hizmetleri başlatılmadı/sorgulanan ilk kullanımda olduğundan emin olmak için.

## <a name="measuring-impact-of-auto-loaded-extensions-using-activity-log"></a>Etkinlik günlüğü kullanarak uzantıları otomatik etkisini ölçmek yüklendi

Visual Studio 2017 güncelleştirme 3'den itibaren Visual Studio etkinlik günlüğü şimdi paketleri performans etkisini girişlerinde başlatma ve çözüm yüklenmesi sırasında içerir. Bu ölçümler görmek için/log anahtarı ile Visual Studio'yu başlatın ve ActivityLog.xml dosyasını açın gerekiyor.

Etkinlik günlüğünde Girişleri "Visual Studio performansı yönetme" kaynağı altında olur ve aşağıdaki gibi görünür:

```Component: 3cd7f5bf-6662-4ff0-ade8-97b5ff12f39c, Inclusive Cost: 2008.9381, Exclusive Cost: 2008.9381, Top Level Inclusive Cost: 2008.9381```

Bu, pakette "Visual Studio 2008 ms başlangıç olarak harcanan GUID 3cd7f5bf-6662-4ff0-ade8-97b5ff12f39c ile" anlamına gelir. Visual Studio savigs kullanıcı olduğu gibi bir paket etkisini hesaplanırken birincil sayı olarak üst düzey maliyet dikkate nota bakın bunlar uzantısı, pakette için devre dışı bıraktığınızda.

## <a name="measuring-impact-of-auto-loaded-extensions-using-perfview"></a>Otomatik etkisini ölçmek uzantılarını PerfView kullanarak yüklendi

Kod çözümleme paket başlatma yavaşlatabilir kod yollarını belirlemenize yardımcı olabilecek olsa da, Visual Studio başlangıç paketi yük etkisini anlamak için PerfView gibi uygulamaları kullanarak izleme de kullanabilir.

PerfView etkin bir uygulama ya da CPU kullanımı veya sistem çağrıları engelleme nedeniyle yollarında anlamanıza yardımcı olacak bir sistem geniş izleme aracıdır. Aşağıda PerfView adresinde kullanarak bir örnek uzantısı çözümleme üzerinde bir örnek şudur [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=28567).

**Kod örneği:**

Bu örnek örneği temel alarak göstermek için tasarlanmış aşağıdaki kodu durumda bazı gecikme nedenler:

```csharp
protected override void Initialize()
{
    // Initialize a class from another assembly as an example
    MakeVsSlowServiceImpl service = new MakeVsSlowServiceImpl();

    // Costly work in main thread involving file IO
    string systemPath = Environment.GetFolderPath(Environment.SpecialFolder.Windows);
    foreach (string file in Directory.GetFiles(systemPath))
    {
        DateTime creationDate = File.GetCreationTime(file);
    }

    // Costly work after shell is initialized. This callback executes on main thread
    KnownUIContexts.ShellInitializedContext.WhenActivated(() =>
    {
        DoMoreWork();
    });

    // Start async work on background thread
    DoAsyncWork().Forget();
}

private async Task DoAsyncWork()
{
    // Switch to background thread to do expensive work
    await TaskScheduler.Default;
    System.Threading.Thread.Sleep(500);
}

private void DoMoreWork()
{
    // Costly work
    System.Threading.Thread.Sleep(500);
    // Blocking call to an asynchronous work.
    ThreadHelper.JoinableTaskFactory.Run(async () => { await DoAsyncWork(); });
}
```

**Bir izleme PerfView ile kaydetme:**

Yüklü uzantınız ile Visual Studio ortamınızın Kurulumu sonra PerfView açarak ve toplama iletişim "Topla" menüsünden açmak başlangıç izlemesi kaydedebilirsiniz.

![perfview toplama menüsü](media/perfview-collect-menu.png)

Çağrı yığınları CPU tüketimi için varsayılan seçenekleri sağlar ancak biz de engelleme sürede ilgi olduğundan, "Saat iş parçacığı" yığınları da etkinleştirmeniz gerekir. Ayarları hazır olduğunuzda "Üzerinde koleksiyonunu Başlat"'i tıklatın ve kaydı başladıktan sonra Visual Studio'yu başlatın.

Koleksiyon durdurmadan önce Visual Studio tam olarak başlatılmadan, ana pencereyi tamamen görünür olduğundan ve otomatik olarak göster herhangi UI parçalarını uzantınız varsa, bunlar ayrıca görünür olduğundan emin olmak istersiniz. Visual Studio tamamen yüklenmeden ve uzantınızı başlatıldı sonra izleme çözümlemek için kaydı durdurabilirsiniz.

**Bir izleme PerfView ile çözümleme:**

Kayıt tamamlandıktan sonra PerfView otomatik olarak izleme açın ve Seçenekleri'ni genişletin.

Bu örneğin amaçları doğrultusunda, biz çoğunlukla "Gelişmiş grubunun" altında bulabilirsiniz "İş parçacığı zaman yığınları" görünümünde ilgilendiğiniz. Bu görünüm, CPU süresi ve disk g/ç veya işleyicilerinin bekleyen gibi engellenen zaman dahil olmak üzere bir yöntem tarafından bir iş parçacığı üzerinde harcanan toplam süreyi gösterir.

 ![iş parçacığı zaman yığınları](media/perfview-thread-time-stacks.png)

 "Zaman Yığınlar İş parçacığı" görünümü açılırken analiz başlatmak için "devenv" işlem seçmeniz gerekir.

İş parçacığı zaman yığınları daha ayrıntılı bir analiz için kendi Yardım menüsünü altında okumak nasıl hakkında yönergeler PerfView açıklanmıştır. Bu örneğin amaçları doğrultusunda, yalnızca yığınları bizim paketleri modül adı ve başlangıç iş parçacığı ile ekleyerek bu görünümü daha fazla filtrelemek istiyoruz.

1. Varsayılan olarak eklenen herhangi bir gruplama kaldırmak için boş metin için "GroupPats" ayarlayın.
2. ", Derleme adı kısmını içerecek şekilde IncPats" ve başlangıç iş parçacığı kümesi yanı sıra mevcut işlem Filtresi. Bu durumda, "devenv; olmalıdır Başlangıç iş parçacığı; MakeVsSlowExtension".

Şimdi görünümü yalnızca uzantısı ilgili derlemeler ile ilişkilendirilmiş maliyetini gösterir. Bu görünümde, başlangıç iş parçacığı "Inc" (her ikisi de dahil maliyet) sütunu altında listelenen her zaman bizim filtrelenmiş uzantısı ilgili ve başlangıç etkileyen.

Bazı ilginç çağrısı Yukarıdaki örnek için yığınları olacaktır:

1. System.IO sınıfını kullanarak g/ç: Bu çerçeveleri dahil maliyetini izlemeye, çok pahalı olmayabilir olsa da, dosya g/ç hızı makine başka bir makine değişir bu yana bir sorunun olası bir nedeni oldukları.

  ![Sistem GÇ çerçeveler](media/perfview-system-io-frames.png)

2. Diğer zaman uyumsuz iş üzerinde bekleyen çağrılar engelleme: dahil süre bu durumda ana iş parçacığı engellenmiş zaman uyumsuz iş tamamlanma zamanı temsil eder.

  ![engelleme çağrısı çerçeveler](media/perfview-blocking-call-frames.png)

Bir etkisini belirlemek yararlı olacak izleme görünümlerinde biri "Görüntü yük yığınları" olacaktır. "İş parçacığı zaman yığınları" görünüme uygulanan gibi aynı filtre uygulamak ve otomatik yüklenen paketiniz tarafından yürütülen kod nedeniyle yüklenen tüm derlemelere öğrenin.

Her ek derlemeyi başlangıç yavaş makinelerde önemli ölçüde yavaşlatabilir ek disk I/O gerektireceğini gibi bir paket başlatma yordam içinde yüklenen derlemeler sayısını en aza indirmek önemlidir.

## <a name="summary"></a>Özet

Visual Studio Başlangıç biz sürekli geri bildirim alma üzerinde alanları biri olmuştur. Bileşenleri ve yükledikleri uzantıları bakılmaksızın deneyimi tutarlı bir başlangıç tüm kullanıcılar için daha önce belirtildiği gibi Amacımız olduğunu ve bu hedefe ulaşmak yardımcı olmak için uzantı sahipleriyle birlikte çalışmaya isteriz. Yukarıdaki yönergelere başlangıç uzantıları etkisini anlama ve ya da yük otomatik olarak veya zaman uyumsuz olarak kullanıcı üretkenliği üzerindeki etkiyi en aza indirmek için yüklemek için gereken önleme yardımcı olmalıdır.
