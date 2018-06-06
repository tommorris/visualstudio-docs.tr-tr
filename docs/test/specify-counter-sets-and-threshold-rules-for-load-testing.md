---
title: Visual Studio'da Test yük kümelerini ve eşik kurallarını sayacı
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- counters, counter sets
- load tests, thresholds
- counter sets
- load tests, performance
- load tests, counter sets
- load tests, threshold rules
ms.assetid: 9e14d955-f3a4-4717-bbfe-7f08cdda5678
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 7e5e6919dbc37294ef677f3c512c51d53aea0e2f
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751348"
---
# <a name="specify-counter-sets-and-threshold-rules-for-computers-in-a-load-test"></a>Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtin

Yük testleri performans sayacı verilerini analiz ederken kullanışlı olan adlandırılmış sayaç kümeleri sağlar. Sayaç kümeleri teknoloji ile düzenlenir ve uygulama, ASP.NET, .NET uygulaması, IIS ve SQL içerir. Kullanarak bir yük testi oluşturduğunuzda **Yeni Yük Testi Sihirbazı**, başlangıç sayaç kümesini ekleyin. Bu, yük testi için önceden tanımlanmış ve önemli sayaç kümeleri kümesi sunar. Sayaçlarınızın içinde yönetmek **Yük Testi Düzenleyicisi**.

> [!NOTE]
> Yük testleri Uzak makinelerde dağıtılmışsa, denetleyici ve aracı sayaçları denetleyici ve aracı eşlenen sayaç. Yükleme testinizde uzak makineleri kullanma hakkında daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

Sayaç kümeleri, belirttiğiniz bilgisayarlardan toplanır. Bir sayaç kümesi ve bir yük testi sırasında kullanılan bir bilgisayar arasındaki ilişkidir bir *sayaç kümesi eşlemesi*. Örneğin, test ettiğiniz Web server ASP.NET, IIS olabilir ve .NET uygulama sayaç kümesi eşlemelerine.

Varsayılan olarak, performans sayaçları denetleyicisi ve aracıları toplanır. Daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

Sayaçları toplamak bilgisayarları listesine test altındaki sunucular eklemek önemlidir. Ardından, herhangi bir önemli sistem veri toplanır ve yük testi sırasında izlenir.

## <a name="tasks"></a>Görevler

|Görevler|İlişkili Konular|
|-----------|-----------------------|
|**Yük testi için sayaç kümelerini yönetme:** yük testlerini oluşturduktan sonra sayaç kümesi Yük Testi Düzenleyicisi'ni düzenleyebilirsiniz. Sayaç kümelerini yönetme, performans verileri toplamak istediğiniz bilgisayarlar kümesi seçme ve her bir bilgisayardan toplamak için sayaç kümelerini kümesi atama içerir. Yük Testi Düzenleyicisi'nde sayaçlarınızın yönetin.|-   [Nasıl yapılır: sayaç kümelerini yönetme](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)|
|**Sayaç kümeleri yük testine ekleme:** Yeni Yük Testi Sihirbazı ile bir yük testi oluşturduğunuzda, bir başlangıç sayaç kümesini ekleyin. Bu, yük testi için önceden tanımlanmış sayaç kümeleri kümesi sunar. Bir yük testi oluşturduktan sonra Yük Testi Düzenleyicisini kullanarak varolan sayaç kümelerine yeni sayaçlar ekleyebilirsiniz.|-   [Nasıl yapılır: sayaç kümelerine sayaç ekleme](../test/how-to-add-counters-to-counter-sets-using-the-load-test-editor.md)<br />-   [Nasıl yapılır: özel sayaç kümeleri ekleme](../test/how-to-add-custom-counter-sets-using-the-load-test-editor.md)|
|**Yük testi için sayaçları kullanarak bir eşik kuralı belirtin:** bir eşik kuralı, bir yük testi sırasında sistem kaynak kullanımını izlemek için bir bireysel performans sayacı üzerine ayarlanan bir kuraldır. Sayaç kümesi tanımları birçok anahtar performans sayaçları için önceden tanımlanmış eşik kurallarını içerir. Yük testlerindeki eşik kuralları bir performans sayacı değeri sabit bir değer veya başka bir performans sayacı değeri ile karşılaştırın.|-   [Nasıl yapılır: bir eşik kuralı ekleme](../test/how-to-add-a-threshold-rule-using-the-load-test-editor.md)|
|**Sayaç kümeleri eşlendi bilgisayarlara kolay adlar atayın:** kolayca tanınan bir adı bir bilgisayar için geçerli sağlayan bilgisayar etiketleri ekleyebilirsiniz. Etiketler görüntülenir **sayaç kümesi eşlemeleri** Yük Testi Düzenleyicisi'nde ağaç düğümü. Daha da önemlisi, etiketler görüntülenir hangi rolü belirlemede yardımcı Excel raporlarında yük testinde, örneğin, "Lab2 içinde Web Server1" bilgisayarında veya "Phoenix ofisi içinde SQL Server2".<br /><br /> Daha fazla bilgi için bkz: [Test karşılaştırmaları veya eğilim analizleri için yük testleri sonuçlarını raporlama](../test/compare-load-test-results.md).|-   [Nasıl yapılır: kümesi eşlemelerine bilgisayar etiketleri sayaç ekleme](../test/how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor.md)|

