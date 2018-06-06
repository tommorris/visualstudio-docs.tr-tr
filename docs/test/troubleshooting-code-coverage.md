---
title: Visual Studio'da kod kapsamı sorunlarını giderme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: troubleshooting
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 1169d4e482f097ca923cc017964724e5886658d1
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751572"
---
# <a name="troubleshoot-code-coverage"></a>Kod Kapsamı Sorunlarını Giderme

Visual Studio'daki kod kapsamı analiz aracı yerel ve yönetilen (.ddl veya .exe dosyaları) derlemeler için verileri toplar. Ancak bazı durumlarda Kod Kapsamı Sonuçlar penceresi "Boş üretilen sonuçlar: ..." benzeri bir hata gösterir. Neden boş sonuçlar alabilirsiniz birkaç nedeni vardır. Bu makalede, bu sorunları çözmenize yardımcı olur.

## <a name="what-you-should-see"></a>Görmeniz gereken

İsterseniz bir **kod kapsamını çözümleme** Test menüsünde komutunu ve yapı ve test başarıyla çalışması sonra kod kapsamı penceresinde sonuçlarının bir listesini görürsünüz. Ayrıntıları görmek için öğeleri genişletmeniz gerekebilir.

![Kod kapsamı sonuçları renklendirme ile](../test/media/codecoverage1.png)

