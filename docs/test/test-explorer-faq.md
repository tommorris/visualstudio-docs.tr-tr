---
title: Test Gezgini ile ilgili SSS | Microsoft Docs
ms.date: 1/15/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
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
ms.openlocfilehash: fd64bb3bce6b6477c0db1c7d0c5a15e518ae71ef
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="visual-studio-test-explorer-faq"></a>Visual Studio Test Gezgini ile ilgili SSS

## <a name="test-discovery"></a>Test bulma

### <a name="1-the-test-explorer-is-not-discovering-my-tests-that-have-theories-custom-adapters-custom-traits-use-ifdefs-or-are-dynamically-defined-how-can-i-discover-these-tests"></a>1. Test Gezgini kuramlarý, özel bağdaştırıcılar, özel özellikleri, kullanım #ifdefs veya dinamik olarak tanımlanan my test bulunurken değil. Bu testler nasıl bulabilmesi için?

  Projenizi derleme ve derleme tabanlı bulma içinde açık olduğundan emin olun **Araçlar > Seçenekler > Test**.

  [Gerçek zamanlı Test bulma](https://go.microsoft.com/fwlink/?linkid=862824), kaynak dayalı test bulma olduğu kullanan kuramlarý, özel bağdaştırıcıları, özel nitelikler testleri Bul olamaz `#ifdef` deyimleri veya diğer herhangi bir yolla tanımlanmış dinamik olarak. Derleme, bu testler doğru şekilde bulunmak gereklidir. 15.6 önizlemelerde derleme tabanlı bulma (Geleneksel discoverer) yalnızca derlemeleri sonra çalışır. Gerçek zamanlı Test bulma bulur, while gibi sayıda testleri yani düzenlemekte olduğunuz ve derleme tabanlı bulma derleme sonrası görünmesi kuramlarý (veya dinamik olarak tanımlanan tüm testlerin) sağlar. Gerçek zamanlı Test bulma yanıt hızını artırır, ancak durağan derleme sonrası eksiksiz ve doğru sonuçlar almak izin verir.

### <a name="2-what-does-the--plus-symbol-that-appears-in-the-top-line-of-test-explorer-mean"></a>2. Ne yaptığını '+' (artı) Test Gezgini ortalama ilk satırda görünen simgesini?

  '+' (Artı) simgesi gösterir derleme tabanlı bulma açıksa, daha fazla test derleme sonrası bulunan. Bu dinamik olarak tanımlanmışsa testleri projenizde algılanan görünecektir.

  ![Artı özet satırı simgesi](media/testex-plussymbol.png)

### <a name="3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on"></a>3. Derleme tabanlı bulma için proje artık çalışmıyor. Nasıl onu kapatırım geri?

  Gidin **Araçlar > Seçenekler > Test** ve için kutuyu **ayrıca derlemelerden sonra derlemeleri yerleşik testleri bulma.**

  ![Derleme seçeneği](media/testex-toolsoptions.png)

### <a name="4-tests-now-appear-in-test-explorer-while-i-type-without-having-to-build-my-project-what-changed"></a>4. I proje oluşturmanıza gerek kalmadan, yazarken testlerin artık Test Gezgini görüntülenir. Neler değişti mi?

  Bu özellik adında [gerçek zamanlı Test bulma](https://go.microsoft.com/fwlink/?linkid=862824). Testleri bulmak ve projenizin oluşturmaya gerek kalmadan gerçek zamanlı olarak Test Gezgini doldurmak için bir .NET Complier Platformu ("Roslyn") Çözümleyicisi kullanır. SSS #1 kuramlarý veya özel nitelikler gibi dinamik olarak tanımlanan testler için test bulma davranış hakkında daha fazla bilgi için bkz.

### <a name="5-what-languages-and-test-frameworks-can-use-real-time-test-discovery"></a>5. Hangi dilleri ve test çerçevelerini gerçek zamanlı Test bulma kullanabilir miyim?

  [Gerçek zamanlı Test bulma](https://go.microsoft.com/fwlink/?linkid=862824) yalnızca yönetilen dilleri (C# ve Visual Basic), bu yana çalışan .NET ("Roslyn") derleyici kullanılarak oluşturulur. Şimdilik, gerçek zamanlı Test bulma yalnızca xUnit, NUnit ve mstest'i çerçeveleri çalışır.

## <a name="features"></a>Özellikler

### <a name="how-can-i-turn-on-feature-flags-to-try-out-new-testing-features"></a>Yeni test özellikleri denemek için özellik bayrakları üzerinde nasıl kapatabilir miyim?

Özellik bayrakları ürün özellikleri resmi olarak sevk önce geribildirim vermek istediğiniz hırslı kullanıcılara Deneysel veya tamamlanmamış bölümlerini sevk etmek için kullanılır. Bunlar, IDE deneyimi kararlılığını. Bunları yalnızca güvenli geliştirme ortamlarında, sanal makineleri gibi kullanılması önerilir. Özellik bayrakları her zaman kullanın--bilgisayarınızı-kendi-riskli ayarlardır. Deneysel özellikleri açabilirsiniz [özellik bayrakları uzantısı](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension), veya Geliştirici komut istemi üzerinden.

![Özelliği bayrak uzantısı](media/testex-featureflag.png)

Visual Studio Geliştirici komut istemi üzerinden özellik bayrağı etkinleştirmek için aşağıdaki komutu kullanın. Visual Studio makinenizde yüklendiği için yolu değiştirin ve istenen özellik bayrağı kayıt defteri anahtarını değiştirin.

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise” HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> Aynı komutu bayrağıyla sonra dword 1 yerine 0 değerini kullanarak devre dışı bırakabilirsiniz.
  
## <a name="see-also"></a>Ayrıca bkz.

<xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>  
[Oluşturma ve var olan kod için birim testleri çalıştırma](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
[birim testi kodunuzu](unit-test-your-code.md)
[Canlı birim testi ile ilgili SSS](live-unit-testing-faq.md)
