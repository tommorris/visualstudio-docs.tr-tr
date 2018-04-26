---
title: Visual Studio Hata Ayıklayıcısı'ndaki ipuçları
description: Üretkenlik ipuçları için Visual Studio hata ayıklayıcısı öğrenin
ms.custom: ''
ms.date: 06/15/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 5262d8b1-2648-429e-85d5-90fcaadfb362
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bb4fb2c32f74a764e092e0e6f65685a358d64f54
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="learn-productivity-tips-and-tricks-for-the-debugger-in-visual-studio"></a>Hata ayıklayıcı Visual Studio için üretkenlik ipuçları ve püf noktaları öğrenin

Visual Studio hata ayıklayıcısı için birkaç üretkenlik ipuçları ve püf noktaları öğrenmek için bu konuyu okuyun. Hata ayıklayıcı temel özelliklerini göz için bkz: [hata ayıklayıcı özelliği Turu](../debugger/debugger-feature-tour.md). Bu konuda, özellik turu dahil edilmeyen bazı alanlar kapsar.

## <a name="pin-data-tips"></a>PIN veri ipuçları

Hata ayıklama sırasında veri İpuçları'ni sık getirirseniz, kendiniz hızlı erişim vermek bir değişken veri ipucu sabitlemek istediğiniz. Değişkeni yeniden başlatıldıktan sonra bile sabitlenmiş kalır. Veri ipucu sabitlemek için üzerine getirildiğinde sırasında sabitleme simgesine tıklayın. Birden çok değişkenleri sabitleyebilirsiniz.