Daha fazla bilgi için bkz: [kullanarak kod kapsamı belirleme ne kadar kodun için test](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

## <a name="possible-reasons-for-seeing-no-results-or-old-results"></a>Sonuçları ya da eski sonuçları görmek için olası nedenler

### <a name="do-you-have-the-right-edition-of-visual-studio"></a>Visual Studio'nun doğru sürümüne sahip misiniz?
 Visual Studio Enterprise gerekir.

### <a name="no-tests-were-executed"></a>Hiçbir sınama yürütülemedi

Analiz&mdash;çıktı penceresini denetleyin. İçinde **Göster çıktısını** aşağı açılan listesinde, seçin **testleri**. Herhangi bir uyarı veya hatanın günlüğe kaydedilip kaydedilmediğine bakın.

Açıklama&mdash;kod kapsamı çözümlemeyi testleri çalıştırırken yapılır. Testler çalıştırıldığında sadece belleğe yüklenen derlemeleri içerir. Testleri hiçbiri yürütüldüğünden, rapor için kod kapsamı için hiçbir şey yoktur.

Çözümleme&mdash;Test Explorer'da seçin **tümünü Çalıştır** testleri başarıyla çalıştığını doğrulamak için. Kullanmadan önce hataları düzeltmek **kod kapsamını çözümleme**.

### <a name="youre-looking-at-a-previous-result"></a>Bir önceki sonucunda arıyorsanız

Değiştirme ve testleri yeniden çalıştırın, bir önceki kod kapsamı sonuç görünür, bu eski çalıştırma renklendirme kod dahil olabilir.

1.  Kod Kapsamı Çözümlemeyi Çalıştırın.

2.  En son sonuç kümesini Kod Kapsamı sonuçları penceresinde seçtiğinizden emin olun.

### <a name="pdb-symbol-files-are-unavailable"></a>.pdb (simge) dosyaları kullanılamaz

Analiz&mdash;derleme hedef klasörü (genellikle bin\debug) açın ve her derlemesi için olduğunu .pdb dosyasını .dll veya .exe dosyası ile aynı dizinde doğrulayın.

Açıklama&mdash;kod kapsamı altyapısı her derlemeyi test çalışması sırasında erişilebilir dosya kendi ilişkili .pdb sahip olması gerekir. Belirli bir derleme için .pdb dosyası yoksa, derleme analiz değil.

.pdb dosyası .dll veya .exe dosyasıyla birlikte aynı derleme sırasında oluşturulmalıdır.

Çözümleme&mdash;yapı ayarlarınızı .pdb dosyası oluşturma emin olun. Proje yapılandırıldığında .pdb dosyaları güncelleştirilmediyse, ardından açık proje özelliklerini seçin **yapı** sayfasında, **Gelişmiş**ve incelemek **hata ayıklama bilgisi**.

.pdb ve .dll veya .exe dosyaları farklı yerlerdeyse, .pdb dosyasını aynı dizine kopyalayın. Kod kapsamı motorunu .pdb dosyalarını başka bir konumda aramak için yapılandırmak mümkündür. Daha fazla bilgi için bkz: [kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md).

### <a name="using-an-instrumented-or-optimized-binary"></a>Araçlı ya da optimize edilmiş ikili kullanma

Analiz&mdash;ikili Gelişmiş en iyi duruma getirme profil temelli iyileştirme gibi herhangi bir biçimde gerçekleştirdi veya vsinstr.exe veya vsperfmon.exe gibi bir profil oluşturma aracı tarafından izlenmiş sağlamayacağınızı belirleyin.

Açıklama&mdash;bir derleme zaten izlenmiş veya başka bir profil oluşturma aracı tarafından en iyi duruma getirilmiş, derleme kod kapsamı çözümlemeyi atlanır. Kod kapsamı çözümlemeyi böyle derlemelerini gerçekleştirilemiyor.

Çözümleme&mdash;en iyi duruma getirme ve kullanım yeni bir yapı kapatma.

### <a name="code-is-not-managed-net-or-native-c-code"></a>Kod yönetilen (.NET) veya yerel (C++) kodu değilse

Analiz&mdash;bazı testleri çalıştırma üzerinde doğrulama yönetilen ya da C++ kodu.

Açıklama&mdash;Visual Studio'da kod kapsamı çözümlemeyi yalnızca yönetilen ve yerel (C++) kodu kullanılabilir. Üçüncü taraf araçları ile çalışıyorsanız, farklı bir platformda bazılarını veya tümünü kod yürütebilir.

Çözümleme&mdash;hiçbiri kullanılamaz.

### <a name="assembly-has-been-installed-by-ngen"></a>NGen tarafından yüklenen derleme

Analiz&mdash;derleme yerel görüntü önbellekten yüklenmedi doğrulayın.

Açıklama&mdash;performans nedenleriyle yerel görüntü derlemeleri değil incelenir. Daha fazla bilgi için bkz: [Ngen.exe (yerel Görüntü Oluşturucu)](/dotnet/framework/tools/ngen-exe-native-image-generator).

Çözümleme&mdash;derlemeye MSIL sürümünü kullanın. NGen ile işlem yok.

### <a name="custom-runsettings-file-with-bad-syntax"></a>Hatalı sözdizimi ile özelleştirilmiş .runsettings dosyası

Analiz&mdash;özel kullanıyorsanız *.runsettings* dosyasının söz dizimi hatası içeriyor olabilir. Kod kapsamı çalışmıyor ve kod kapsamı penceresi eski sonuçları test çalıştırma ya da onu sonunda açmaz.

Açıklama&mdash;kod kapsam seçeneklerini yapılandırmak için özel .runsettings dosyasını ile birim testleri çalıştırabilirsiniz. Bu seçenek size dosyaları eklemeyi veya çıkarmayı sağlar. Daha fazla bilgi için bkz: [kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md).

Çözümleme&mdash;hatalarının olası iki tür vardır:

-   **XML hatası**

     .runsettings dosyasını Visual Studio XML düzenleyicisinde açın. Hata göstergelerine bakın.

-   **Normal ifade hatası**

     Dosyadaki her dize bir düzenli ifadedir. Her birini hatalar için gözden geçirin ve bu belirtilen için bakın:

    -   Eşleşmeyen parantez (...) veya atlanmayan parantez \\(... \\). Arama dizisinde parantezleri eşleştirmek istiyorsanız, atlatmak gerekir. Örneğin, bir işlev kullanımı eşleştirmek için şunu yazın: `.*MyFunction\(double\)`

    -   İfadenin başına yıldız veya artı koyun. Herhangi bir karakter dizesini eşleştirmek için yıldız bir nokta kullanın: `.*`

### <a name="custom-runsettings-file-with-incorrect-exclusions"></a>Yanlış istisnalarla özelleştirilmiş .runsettings dosyası

Analiz&mdash;özel kullanıyorsanız *.runsettings* dosya, derlemenizi içerdiğinden emin olun.

Açıklama&mdash;kod kapsam seçeneklerini yapılandırmak için özel .runsettings dosyasını ile birim testleri çalıştırabilirsiniz. Bu seçenek size dosyaları eklemeyi veya çıkarmayı sağlar. Daha fazla bilgi için bkz: [kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md).

Çözümleme&mdash;Tümünü Kaldır `Include` .runsettings dosyasını ve ardından Kaldır tüm düğümlerden `Exclude` düğümleri. Bu problemi çözdüyse, bunları aşamalar halinde yerleştirin.

DataCollectors düğümünün Kod Kapsamını belirttiğinden emin olun. Aşağıdaki örnekte karşılaştırmak [kod kapsamı çözümlemeyi özelleştirme](../test/customizing-code-coverage-analysis.md).

## <a name="some-code-is-always-shown-as-not-covered"></a>Bazı kodlar her zaman kapsandığı gibi gösterilmez

### <a name="initialization-code-in-native-dlls-is-executed-before-instrumentation"></a>İzlemeden önce yerel DLL'lerdeki kodun başlatılması

Analiz&mdash;statik olarak bağlantılı yerel kodda, başlatma işlevinin parçası **DllMain** ve onu çağıran kodu bazen gösterilen kodu yürütülen olsa bile, kapsanmayan olarak.

Açıklama&mdash;kod kapsamı aracının çalıştığı yalnızca çalışan uygulama başlatılmadan önce bir derlemeye araçları ekleyerek. Hiçbir derleme başlatma kodda önceden yüklenen **DllMain** derleme yükler hemen sonra ve uygulama çalıştırılmadan önce yürütür. Kapsanmayan için bu kodu görüntülenir. Genellikle, bu statik olarak yüklenen derlemeler için geçerlidir.

Çözümleme&mdash;yok.

## <a name="see-also"></a>Ayrıca bkz.

- [Ne Kadar Kodun Test Edildiğini Belirlemek için Kod Kapsamını Kullanma](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)