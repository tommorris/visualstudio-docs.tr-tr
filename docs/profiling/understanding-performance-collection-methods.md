---
title: Performans koleksiyon yöntemleri anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.wizard.methodpage
helpviewer_keywords:
- Profiling Tools, profiling methods
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a6312a674cc3e9764971f2add59c8e1f0441790
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34477489"
---
# <a name="understand-performance-collection-methods"></a>Performans koleksiyon yöntemleri anlama

Profil oluşturma Visual Studio Araçları performans verilerini toplamak için kullanabileceğiniz beş yöntemleri sağlar. Bu konuda farklı yöntemleri açıklar ve belirli bir yöntem ile veri toplama uygun olabilir bazı senaryolar önerir.

> [!NOTE]
> Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

|Yöntem|Açıklama|
|------------|-----------------|
|[Örnekleme](#sampling)|Bir uygulama tarafından gerçekleştirilen iş hakkında istatistiksel veriler toplar.|
|[İzleme](#instrumentation)|Zamanlama hakkında ayrıntılı bilgiler toplar her işlev çağrısı.|
|[Eşzamanlılık](#concurrency)|Çok iş parçacıklı uygulamalar hakkında ayrıntılı bilgi toplar.|
|[.NET bellek](#net_memory)|Ayrıntılı .NET bellek ayırma ve atık toplama ile ilgili bilgiler toplar.|
|[Katman etkileşimli](#tier_interaction)|Bir SQL Server veritabanı için zaman uyumlu ADO.NET işlev çağrıları hakkında bilgi toplar.<br /><br /> Katman etkileşim profil, herhangi bir sürümünü Visual Studio kullanarak toplanabilir. Ancak, katman etkileşimli profil oluşturma verilerini, yalnızca Visual Studio kuruluş içinde görüntülenebilir.|

Bazı profil oluşturma yöntemlerini kullanarak, yazılım ve donanım performans sayaçları gibi ek verilerini de toplayabilirsiniz. Daha fazla bilgi için bkz: [ek performans verileri toplama](../profiling/collecting-additional-performance-data.md).

## <a name="sampling"></a>Örnekleme

Örnekleme profili oluşturma yöntemi, profil çalıştırılması sırasında bir uygulama tarafından gerçekleştirilen iş hakkında istatistiksel veriler toplar. Örnekleme yöntemi basit ve uygulama yöntemlerini yürütülmesi üzerinde çok az etkisi yoktur.

Örnekleme profili oluşturma Visual Studio Araçları'nın varsayılan yöntemdir. Aşağıdakiler için yararlı olur:

- İlk explorations, uygulamanızın performansını.
- İşlemci (CPU) kullanımı ile ilgili performans sorunlarını.

Örnekleme profili oluşturma yöntemi, belirlenen aralıklarla Bilgisayar işlemcisi keser ve işlev çağrı yığını toplar. Özel örnek sayımları yürütüyor işlevi için artırılır ve kapsayıcı sayıları tüm işlevleri çağırma çağrı yığınında artırılır. Bu sayıları profili modülü, işlev, kaynak kodu satır ve yönergesi için toplamları örnekleme raporlar görüntülemektedir.

Varsayılan olarak, profil oluşturucu örnekleme aralığı için CPU döngülerini ayarlar. Aralık türü için başka bir CPU performans sayacı değiştirebilir ve sayacı olay sayısı için bir aralığı ayarlayabilirsiniz. Ayrıca, bir SQL server veritabanına ADO.NET yoluyla yapılan sorguları hakkında bilgi sağlayan katman etkileşim profiling(TIP) verileri toplayabilir.

[Örnekleme kullanarak performans istatistikleri toplama](../profiling/collecting-performance-statistics-by-using-sampling.md)

[Örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)

[Örnek yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)

## <a name="instrumentation"></a>İzleme

İzleme profili oluşturma yöntemi, bir profili uygulamasında işlev çağrıları için ayrıntılı zamanlama toplar. Profil oluşturma araçları aşağıdakiler için yararlıdır:

- Giriş/Çıkış darboğazları disk g/ç gibi araştırılıyor.
- Belirli bir modülün incelenmesi veya işlevler kümesi kapatın.

İzleme yöntemi kodu Araçlı dosyasındaki her işlev ve bu işlevler tarafından yapılan her işlev çağrısı için zamanlama bilgilerini yakalar ikili bir dosyaya yerleştirir. Bir dosyaya yazmak gibi işlemleri için işletim içine bir işlevi çağırdığı zaman araçları da tanımlar. İzleme raporları bir işlevi veya kaynak kodu satır harcanan toplam süreyi göstermek için dört değerleri kullanır:

- Geçen Inclusive - işlevi veya kaynak satırı yürütmek için geçen toplam süre.

- Uygulama Inclusive - işlevi veya kaynak satırı yürütülürken, ancak işletim sistemi çağrılarında harcanan zaman hariç harcanan süre.

- Geçen özel - işlevi veya kaynak kodu satır gövdesinde kod yürütmek için geçen süre. İşlev veya kaynak satırı tarafından çağrılan işlevler yürütmek için harcanan süre dışlandı.

- Uygulama özel - işlevi veya kaynak kodu satır gövdesinde kod yürütmek için geçen süre. İşletim sistemi ve işlev veya kaynak satırı tarafından çağrılan işlevler yürütmek için harcanan süre çağrıları yürütmek için geçen süre dışlandı.

İzleme metodunu kullanarak CPU ve yazılım performans sayaçları de toplayabilir.

[İzleme veri değerlerini anlama](../profiling/understanding-instrumentation-data-values.md)

[İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)

[İzleme yöntemi veri görünümleri](../profiling/instrumentation-method-data-views.md)

## <a name="concurrency"></a>Eşzamanlılık

Eşzamanlılık profili oluşturma, birden çok iş parçacıklı uygulamalar hakkında bilgi toplar. Paylaşılan bir kaynağa erişim beklemek için bu rekabeti iş parçacıklarının her zaman ayrıntılı çağrı yığını bilgileri toplar profil kaynak çekişmesini zorlandı. Eşzamanlılık görselleştirme ayrıca birden çok iş parçacıklı uygulamanızın kendisini, donanım, işletim sistemi ve diğer işlemleri ana bilgisayar ile nasıl etkileşim kurduğu hakkında daha fazla genel bilgi toplar:

- Kaynak çakışması raporları çekişmeleri ve modüller, İşlevler, kaynak kod satırlarını ve bekleme gerçekleştiği yönergeleri için bir kaynak için bekleyen harcanan toplam süreyi toplam sayısını görüntüler. Oluşma gibi zaman çizelgesi grafikleri çekişmeleri da gösterir.

- Eşzamanlılık görselleştiricisi performans sorunları, CPU yetersiz kullanım, iş parçacığı Çekişme, iş parçacığı geçiş, eşitleme gecikmeler, çakışan g/ç alanlarının ve diğer bilgileri bulmak için kullanabileceğiniz grafik bilgilerini görüntüler. Mümkün olduğunda veri yığını ve kaynak çağırmak için grafik çıktısı bağlantılar kod. Eşzamanlılık görselleştirme verileri, yalnızca komut satırı ve Windows uygulamaları için toplanabilir.

[Kaynak çakışması veri değerlerini anlama](../profiling/understanding-resource-contention-data-values.md)

[İş parçacığı ve işlem eşzamanlılık verileri toplama](../profiling/collecting-thread-and-process-concurrency-data.md)

[Kaynak çakışması veri görünümleri](../profiling/resource-contention-data-views.md)

[Eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md)

## <a name="net-memory"></a>.NET bellek

.NET bellek ayırma profil oluşturma yöntemi, bir .NET Framework nesnesinin profili uygulamadaki her ayırma bilgisayar işlemci kesintiye uğratır. Nesne yaşam verisi ayrıca toplandığında, profil oluşturucu işlemci her .NET Framework atık toplama sonra kesintiye uğratır.

Profil Oluşturucu türü, boyut ve bir ayırma oluşturulan ya da bir atık toplama zarar görmüş nesne sayısı hakkında bilgiler toplar.

- Ayırma olay oluştuğunda profil oluşturucu işlevi çağrı yığını hakkında ek bilgi toplar. Şu anda yürütülmekte işlevi için özel ayırma sayıları artırılır ve tüm işlevleri çağırma çağrı yığınında için kapsayıcı sayısı artar. .NET raporları profili türleri, modüller, İşlevler, kaynak kod satırlarını ve yönergeler için bu sayıları toplamları sunar.

- Çöp toplama ortaya çıktığında, profil oluşturucu zarar görmüş nesneler hakkındaki verileri ve her atık toplama oluşturmada nesneler hakkında bilgi toplar. Çalıştırma profili oluşturma sonunda, profil oluşturucu değil açıkça zarar görmüş nesneler hakkındaki verileri kaydeder. Nesne ömrü rapor ayrıldı her tür toplamlarını profil Çalıştır görüntüler.

.NET bellek profili oluşturma örnekleme veya araçları modunda kullanılabilir. Nesne ömrü benzersiz to.NET bellek profili oluşturma, raporları ve seçtiğiniz modu ayırma etkilemez:

- .NET bellek çalıştırdığınızda örnekleme modunda profil profiler.NET bellek ayırma olayları aralığı olarak kullanır ve raporlarında (bunlar dahil) ve özel değerler olarak ayrılan nesneleri ve ayrılan toplam bayt sayısını görüntüler.

- .NET bellek profili oluşturma araçları modunda çalıştırdığınızda, birlikte (bunlar dahil) ve özel ayırma değerleri ayrıntılı zamanlama bilgileri toplanır.

[Bellek ayırma ve nesne yaşam süresi veri değerlerini anlama](../profiling/understanding-memory-allocation-and-object-lifetime-data-values.md)

[.NET bellek ayırma ve yaşam süresi verilerini toplama](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)

[.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)

## <a name="tier-interaction"></a>Katman etkileşimli

Katman etkileşimli profil oluşturma ekler bilgi zaman uyumlu hakkında bir profil oluşturma veri dosyası [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] arasında çağıran bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sayfa veya başka bir uygulama ve [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] veritabanı. Veri sayısı ve zaman çağrılarının ve maksimum ve minimum içerir. Katman etkileşimli veri örnekleme, izleme, .NET bellek veya eşzamanlılık yöntemleri ile toplanan verileri profil için eklenebilir.

![Katman etkileşim profil verileri](../profiling/media/tierinteraction_profilingtools.png "TierInteraction_ProfilingTools")

Profil oluşturma araçları tarafından toplanan katman etkileşim verileri

[Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)

[Etkileşim görünümleri](../profiling/tier-interaction-views.md)

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: bir web sitesi için performans verileri toplama](../profiling/how-to-collect-performance-data-for-a-web-site.md)  
[Performans profili oluşturma Başlangıç Kılavuzu](../profiling/beginners-guide-to-performance-profiling.md)