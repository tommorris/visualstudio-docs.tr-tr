---
title: CPU ve Windows sayaçları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.counters
helpviewer_keywords:
- Windows counters in Profiling Tools
- CPU counters in Profiling Tools
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8166645f9e767b63d22ebf36bb056c16d339131f
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748744"
---
# <a name="cpu-and-windows-counters"></a>CPU ve Windows sayaçları

Visual Studio profil oluşturucu, işletim sistemi (Windows sayaçları) tarafından oluşturulan performans verilerini ve işlemci birimi (CPU sayaçları) tarafından oluşturulan performans verilerini toplamanıza olanak sağlar.

> [!NOTE]
> Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="windows-counters"></a>Windows sayaçları

Windows sayaçlarını işletim sistemi veya uygulama, bir hizmet veya sürücü performansı hakkında bilgi sağlayan Windows Tanılama Altyapısı'nın bir parçasıdır. Windows sayaçlarını geçerli bilgisayar yapılandırmasına göre değişir ve diğer bilgisayarlarda kullanılamayabilir. Windows performans sayaçlarını, görünümler ve raporlar filtrelemek için kullanılabilir işaretleri profil olarak veri dosyalarının profil toplanır.

## <a name="cpu-counters"></a>CPU sayaçları

CPU sayaçları, donanım ile ilgili olayları sayısı depolamak bilgisayarın CPU özelliğidir. İzleme profili oluşturma yöntemi kullanarak CPU sayaç verileri toplama işleminde veri işlevleri ve modülleri için veri eklenir. İzleme metodunu kullanarak birden çok CPU sayaçları toplayabilirsiniz. Örnekleme yöntemi kullandığınızda, örneklenen için olay olarak kullanılacak bir sayaç seçin.

Performans sayaçları CPU özgüdür. Farklı modelleri ve bir CPU sürümleri aynı performans sayacını sağlamak için önemli ölçüde farklı yapılandırma ayarlarını sahip olabilir. [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] Profil Oluşturucu taşınabilir olayları bazı ortak belirli işlemci performans sayaçlarını ayırmanıza ve toplama veya genel performans olaylarını örnek olanak sağlar.

Örneğin, L2 İsabetsiz Önbellek okuma sayısı, profil oluşturucu kullandığınızda, belirli bir olay sayısı istiyorsanız, bu olay gönderen geçici bir performans oturumu oluşturabilirsiniz. L2 önbellek ile herhangi bir CPU üzerinde bunu yapabilirsiniz. Performans oturumunu platformdan platforma değişiklik yapmadan taşınabilir.

Visual Studio profil oluşturucu, belirli olaylar için belirli bir platform desteklemeye devam eder. Örneğin, bir geliştirici Pentium 4 platformunda birlikte NetBurst mimarisi özgü olaylar saymak isteyebilirsiniz. Bu olay belirli bir platformda belirli performans oturumu için taşınabilir ancak geliştirici hala kullanılabilir değil.

## <a name="portable-and-platform-events"></a>Taşınabilir ve platform olaylarını

Bir grup için belirli bir işlemci özgü olmayan CPU sayaçları taşınabilir olaylardır. Diğer tüm CPU sayaçları platform olayları adı verilir ve çeşitli platformlarda desteklenmiyor olabilir.

 Taşınabilir ve platform olaylarını sayaçlarını tanımlanır. *xml* dosyaları, burada sayaçlarıyla ilgili belirli değerler sağlanır. Veri Intel ve AMD CPU'lar, örneğin, farklı olduğundan farklı CPU'lar için birden çok dosya vardır. [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)] Profil oluşturucu için performans ölçüm kullanıcıya uygun sayaçları, taşınabilir ve platform sunmak için bu bilgileri kullanır.

### <a name="portable-events"></a>Taşınabilir olayları

Taşınabilir olayları aşağıdaki olaylar içerir:

**Genel olaylar**

|Olay adı|Olay açıklaması|
|----------------|-----------------------|
|Yönergeler kullanımdan kaldırıldı|Olay tamamlanana kadar yürütülen yönerge sayısını gösterir.|
|Olmayan durdurulan döngüsü|Hangi işlemci, örneğin, g/ç için bekleyen durdurulmaz döngüleri gösterir.|

**Ön uç olayları**

|Olay adı|Olay açıklaması|
|----------------|-----------------------|
|ITLB isabetsizliği|Bir isabetsizliği sonuçlandı yönerge çeviri görünüm edilgen arabellek aramaları sayısını gösterir.|

