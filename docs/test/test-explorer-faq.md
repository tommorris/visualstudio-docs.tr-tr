---
title: Visual Studio Test Gezgini hakkında SSS
ms.date: 1/15/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Test Explorer
- Test window
- Visual Studio Test Explorer
- summary line
- unit tests
- Test Explorer FAQ
ms.author: kehavens
ms.workload:
- multiple
author: kendrahavens
manager: douge
ms.openlocfilehash: 720a69b1eae8a14247027a52ef2972e43203163b
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382415"
---
# <a name="visual-studio-test-explorer-faq"></a>Visual Studio Test Gezgini hakkında SSS

## <a name="test-discovery"></a>Test bulma

### <a name="1-the-test-explorer-is-not-discovering-my-tests-that-are-dynamically-defined-for-example-theories-custom-adapters-custom-traits-ifdefs-etc-how-can-i-discover-these-tests"></a>1. Test Gezgini dinamik olarak tanımlanan testlerimi bulma değil. (Örneğin, Teoriler, özel bağdaştırıcı, özel özellikleri, #ifdefs, vb.) Bu testleri bulmak ne?

  Derleme tabanlı bulma içinde açık olduğundan emin olun ve projenizi **Araçları** > **seçenekleri** > **Test**.

  [Gerçek zamanlı test bulma](https://go.microsoft.com/fwlink/?linkid=862824) kaynak tabanlı test bulma. Teoriler, özel bağdaştırıcı, özel özellikleri kullanan testler bulamaz `#ifdef` deyimleri, çalışma zamanında tanımlanmadığından vb. Bu testler doğru şekilde bulunmak bir derleme gereklidir. 15.6 Preview sürümlerinde, derleme tabanlı bulma (Geleneksel Bulucu) yalnızca derlemeler sonra çalışır. Bu ayar, while gibi çok testleri gerçek zamanlı Test bulma bulur anlamına gelir. düzenlemekte olduğunuz ve derleme tabanlı bulma dinamik olarak tanımlanan testleri, derleme sonrası görünmesini sağlar. Gerçek zamanlı Test bulma yanıt hızını artırır ancak durağan derleme sonrası tam ve doğru sonuçlar elde izin verir.

### <a name="2-what-does-the--plus-symbol-that-appears-in-the-top-line-of-test-explorer-mean"></a>2. Ne yaptığını '+' (artı) Test Gezgini ortalama ilk satırda görünen simge?

  '+' (Artı) sembolü, derleme tabanlı bulma açık olduğu sürece, daha fazla test derleme sonrası bulunan belirtir. Dinamik olarak tanımlanmışsa Test projenizde algılanan görünür.

  ![Artı özet satırı simgesi](media/testex-plussymbol.png)

### <a name="3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on"></a>3. Derleme tabanlı bulma artık Projem için çalışmaktadır. Nasıl bu kapatırım yeniden?

  Git **Araçları** > **seçenekleri** > **Test** ve kutusunu işaretlemeniz **testleri yerleşik derlemelerden sonra ayrıca keşfedin oluşturur.**

  ![Derleme tabanlı seçeneği](media/testex-toolsoptions.png)

### <a name="4-tests-now-appear-in-test-explorer-while-i-type-without-having-to-build-my-project-what-changed"></a>4. Ben Projemi oluşturmak zorunda kalmadan, yazarken testleri şimdi Test Gezgini'nde görünür. Neler değişti?

  Bu özelliğin adı [gerçek zamanlı test bulma](https://go.microsoft.com/fwlink/?linkid=862824). Testleri bulmak ve Test Gezgini, projenizi oluşturmaya gerek kalmadan gerçek zamanlı olarak doldurmak için Roslyn çözümleyicinizi kullanır. Teoriler veya özel nitelikler gibi dinamik olarak tanımlanan testler için test bulma davranış hakkında daha fazla bilgi için bkz. SSS 1.

### <a name="5-what-languages-and-test-frameworks-can-use-real-time-test-discovery"></a>5. Gerçek zamanlı Test bulma, hangi diller ve test çerçeveleri kullanabilir miyim?

  [Gerçek zamanlı test bulma](https://go.microsoft.com/fwlink/?linkid=862824) yalnızca bu yana yönetilen diller (C# ve Visual Basic) için çalışır Roslyn derleyicisi kullanılarak oluşturulur. Şimdilik, gerçek zamanlı Test bulma yalnızca xUnit, NUnit ve MSTest çerçeveleri çalışır.

### <a name="6-how-can-i-turn-on-logs-for-the-test-explorer"></a>6. Test Gezgini için nasıl günlüklerini kapatırım?

  Gidin **Araçları** > **seçenekleri** > **Test** ve günlüğe kaydetme bölümü bulun.

### <a name="7-why-are-my-tests-in-uwp-projects-not-discovered-until-i-deploy-my-app"></a>7. Neden testlerimi uygulamamı dağıtabilirim kadar bulunmayan UWP projelerinde?

  Uygulama dağıtıldığında UWP testler farklı bir çalışma zamanı hedef. Bu testler doğru bir şekilde UWP projeleri için keşfetmek için yalnızca derleme, ancak ayrıca dağıtmanız gerektiği anlamına gelir.

### <a name="8-how-does-sorting-test-results-work-in-the-hierarchy-view"></a>8. Sıralama test sonuçlarını hiyerarşi Görünümü'nde nasıl çalışır?

  Hiyerarşi görünümü alfabetik olarak öğesine test sonucuna göre sıralar. Diğer grubun ayarlarını normalde test sonuçlarını sonucuna göre sıralama ve alfabetik olarak. Aşağıdaki görüntüde karşılaştırma için seçenekleri tarafından farklı bir gruba bakın. Tasarım hakkında geri bildirim sağlayabilirsiniz [bu GitHub sorunu içinde](https://github.com/Microsoft/vstest/issues/1425).

  ![SortingExamples](media/testex-sortingex.png)

### <a name="9-in-the-hierarchy-view-there-are-passed-failed-skipped-and-not-run-icons-next-to-the-project-namespace-and-class-groupings-what-do-these-icons-mean"></a>9. Hiyerarşi Görünümü'nde var. geçirilir, proje ve Namespace sınıfını gruplandırmaları yanındaki başarısız, atlandı ve çalıştırılmadı simgeler. Bu simgeleri ne anlama gelir?

  Proje ve Namespace sınıfını gruplandırmaları yanındaki simge, o grup içindeki testlerin durumunu yansıtır. Aşağıdaki tabloya bakın.

  ![Test Gezgini hiyerarşi simgeleri](media/testex-hierarchyicons.png)

### <a name="10-there-is-no-longer-a-file-path-filter-in-the-test-explorer-search-box"></a>10. Test Gezgini arama kutusuna artık "Dosya yolu" filtresi var.

Dosya yolu filtrede **Test Gezgini** arama kutusuna, Visual Studio 2017 sürüm 15.7 Önizleme 3 kaldırıldı. Bu özellik kullanımın düşük olduğu ve Test Gezgini, bu özellik hariç tutarak test yöntemlerini daha hızlı alabilir. Bu değişiklik, geliştirme akışınızı keser, lütfen hakkında geri bildirim göndererek bize [Geliştirici topluluğu](https://developercommunity.visualstudio.com/).

## <a name="features"></a>Özellikler

### <a name="how-can-i-turn-on-feature-flags-to-try-out-new-testing-features"></a>Yeni test özellikleri denemek için özellik bayraklarını üzerinde nasıl kapatabilir miyim?

Özellik bayrakları, ürün özellikleri resmi olarak sevk etmeden önce geri bildirim sağlamak ister misiniz kullanıcılar avid Deneysel veya tamamlanmamış bölümlerini göndermeye kullanılır. Bunlar, IDE deneyimi kararlılığını. Yalnızca güvenli geliştirme ortamlarında, sanal makineler gibi bunları kullanın. Özellik bayrakları her zaman kullanın--your-kendi-riskli ayarlarıdır. Deneysel özellikler ile etkinleştirebilirsiniz [özellik bayraklarını uzantısı](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension), veya Geliştirici komut istemi aracılığıyla.

![Özellik bayrağı uzantısı](media/testex-featureflag.png)

Visual Studio Geliştirici komut istemi üzerinden bir özellik bayrağını etkinleştirmek için aşağıdaki komutu kullanın. Yol, Visual Studio makinenizde yüklü olduğu için ve kayıt defteri anahtarı için istenen özellik bayrağını değiştirin.

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise" HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> Dword sonra 1 yerine 0 değerini kullanarak aynı komutla bayrağı kapatabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>
- [Oluşturma ve mevcut koda yönelik birim testleri çalıştırma](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
- [Birim testi kod](unit-test-your-code.md)
- [Canlı birim testi ile ilgili SSS](live-unit-testing-faq.md)