## <a name="use-counter-sets"></a>Sayaç kümeleri kullanma

Yük testi araçları toplar ve zaman içinde sayaçlarını kullanarak performans verilerini grafik. Sayaç verileri, bir yük testi sırasında kullanıcı tarafından belirtilen aralıklarla toplanır. Daha fazla bilgi için bkz: [nasıl yapılır: örnek hızı belirtme](../test/how-to-specify-the-sample-rate-for-a-load-test.md). Çalışma zamanında sayaçları görüntüleyebilirsiniz veya kullanarak yük testi sonra görüntüleyebilirsiniz *Yük Testi Çözümleyicisi*.

Sayaç verileri sunucusunda ve herhangi bir bilgisayarda test çalıştırdığı toplanır. Sayaçlar, testleri çalıştırmak için aracı bilgisayarları kümesini ayarladıysanız, bu bilgisayarlarda da toplanır.

Üç sayaç kategorisi vardır: yüzdeleri, sayıları ve ortalamalar. Bazı örnekler % CPU kullanımı, SQL Server kilidi sayar ve Saniyedeki IIS istekleri ' dir.

![Yük Testi Sayaç kümeleri](../test/media/loadtestcountersets.png)

Tek tek HTTP istekleri için performans verilerini bir test çalıştıran bilgisayar tarafından bildirilir. Aracı bilgisayar gibi. İstekleri için ortalama süre için ilk bayta kalan, yanıt süresi ve saniye başına istek sayısı gibi verileri izlemek.

Bir Web sunucusunda performans verileri koleksiyonunu kolaylaştırmak için Visual Studio Enterprise ayrıca Yük testlerindeki kullanım için önceden tanımlanmış, adlandırılmış sayaç kümeleri de sağlar. Bu ayarlar, IIS, ASP.NET veya SQL Server çalıştıran bir sunucu incelerken yararlıdır. Yük Testi Düzenleyicisini kullanarak sayaç varsayılan kümesinde sağlanmayan sayaçları eklenebilir. Bu bilgisayarlarda kaynak kullanımını izleyebilirsiniz emin olmak için yük testlerini bilgisayarları veya test altındaki sunucuları eklemek önemlidir. Daha fazla bilgi için bkz: [nasıl yapılır: sayaç kümelerini Yönet](../test/how-to-manage-counter-sets-using-the-load-test-editor.md).

