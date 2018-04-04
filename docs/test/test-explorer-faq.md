---
title: Visual Studio Test Gezgini ile ilgili SSS | Microsoft Docs
ms.date: 1/15/2018
ms.technology: vs-ide-test
ms.topic: article
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
manager: ghogen
ms.openlocfilehash: 9e64528b6b0669a0403188b540a90e9b921bfb34
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="visual-studio-test-explorer-faq"></a>Visual Studio Test Gezgini ile ilgili SSS

## <a name="test-discovery"></a>Test bulma

### <a name="1-the-test-explorer-is-not-discovering-my-tests-that-are-dynamically-defined-for-example-theories-custom-adapters-custom-traits-ifdefs-etc-how-can-i-discover-these-tests"></a>1. Test Gezgini dinamik olarak tanımlanan my test bulunurken değil. (Örneğin, kuramlarý, özel bağdaştırıcılar, özel özellikleri, #ifdefs, vb.) Bu testler nasıl bulabilmesi için?

  Projenizi derleme ve derleme tabanlı bulma içinde açık olduğundan emin olun **Araçlar > Seçenekler > Test**.

  [Gerçek zamanlı Test bulma](https://go.microsoft.com/fwlink/?linkid=862824) kaynak dayalı test keşfi'dir. Kullanan kuramlarý, özel bağdaştırıcıları, özel nitelikler testleri bulamaz `#ifdef` deyimleri, çalışma zamanında tanımlandığından vb. Derleme, bu testler doğru şekilde bulunmak gereklidir. 15.6 önizlemelerde derleme tabanlı bulma (Geleneksel discoverer) yalnızca derlemeleri sonra çalışır. Bu ayar, gerçek zamanlı Test bulma bulur, while gibi sayıda testleri gelir düzenlemekte olduğunuz ve derleme tabanlı bulma dinamik olarak tanımlanan testleri derleme sonrası görünmesini sağlar. Gerçek zamanlı Test bulma yanıt hızını artırır, ancak durağan derleme sonrası eksiksiz ve doğru sonuçlar almak izin verir.

### <a name="2-what-does-the--plus-symbol-that-appears-in-the-top-line-of-test-explorer-mean"></a>2. Ne yaptığını '+' (artı) Test Gezgini ortalama ilk satırda görünen simgesini?

  '+' (Artı) simgesi gösterir derleme tabanlı bulma açık olduğu sürece, daha fazla test derleme sonrası bulunan. Dinamik olarak tanımlanmışsa testleri projenizde algılanan görünür.

  ![Artı özet satırı simgesi](media/testex-plussymbol.png)

### <a name="3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on"></a>3. Derleme tabanlı bulma için proje artık çalışmıyor. Nasıl onu kapatırım geri?

  Gidin **Araçlar > Seçenekler > Test** ve için kutuyu **ayrıca testleri yerleşik derlemelerden sonra derlemeleri bulmak.**

  ![Derleme seçeneği](media/testex-toolsoptions.png)

### <a name="4-tests-now-appear-in-test-explorer-while-i-type-without-having-to-build-my-project-what-changed"></a>4. I proje oluşturmanıza gerek kalmadan, yazarken testlerin artık Test Gezgini görüntülenir. Neler değişti mi?

  Bu özellik adında [gerçek zamanlı Test bulma](https://go.microsoft.com/fwlink/?linkid=862824). Testleri bulmak ve projenizin oluşturmaya gerek kalmadan gerçek zamanlı olarak Test Gezgini doldurmak için bir Roslyn Çözümleyicisi kullanır. SSS #1 kuramlarý veya özel nitelikler gibi dinamik olarak tanımlanan testler için test bulma davranış hakkında daha fazla bilgi için bkz.

### <a name="5-what-languages-and-test-frameworks-can-use-real-time-test-discovery"></a>5. Hangi dilleri ve test çerçevelerini gerçek zamanlı Test bulma kullanabilir miyim?

  [Gerçek zamanlı Test bulma](https://go.microsoft.com/fwlink/?linkid=862824) yalnızca yönetilen dilleri (C# ve Visual Basic), bu yana çalışan Roslyn derleyici kullanılarak oluşturulur. Şimdilik, gerçek zamanlı Test bulma yalnızca xUnit, NUnit ve mstest'i çerçeveleri çalışır.

### <a name="6-how-can-i-turn-on-logs-for-the-test-explorer"></a>6. Test Gezgini için nasıl açtığında kapatırım?

  Gidin **Araçlar > Seçenekler > Test** ve günlüğe kaydetme bölümü bulun.

### <a name="7-why-are-my-tests-in-uwp-projects-not-discovered-until-i-deploy-my-app"></a>7. Neden Uygulamam dağıtıncaya kadar bulunmayan UWP projeleri my testlerinde misiniz?

  Uygulama dağıtıldığında UWP testleri farklı bir çalışma zamanı hedefleyin. Bu testler UWP projeleri için doğru bir şekilde bulmak için yalnızca projenizi oluşturun, ancak aynı zamanda dağıtmak gerektiği anlamına gelir.

### <a name="8-how-does-sorting-test-results-work-in-the-hierarchy-view"></a>8. Sıralama test sonuçlarını hiyerarşi görünümünde nasıl çalışır?

  Hiyerarşi görünüm testlere göre alfabetik olarak tersine sonuçlara göre sıralar. Bir grubu ayarları tarafından sonuçlara göre normalde test sonuçlarını sıralama ve ardından alfabetik olarak. Karşılaştırma için aşağıdaki görüntüde seçenekleri tarafından farklı grup bakın. Tasarım hakkında geri bildirim sağlayabilirsiniz [bu GitHub sayıda](https://github.com/Microsoft/vstest/issues/1425).

  ![SortingExamples](media/testex-sortingex.png)

### <a name="9-in-the-hierarchy-view-there-are-passed-failed-skipped-and-not-run-icons-next-to-the-project-namespace-and-class-groupings-what-do-these-icons-mean"></a>9. Hiyerarşi görünümünde var. geçirilir, proje, Namespace ve sınıf gruplandırmaları yanındaki başarısız, atlandı ve çalışmadı simgeler. Bu simgeleri ne anlama geliyor?

  Proje, Namespace ve sınıf gruplandırmaları yanındaki simge, gruplandırma testlerde durumunu yansıtır. Aşağıdaki tabloya bakın.

  ![Test Gezgini hiyerarşi simgeler](media/testex-hierarchyicons.png)
  
### <a name="10-there-is-no-longer-a-file-path-filter-in-the-test-explorer-search-box"></a>10. Test Gezgini arama kutusuna artık "Dosya yolu" filtre var.

Dosya yolu filtrede **Test Gezgini** arama kutusuna, Visual Studio 2017 sürüm 15.7 preview 3 kaldırıldı. Bu özellik düşük kullanımı var ve bu özellik hariç tutarak, test yöntemleri daha hızlı Test Gezgini alabilirsiniz. Bu değişiklik, geliştirme akışınızı keser, lütfen bize geri bildirim gönderme tarafından bildirin [Geliştirici topluluğu](https://developercommunity.visualstudio.com/).

## <a name="features"></a>Özellikler

### <a name="how-can-i-turn-on-feature-flags-to-try-out-new-testing-features"></a>Yeni test özellikleri denemek için özellik bayrakları üzerinde nasıl kapatabilir miyim?

Özellik bayrakları ürün özellikleri resmi olarak sevk önce geribildirim vermek istediğiniz hırslı kullanıcılara Deneysel veya tamamlanmamış bölümlerini sevk etmek için kullanılır. Bunlar, IDE deneyimi kararlılığını. Bunları yalnızca güvenli geliştirme ortamlarında, sanal makineleri gibi kullanın. Özellik bayrakları her zaman kullanın--bilgisayarınızı-kendi-riskli ayarlardır. Deneysel özellikleri açabilirsiniz [özellik bayrakları uzantısı](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension), veya Geliştirici komut istemi üzerinden.

![Özelliği bayrak uzantısı](media/testex-featureflag.png)

Visual Studio Geliştirici komut istemi üzerinden özellik bayrağı etkinleştirmek için aşağıdaki komutu kullanın. Visual Studio makinenizde yüklendiği için yolu değiştirin ve istenen özellik bayrağı kayıt defteri anahtarını değiştirin.

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise” HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> Aynı komutu bayrağıyla sonra dword 1 yerine 0 değerini kullanarak devre dışı bırakabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>
- [Oluşturma ve var olan kod için birim testleri çalıştırma](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
- [Kodunuza Birim Testi Uygulama](unit-test-your-code.md)
- [Live Unit Testing SSS](live-unit-testing-faq.md)
