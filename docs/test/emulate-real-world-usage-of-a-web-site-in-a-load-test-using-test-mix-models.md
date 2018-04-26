---
title: Visual Studio'da Test yük için bir Web sitesi gerçek dünya kullanımının öykünmesini yapma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load model, specifying
- load test load model, specifying
ms.assetid: b7fae849-0538-40d1-ab35-2bb3a0fe4393
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 9ec5777bc1a2bfffc650497314a219d071057beb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="emulate-expected-real-world-usage-of-a-web-site-or-application-in-a-load-test-using-a-test-mix-models"></a>Bir Web sitesi veya uygulama Test Karışım Modelleri kullanarak yük testi beklenen gerçek dünya kullanımının öykünmek

Bir Web sitesi veya yük test ettiğiniz uygulamanın beklenen gerçek dünya kullanımını daha doğru bir şekilde tahmin etmek için yük modeli oluşturma seçeneklerini kullanın. Doğru yük modelini temel alan olmayan bir yük testi yanıltıcı sonuçları oluşturabileceğinden Bunu yapmak önemlidir.

## <a name="test-mix-model-enhancements"></a>Test karışımı modeli geliştirmeleri

Yük Testi Düzenleyicisi'ni veya test karışımı modeli Sihirbazı'nı kullanarak bir yük testi senaryosu için test karışımını aşağıdaki türlerini belirtebilirsiniz. Daha fazla bilgi için bkz: [senaryosunda Test karışımı modeli değiştirme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

Yük testi senaryonuz için aşağıdaki test karışımı modeli seçeneklerinden birini belirtebilirsiniz:

-   **Testleri toplam sayısına göre:** hangi Web performans veya birim testi sanal kullanıcı test yineleme başladığında çalıştırıldığında belirler. Yük testi sonunda, belirli bir test sayısı atanan test dağılımı eşleşmedi. Bu test karışımı modeli işlem yüzdeleri bir IIS günlüğü veya üretim verileri üzerinde test karışımı alma kullanın. Daha fazla bilgi için bkz: [yüzdesi temelinde testler başlatılan](#BasedOnTestsStarted).

-   **Sanal kullanıcı sayısına göre:** belirli bir Web performans veya birim testi çalıştıracak sanal kullanıcıların yüzdesini belirler. Yük testindeki herhangi bir noktada, belirli bir testi çalıştıran kullanıcıların sayısını atanan dağıtım ile eşleşir. Bu test karışımı modeli test karışımı özel bir test çalıştıran kullanıcılar yüzdesi alma kullanın. Daha fazla bilgi için bkz: [yüzde tabanlı sanal kullanıcıları](#PercentageBasedonVirtualUsers).

-   **Kullanıcı adına dayalı:** bir belirtilen sayıda saat başına kullanıcı başına yük testi süresince her Web performans testi veya birim testi çalıştırılır. Yük testi boyunca belirli bir hızda testi sanal kullanıcı istediğinizde bu test karışımı modeli kullanın. Daha fazla bilgi için bkz: [ilerleme test karışımı](#PacingTestMix).

    > [!TIP]
    > Seçtiğinizde **yüzdesi test karışımı** ve seçtiğinizde **yüzde tabanlı sanal kullanıcılar**? Bazı testleri test karışımında diğer testleri daha uzun bir süreye bu iki seçenek arasındaki fark önemlidir. Bu durumda, muhtemelen seçmelisiniz **yüzde tabanlı sanal kullanıcıları**. Bu seçenek, bir test çalışması önlemeye yardımcı olur, çok sayıda kullanıcı uzun süreli testleri çalıştırma olasılığı artar içinde. Ancak, tüm testler benzer süreleri varsa, daha güvenli bir şekilde seçebileceğiniz **yüzdesi test karışımı**.

-   **Sıralı sırasına göre:** her sanal kullanıcı testleri senaryoda tanımlanan sırayla Web performans veya birim testleri çalıştırır. Sanal kullanıcı yük testi tamamlanana kadar bu sırayla testlerin dolaşma devam eder. Daha fazla bilgi için bkz: [sıralı](#SequentialOrder).

###  <a name="BasedOnTestsStarted"></a> Başlatılan testleri temel alan yüzdesi
 İçin her test karışımında, ne sıklıkta test sonraki test olarak çalıştırmak için seçilmiş olan belirleyen bir yüzde belirtebilirsiniz. Örneğin, üç testleri aşağıdaki yüzde değerleri atayabilirsiniz:

-   TestA (% 50)

-   TestB (%35)

-   TestC (%15)

 Bu ayarı kullanırsanız başlatmak için sonraki test atanan yüzdeyi temel alır. Bunun için her test çalışmakta olan sanal kullanıcıların sayısını dikkate alarak olmadan.

###  <a name="PercentageBasedonVirtualUsers"></a> Sanal kullanıcı temelli yüzdesi
 Bu test karışımı modeli belirli bir testi çalıştıracak sanal kullanıcıların yüzdesini belirler. Bu test karışımı modeli kullanırsanız başlatmak için İleri test yalnızca atanan yüzdeleri aynı zamanda belirli bir testi çalışmakta olan sanal kullanıcıların yüzdesini temel alır. Yük testindeki herhangi bir noktada, belirli bir testi çalıştıran kullanıcıların sayısını mümkün olduğunca yakın atanan dağıtım eşleşir.

###  <a name="PacingTestMix"></a> Test Karışımı İlerlemesi
 Hız test karışımı belirtirseniz, her sanal kullanıcı her testi için test yürütmesi oranı test karışımında ayarlayın. Sanal kullanıcı saat başına testler gibi her bir test Bu oran ifade edilir. Örneğin, aşağıdaki hız test karışımını aşağıdaki testlere atayabilirsiniz:

-   TestA: saat başına kullanıcı başına 4 testleri

-   TestB: saat başına kullanıcı başına 2 testleri

-   TestC: saat başına kullanıcı başına 0,125 testleri

 Yük testi çalışma zamanı altyapısı hız test karışımı modeli kullanırsanız, testleri başladığı gerçek hızı belirtilen oranla eşit veya daha az olduğunu güvence altına alır. Testler tamamlanması çok uzun atanan numarası çalıştırırsanız, bir hata döndürülür.

 **Test Yinelemeleri Arasındaki Düşünme süresi** ayarı hız test karışımı kullandığınızda geçerli değildir.

#### <a name="applying-distribution-to-pacing-delay"></a>Gecikmesine Dağıtım uygulama
 Değeri **dağıtım gecikmesine Uygula** bir yük testi senaryosunda özelliği true veya false ayarlanabilir:

-   **Doğru**: Senaryo değeri tarafından belirtilen tipik istatistiksel dağıtım gecikmelerine **saatte kullanıcı başına testler** Test Karışımını Düzenle iletişim sütununda. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Örneğin, sahip olduğunuz varsayılmıştır **saatte kullanıcı başına testler** Düzenle Test karışımı iletişim kutusu için saat başına 2 kullanıcı test değeri. Varsa **dağıtım gecikmesine Uygula** özelliği ayarlanmış **doğru**, tipik bir istatistik dağıtım testler arasındaki bekleme süresini uygulanır. Testler hala saatte 2 test çalışır, ancak aralarında 30 dakika mutlaka olmaz. İlk test 4 dakika sonra ikinci test 45 dakika sonra çalışabilir.

-   **Yanlış**: testleri değeri için belirtilen belirli hızda çalışır **saatte kullanıcı başına testler** Test Karışımını Düzenle iletişim sütununda. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Örneğin, sahip olduğunuz varsayılmıştır **saatte kullanıcı başına testler** Düzenle Test karışımı iletişim kutusu için saat başına 2 kullanıcı test değeri. Varsa **dağıtım gecikmesine Uygula** özelliği ayarlanmış **yanlış**, testlerinizi çalıştırdığınızda, neredeyse hiçbir yaratmamış olursunuz. Test 30 dakikada bir çalışır. Bu, saat başına 2 testleri çalıştırmanızı sağlar.

 Daha fazla bilgi için bkz: [nasıl yapılır: dağıtım Adımlama gecikme kullandığınızda için bir kullanıcı hızınıza Test karışımı modeli uygulamak](../test/how-to-apply-distribution-to-pacing-delay-when-using-a-user-pace-test-mix-model.md).

###  <a name="SequentialOrder"></a> Sıralı
 Temel sıralı test düzeni seçeneğini seçerek testlerin tanımlandığı sırada senaryoda tüm Testleri Çalıştır her sanal kullanıcı yapar.

## <a name="test-iterations-property"></a>Test yinelemeleri özelliği
 Çalışma ayarları özelliklerini Test Yinelemeleri özelliği için bir değer belirtebilirsiniz. Bu değer bir yük testi çalıştırmak için test yinelemeleri sayısıdır. Belirtilen test yineleme sayısını başlatıldıktan sonra hiçbir ek test yinelemeleri ayarlarını yük profillerinden birini rağmen başlatılır. Belirtilen test yineleme sayısını tamamlandıktan sonra Yük testi sona erer. Daha fazla bilgi için bkz: [nasıl yapılır: bir çalıştırma ayarında Test yineleme sayısı belirtin](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md).

## <a name="initialize-and-terminate-tests"></a>Testleri başlatma ve sonlandırma
 Her sanal kullanıcının yük testi oturumunun başında ve sonunda çalıştırılacak testleri seçebilirsiniz. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

-   **Testi başlatmak**. Testleri test karışımında birini çalıştırmadan önce bu test her sanal kullanıcı tarafından çalıştırılır.

-   **Test sonlandırmak**. Belirli bir sanal kullanıcı için tüm testler çalıştırıldıktan sonra bu test çalıştırılır.

 Lütfen testi başlatma ve sonlandırma testi hakkında aşağıdakileri unutmayın:

-   Yineleme sayısına göre yerine zamana göre yük test süresi belirtebilirsiniz. Bu durumda, çalışma süresini yük testi tamamlandığında, sonlandırma test çalıştırılmaz.

-   Başlatma testi birim testi veya bir Web performans testi başlatma testi tamamlandıktan sonra testiyse veya tamamlandıktan, nesnenin durumu kaydedilir. Bunu daha sonra Başlangıç bağlamı olarak testleri test karışımında yinelemelerini için kullanılacaktır.

-   Yeni kullanıcılar, yeni kullanıcı yüzdesi, senaryo özelliğinde tanımlanan her zaman yürütme başlatma testi, test karışımı testten Sonlandır test ve bir yineleme.

## <a name="see-also"></a>Ayrıca bkz.

- [Bir Test çalıştıran sanal kullanıcı olasılığını belirtmek için test karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)
- [Sanal kullanıcı etkinlikleri modellemek için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md)
- [Hangi testlerin bir yük testi senaryosunda ekleneceğini belirlemek için Test Karışımını düzenleme](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)
- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)
- [Test karışımı modeli senaryosunda değiştirme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)