**Dal olayları**

|Olay adı|Olay açıklaması|
|----------------|-----------------------|
|Dalları devre dışı|Olay tamamlanana kadar yürütülen şube yönerge sayısını gösterir.|
|Yanlış tahmin edilen dalları|Yanlış bir yol işlemci tahmin nedeniyle oluşabilecek yanlış tahmin edilen dalları gösterir. İşlemci tüm çalışmanın atmak ve doğru yola yeniden başlatmak için yanlış tahmin edilen dalları performansını etkiler.|

**Bellek olayları:**

|Olay adı|Olay açıklaması|
|----------------|-----------------------|
|L2 İsabetsiz Önbellek Okuma okuma sayısı|İkinci düzey önbellek sayısı isabetsiz okuma gösterir.|
|L2 Önbellek Okuma başvuruları|Okunan ikinci düzey önbellek sayısı başvuruları gösterir. Yük isabetsiz içerir ve sahipliği (RFO) isabetsiz ve İsabeti için okuyun.|

## <a name="view-available-counters"></a>Kullanılabilir sayaçları görüntüleyin

Bir komut istemi penceresinde üzerinde Visual Studio IDE içinde kullanılabilir CPU sayaçları listeleyebilirsiniz.

### <a name="visual-studio-ui"></a>Visual Studio UI

Visual Studio IDE içinde bir bilgisayarda kullanılabilir sayaçlar listelemek için performans Gezgini profil oluşturucu performans oturumu olması gerekir.

#### <a name="to-view-a-list-of-a-list-of-all-cpu-counters-that-are-supported-on-the-current-platform"></a>Geçerli platformda desteklenen tüm CPU sayaçları listesini listesini görüntülemek için

1. Performans Gezgini performans oturumu sağ tıklatın ve ardından **özellikleri**.

2. Aşağıdakilerden birini yapın:

    -   Tıklatın **örnekleme**ve ardından **performans sayacı** gelen **örnek** olay listesi. CPU sayaçları listelenen **kullanılabilir performans sayaçları**.

         **Not** tıklatın **iptal** önceki örnekleme yapılandırmaya dönmek için.

     veya

    -   Seçin **CPU sayaçları**ve ardından **toplamak CPU sayaçları**. CPU sayaçları listelenen **kullanılabilir sayaçlar**.

         **Not** tıklatın **iptal** önceki sayaç koleksiyonu yapılandırmaya dönmek için.

#### <a name="to-view-a-list-of-a-list-of-window-counters-that-are-supported-on-the-current-platform"></a>Geçerli platformda desteklenen penceresi sayaçlarının listesi listesini görüntülemek için

1. Performans Gezgini performans oturumu sağ tıklatın ve ardından **özellikleri**.

2. Tıklatın **Windows sayaçları**.

3. Seçin **toplamak Windows sayaçları**.

4. Gelen **sayacı kategorisi** listesinde, bir sayaç grubunu seçin. Windows sayaç grubu için liste kutusunda görüntülenir.

     **Not:** tıklatın **iptal** önceki sayaç koleksiyonu yapılandırmaya dönmek için.

### <a name="command-line"></a>Komut satırı

Kullanarak [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı aracını komut satırından bir bilgisayarda kullanılabilir CPU sayaçları listesi.

#### <a name="to-list-of-cpu-counters-that-are-supported-on-the-current-platform"></a>CPU sayaçları bir listesi için geçerli platformda desteklenir

1. Bir komut istemi penceresi açın.

2. Tür

     **\<Visual Studio performans araçları dizin > \VSPerfCmd /querycounters**

     Burada  *\<Visual Studio performans araçları dizin >* Visual Studio yüklemenizin performans araçları dizinine genellikle yoludur

     *C:\Program Files\Microsoft Visual Studio 10.0\Team Araçlar\Performans araçları*

## <a name="see-also"></a>Ayrıca bkz.

[Genel Bakışlar](../profiling/overviews-performance-tools.md)  
[Nasıl yapılır: Örnekleme olayları seçme](../profiling/how-to-choose-sampling-events.md)  
[Nasıl yapılır: CPU sayaç verileri toplama](../profiling/how-to-collect-cpu-counter-data.md)  
[Nasıl yapılır: Windows sayaç verileri toplama](../profiling/how-to-collect-windows-counter-data.md)