Sonuç çözümlemesi yükleme çalıştırır, belirli bir alanını, etki alanına özgü bilgisi kümesi eşik kuralları ve bir ölçüm uygulamada belirli bir sorunun ne zaman yansıtır anlatma burada toplamak için hangi verilerin bilmek için sık gerektirir. Daha fazla bilgi için bkz: [eşik kuralları hakkında](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md#SpecifyingCounterSetsThresholdRulesAboutThresholdRules).

### <a name="performance-counter-sampling-interval-considerations"></a>Performans sayacı örnekleme aralığı hakkında önemli noktalar

Uygun bir değer seçin **örnek hızı** özelliğinde yük testi çalıştırma ayarları yük testlerini uzunluğuna göre. Varsayılan değer olarak beş saniye gibi daha küçük bir örnek hızı yük testi sonuçları veritabanında daha fazla alan gerektirir. Uzun yük testleri için örnek hızı artırma toplanan veri miktarını azaltır. Daha fazla bilgi için bkz: [nasıl yapılır: örnek hızı belirtme](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Örnek hızları için bazı yönergeler verilmiştir.

|Yük test süresi|Önerilen örnek hızı|
|------------------------|-----------------------------|
|\< 1 saat|5 saniye|
|1−8 saatleri|15 saniye|
|8−24 saatleri|30 saniye|
|> 24 saat|60 saniye|

## <a name="store-performance-data"></a>Performans verileri depola

Yük testi sırasında performans sayacı verileri toplanır ve depolanır *Yük Testi Sonuçları Deposu*. Daha fazla bilgi için bkz: [yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md).

## <a name="about-threshold-rules"></a>Eşik kuralları hakkında

A *eşik kuralı* bir yük testi sırasında sistem kaynak kullanımını izlemek için bir bireysel performans sayacı üzerine ayarlanan bir kuraldır. Sayaç kümesi tanımları birçok anahtar performans sayaçları için önceden tanımlanmış eşik kurallarını içerir. Daha fazla bilgi için bkz: [Yardım analiz performans sayacı verilerini Yük testlerindeki kullanarak sayaç kümelerine](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

## <a name="threshold-rules-and-levels"></a>Eşik kuralları ve düzeyleri

Yük testlerinde eşik kuralları oluşturduğunuzda, iki tür kural arasında seçin:

Sabiti karşılaştırma&mdash;bir performans sayacı değeri sabit değerle karşılaştırın.

Sayaçları karşılaştırma&mdash;bir performans sayacı değeri başka bir performans sayacı değeri ile karşılaştırın.

Eşik kuralları oluşturduğunuzda kural düzeylerini de ayarlayın. Uyarı eşiği ve Kritik Eşik düzeyleri şunlardır. Yük testi görüntülediğinizde, uyarı düzeyi Eşik ihlalleri sarı simgeyle gösterilir ve kritik düzey Eşik ihlalleri kırmızı simgeyle gösterilir.

## <a name="the-alert-if-over-property"></a>Özelliği üzerinden olursa uyarı

Ayarlama **uyarı üzerinden** özelliğine **True** bir Eşiği aşan bir sorun olduğunu gösterebilir. Örneğin, üzerinde eşik kuralı ayarlarsanız **% işlemci zamanı**, ve değer 90, kullanım'dan büyük olduğunda uyarı almak istediğiniz **Sabiti Karşılaştır** kural türü, Ayarla **Kritik Eşik Değer** 90 ve kümesi **uyarı üzerinden** için **doğru**.

Ayarlama **uyarı üzerinden** özelliğine **False** eşiğin altına dönmeden bir sorun olduğunu gösterebilir. Örneğin, üzerinde eşik kuralı ayarlarsanız **İsteği/sn**, ve değer 50, kullanım altında olduğunda uyarı almak istediğiniz **Sabiti Karşılaştır** kural türü, Ayarla **Kritik Eşik değeri** 50 ve kümesi **uyarı üzerinden** için **False**.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: bir eşik kuralı ekleme](../test/how-to-add-a-threshold-rule-using-the-load-test-editor.md)
- [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)