![Bir veri ipucu sabitleme](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

## <a name="edit-your-code-and-continue-debugging-c-vb-c"></a>Kodunuzu Düzenle ve devam hata ayıklama (C#, VB, C++)

Visual Studio tarafından desteklenen çoğu dillerde kodunuzu bir hata ayıklama oturumu ortasında düzenleme ve hata ayıklama devam edebilirsiniz. Bu özelliği kullanmak için imlecinizi hata ayıklayıcı, yapma düzenlemeleri ve tuşuna duraklatıldı sırada kodunuzu tıklayın **F5**, **F10**, veya **F11** hata ayıklama devam etmek için.

![Düzenle ve devam et hata ayıklama](../debugger/media/dbg-tips-edit-and-continue.gif "EditAndContinue")

Özelliğini kullanarak ve özellik kısıtlamaları hakkında daha fazla bilgi için bkz: [Düzenle ve devam et](../debugger/edit-and-continue.md).

## <a name="debug-issues-that-are-hard-to-reproduce"></a>Yeniden zor sorunlar hata ayıklama

Zor ya da zaman alıcı uygulamanızı belirli bir durumda yeniden oluşturmak, koşullu kesme noktası kullanımını yardımcı olup olmadığını değerlendirin. Kullanabileceğiniz [koşullu kesme noktaları](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) ve filtre uygulama (örneğin, bir değişken depolama hatalı veri durumunu) istenilen durumu girene kadar uygulama kodunuza çiğnemekten kaçının için kesme noktaları. İfadeler, filtreleri, isabet sayısına ve benzeri kullanarak koşullar ayarlayabilirsiniz.

#### <a name="to-create-a-conditional-breakpoint"></a>Koşullu kesme noktası oluşturmak için

1. Bir kesme noktası simgesi (kırmızı Top) sağ tıklatın ve seçin **koşullar**.

2. İçinde **kesme noktası ayarları** penceresinde, bir ifade türü.

    ![Koşullu kesme noktası](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

3. Koşul başka türde ilgileniyorsanız seçin **filtre** yerine **koşullu ifade** içinde **kesme noktası ayarları** iletişim kutusunu ve ardından izleyin Filtre ipuçları.

## <a name="change-the-execution-flow"></a>Yürütme akışını değiştirme

Hata ayıklayıcısı ile kod satırında duraklatıldı, sol taraftaki sarı ok işaretçi şablonlarınızdan fareyi kullanın. Kod yürütme yolunda farklı bir noktasına sarı ok işaretçiyi taşıyın. Ardından, F5 veya bir adım komutunu uygulama çalıştırmaya devam etmek için kullanın.

![Yürütme işaretçiyi](../debugger/media/dbg-tour-move-the-execution-pointer.gif "yürütme işaretçiyi taşıyın")

Yürütme akış değiştirerek farklı kod yürütme yollarını test veya hata ayıklayıcı başlatmadan kodu yeniden gibi işlemler yapabilirsiniz.

> [!WARNING]
> Genellikle bu özellikle dikkatli olmanız gerekir ve araç ipucunda bir uyarı görürsünüz. Diğer uyarılar çok görebilirsiniz. İşaretçinin taşınması bir önceki uygulama durumu uygulamanıza geri alınamaz.

## <a name="track-an-out-of-scope-object-c-visual-basic"></a>İzleme kapsamını nesneyi (C#, Visual Basic)

Hata ayıklayıcı windows gibi kullanarak değişkenler görüntülemek kolayca **izleme** penceresi. Ancak, bir değişken gittiğinde kapsam dışında **izleme** penceresinde gri renkte görüntülenir görebilirsiniz. Bazı uygulama senaryolarda bir değişkenin değerini bile zaman kapsamının dışına değişkendir ve yakından izlemek isteyebilirsiniz değiştirebilir (örneğin, bir değişken toplanacak alabilirsiniz). İçinde için bir nesne kimliği oluşturarak değişkeni izleyebilirsiniz **izleme** penceresi.

#### <a name="to-create-an-object-id"></a>Bir nesne kimliği oluşturmak için

1.  İzlemek istediğiniz bir değişken yakın bir kesme noktası ayarlayın.

2.  Hata ayıklayıcıyı başlatma (**F5**) ve kesme geçmeyin.

3. Değişkeni bulunamıyor **Yereller** penceresi (**hata ayıklama > Windows > Yereller**), değişkeni sağ tıklatın ve seçin **olun nesne kimliği**.

    ![Bir nesne kimliği oluşturma](../debugger/media/dbg-tips-watch-create-object-id.png "CreateObjectID")
  
4.  Görmeniz gerekir bir **$** bir süre içinde artı **Yereller** penceresi. Bu değişken nesne kimliğidir.
  
5.  Nesne Kimliği değişkeni sağ tıklatın ve seçin **Gözcü Ekle**.

Daha fazla bilgi için bkz: [bir nesne kimliği oluşturma](../debugger/watch-and-quickwatch-windows.md#bkmk_objectIds).

## <a name="view-return-values-for-functions"></a>İşlev dönüş değerlerini görüntüleme

İşlevlerinizi için dönüş değerlerini görüntülemek için görünür işlevleri bakın **otomobiller** kodunuz atlama sırada penceresi. Bir işlev için dönüş değerini görmek için ilgilendiğiniz işlevi zaten yürüttüğünü emin olun (basın **F10** işlev çağrısı üzerinde şu anda durdurulmuş durumda, bir kez). Pencere kapatıldıktan kullanırsanız **hata ayıklama > Windows > otomobiller** açmak için **otomobiller** penceresi.

![Pencere otomobiller](../debugger/media/dbg-tips-autos-window.png "AutosWindow")

Ayrıca, işlevlerde girebilirsiniz **hemen** dönüş değerlerini görüntülemek için pencere. (Kullanarak açmak **hata ayıklama > Windows > hemen**.)

![Komut penceresi](../debugger/media/dbg-tips-immediate-window.png "ImmediateWindow")

De kullanabilirsiniz [sözde değişkenler](../debugger/pseudovariables.md) içinde **izleme** ve **hemen** penceresinde gibi `$ReturnValue`.

## <a name="string_visualizer"></a>Görselleştirici dizelerde inceleyin.

Dizelerle çalışırken, tüm biçimlendirilmiş dize görüntülemek yararlı olabilir. Düz metin, XML, HTML veya JSON dizesi görüntülemek için büyüteç simgesini tıklatın ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Görselleştirici simgesi") bir dize değeri içeren bir değişken gelerek veya onları oluştu.

![Dize Görselleştirici açmak](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

Dize Görselleştirici bir dize dize türüne bağlı olarak biçimlendirilmiş olup bulmanıza yardımcı olabilir. Örneğin, boş **değeri** alan gösterir dize Görselleştirici türü tarafından tanınmıyor. Daha fazla bilgi için bkz: [dize Görselleştirici iletişim kutusu](../debugger/string-visualizer-dialog-box.md).

![JSON dize Görselleştirici](../debugger/media/dbg-tips-string-visualizer-json.png "JSONStringVisualizer")

Birkaç diğer türleri için hata ayıklayıcı pencerelerde WPF nesneleri gibi görselleştiriciler da açabilirsiniz.

## <a name="break-into-code-on-handled-exceptions"></a>İşlenmiş özel durum kodu içine bölün

Hata ayıklayıcı kodunuzun işlenmeyen özel durumlar üzerinde içine keser. Ancak, özel durumlar ele (içinde oluşan özel durumlar gibi bir `try/catch` blok) de hataların bir kaynak olabilir ve bunlar ortaya çıktığında araştırmak isteyebilirsiniz. Seçeneklerinde yapılandırarak de işlenmiş özel durumlar için koda ayırmak için hata ayıklayıcı yapılandırabilirsiniz **Exception ayarlarını** iletişim kutusu. Seçerek bu iletişim kutusunu açmak **hata ayıklama > Windows > özel ayarları**.

**Exception ayarlarını** iletişim kutusu özel durum kodu içine ayırmak için hata ayıklayıcı bildirmenize olanak tanır. Aşağıdaki çizimde, hata ayıklayıcı kodunuza keser. her bir `System.NullReferenceException` oluşur. Daha fazla bilgi için bkz: [özel durumları yönetme](../debugger/managing-exceptions-with-the-debugger.md).

![Özel durum Ayarları iletişim kutusu](../debugger/media/dbg-tips-exception-settings.png "ExceptionSettingsDialogBox")

## <a name="debug-deadlocks-and-race-conditions"></a>Hata ayıklama Kilitlenmeler ve yarış durumları

Tür birden çok iş parçacıklı uygulamalar için ortak olan sorunları hata ayıklamak gerekiyorsa, genellikle iş parçacığı konumunu hata ayıklama sırasında görüntüleme yardımcı olabilir. Kolayca kullanarak bunu yapabilirsiniz **kaynak iş parçacıkları Göster** düğmesi.

#### <a name="to-show-threads-in-your-source-code"></a>Kaynak kodda iş parçacığı göstermek için

1.  Hata ayıklama sırasında tıklatın **kaynak iş parçacıkları Göster** düğmesini ![kaynak iş parçacıkları Göster](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker") içinde **hata ayıklama** araç.
  
2.  Cilt payını penceresinin sol tarafındaki bakın. Bu satırda gördüğünüz bir *iş parçacığı işaret* simgesi ![iş parçacığı işaret](../debugger/media/dbg-thread-marker.png "ThreadMarker") iki havlu iş parçacığı benzer. İş parçacığı işaret bir iş parçacığı bu konumda durdurulduğunu gösterir.

    Bir iş parçacığı işaret kısmen bir kesme noktası tarafından gizli bilgiler, dikkat edin.
  
3.  İşaretçinin iş parçacığı işaret gelin. Bir DataTip görünür. DataTip her durdurulan iş parçacığı için adı ve iş parçacığı kimliği numarasını belirtir.

    İş parçacıkları konumunu da görüntüleyebilirsiniz [Paralel Yığınlar penceresini](../debugger/get-started-debugging-multithreaded-apps.md).

## <a name="examine-payloads-for-web-services-and-network-resources-uwp"></a>Web hizmetleri ve ağ kaynaklarına (UWP) için yükü inceleyin

UWP uygulamalarında kullanılarak gerçekleştirilen ağ işlemlerinin çözümleyebilirsiniz `Windows.Web.Http` API. Web hizmetleri ve ağ kaynaklarını hata ayıklamaya yardımcı olması için bu aracı kullanabilirsiniz. Aracı kullanmak için **hata ayıklama > Performans Profil Oluşturucu**. Seçin **ağ**ve ardından **Başlat**. Uygulamanızda kullanan senaryosuyla Git `Windows.Web.Http`ve ardından **durdurmak koleksiyonu** raporu oluşturmak için.

![Ağ kullanımı aracı profili oluşturma](../profiling/media/prof-tour-network-usage.png "NetworkUsageProfTool")

Bir işlem Özet görünümünü için daha ayrıntılı olarak seçin.

![Ayrıntılı bilgi ağ kullanımını aracında](../profiling/media/prof-tour-network-usage-details.png "DetailedViewNetworkUsage")

Daha fazla bilgi için bkz: [ağ kullanımını](../profiling/network-usage.md).

## <a name="get-more-familiar-with-how-the-debugger-attaches-to-your-app"></a>Hata Ayıklayıcı'nın, uygulamanızın nasıl ekler daha hakkında bilgi edinin

Çalışan uygulamanıza eklemek için hata ayıklayıcısı hata ayıklama çalıştığınız uygulama tam aynı derleme için oluşturulan simge (.pdb) dosyalarını yükler. Bazı senaryolarda, simge dosyaları biraz bilgisi yararlı olabilir. Visual Studio kullanarak simge dosyaları nasıl yükler inceleyebilirsiniz **modülleri** penceresi.

Açık **modülleri** seçerek hata ayıklama sırasında penceresi **hata ayıklama > Windows > modülleri**. **Modülleri** penceresi öğrenebilirsiniz hata ayıklayıcı kullanıcı kodu olarak davranma hangi modüllerin veya [ *kendi kodumu*](../debugger/just-my-code.md)ve Modül durumu yüklenirken simgesi. Çoğu senaryoda, hata ayıklayıcı kullanıcı kodu için simge dosyaları otomatik olarak bulur ancak adımla (veya hata ayıklama) .NET framework kodu, sistem kodu ya da üçüncü taraf kitaplık kodu istiyorsanız, doğru simge dosyaları almak için ek adımlar gereklidir.

![Sembol bilgilerini modülleri penceresinde görüntülemek](../debugger/media/dbg-tips-modules-window.png "ViewSymbolInformation")

Sembol bilgilerini yükleyebilir **modülleri** sağ tıklayarak ve seçme penceresi **yük simgeleri**.

Bazı durumlarda, uygulama geliştiriciler (ayak izini azaltmak için) eşleşen simge dosyaları, böylece yayımlanmış bir sürüm'e daha sonra debug eşleşen sembolün bir kopyası için derleme dosyalarını tut ancak olmadan uygulamaları birlikte.

Hata ayıklayıcı kodu kullanıcı kodu olarak nasıl sınıflandırır çıkışı bulmak için bkz: [sadece kendi kodumu](../debugger/just-my-code.md). Simge dosyaları hakkında daha fazla bilgi için bkz: [Visual Studio hata ayıklayıcısında simge (.pdb) ve kaynak dosyaları belirtme](specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).

## <a name="learn-more"></a>Daha fazla bilgi edinin

Bu Web günlüğü postaları ek ipuçları ve püf noktaları ve daha ayrıntılı bilgi için bkz:

- [Visual Studio'da hata ayıklama için 7 daha az bilinen girişlerini](https://blogs.msdn.microsoft.com/visualstudio/2017/06/26/7-lesser-known-hacks-for-debugging-in-visual-studio/)
- [Visual Studio'da 7 gizli gems](https://blogs.msdn.microsoft.com/visualstudio/2017/10/05/7-hidden-gems-in-visual-studio-2017/)

## <a name="see-also"></a>Ayrıca Bkz.
[Klavye Kısayolları](../ide/tips-and-tricks-for-visual-studio.md)
