---
title: Mimarinizi çözümleme ve mimarinizin modelini oluşturma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, exploring code
- Visual Studio Ultimate, visualizing code
- diagrams - modeling
- Visual Studio ALM, modeling
- application, design
- architecture
- code visualization
- application design
- applications, architecture
- code exploration
- Visual Studio ALM, exploring code
- modeling
- application architecture
- application, modeling
- applications, modeling
- architecture [Visual Studio ALM], modeling
- application modeling
- Visual Studio Ultimate, modeling
- architecture [Visual Studio Ultimate], modeling
- application, architecture
- Visual Studio ALM, visualizing code
- applications, designing
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be58a86ec6c3b87954ff5b5be012ce636ad52204
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106966"
---
# <a name="analyze-and-model-your-architecture"></a>Mimarinizi çözümleme ve mimarinizin modelini oluşturma
Visual Studio mimari kullanarak ve modelleme tasarımı ve uygulamanızı model araçları uygulamanızı mimari gereksinimleri karşıladığından emin olun.

* Varolan program kodunun daha kolay kodun yapısı, davranış ve ilişkileri görselleştirmek için Visual Studio kullanarak anlayın.

* Ekibinizin mimari bağımlılıkları saygı göstermek için gerekli bilgilendirin.

* Geliştirme sürecinin bir parçası olarak uygulama yaşam döngüsü boyunca ayrıntı farklı düzeylerde modelleri oluşturun.

Bkz: [senaryo: Görselleştirme ve modelleme kullanarak tasarımınızı değiştirme](../modeling/scenario-change-your-design-using-visualization-and-modeling.md).

## <a name="to"></a>Bitiş

|||
|-|-|
|**Kodu görselleştirme**:<br /><br /> -Kod haritaları oluşturarak kodun kuruluş ve ilişkileri bakın. Derlemeler, ad alanları, sınıflar, yöntemleri ve benzeri arasındaki bağımlılıkları görselleştirin.<br />-Sınıf diyagramları koddan oluşturarak sınıf yapısı ve belirli bir projenin üyeleri bakın.<br />-Kodunuzu ve tasarımı arasındaki çakışmaları kodunu doğrulamak için bağımlılık diyagramları oluşturarak bulun.|-   [Kodu görselleştirme](../modeling/visualize-code.md)<br />-   [Sınıfları ve diğer türleri (Sınıf Tasarımcısı) ile çalışma](../ide/working-with-classes-and-other-types-class-designer.md)<br />-   [Video: Visual Studio 2015 kod haritalarını koduyla tasarımdan anlama](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2015/502)<br />-   [Video: mimarisi bağımlılıklarınızı gerçek zamanlı doğrula](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)|
|**Mimariyi tanımlayın**:<br /><br /> -Tanımlama ve bağımlılık diyagramları oluşturarak kodunuzun bileşenleri arasındaki bağımlılıkları kısıtlamaları zorlayın.|-   [Video: Visual Studio (Channel 9) mimarisi bağımlılıklarla doğrula](https://channel9.msdn.com/Events/Connect/2016/170)|
|**Sisteminiz gereksinimleri ile doğrulamak ve yönelik tasarım:**<br /><br /> -Hedeflenen mimariyi açıklamakta bağımlılık diyagramları ile kod bağımlılıklarını doğrulayın ve tasarım ile çakışabilir Değişliklerini.|-   [Video: Visual Studio (Channel 9) mimarisi bağımlılıklarla doğrula](https://channel9.msdn.com/Events/Connect/2016/170)|
|**Modelleri ve diyagramları özelleştirme**:<br /><br /> -Kendi etki alanına özgü dil oluşturun.|-   [Visual Studio - etki alanına özgü dil SDK Modelleme](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|
|**T4 şablonları kullanarak metin oluşturan**:<br /><br /> -Metin tabanlı dosyaları oluşturmak için metin blokları ve şablonlar içindeki Denetim mantığı kullanın.<br /> -Visual Studio'da bulunan MSBuild ile T4 şablon oluşturma|-   [Kod oluşturma ve T4 metin şablonları](../modeling/code-generation-and-t4-text-templates.md)|
|**Paylaşımı modelleri, diyagramları ve Team Foundation sürüm denetimini kullanarak kod haritalarını**:<br /><br /> -Kod haritalarını, projeler ve Team Foundation sürüm denetimi altındaki bağımlılık diyagramları put bunları paylaşabilmek için.| |

Visual Studio hangi sürümlerinin her özelliğini desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)

## <a name="types-of-models-and-typical-uses"></a>Model türleri ve tipik kullanır

### <a name="code-maps"></a>Kod haritaları
Kod kodunuzda organizasyon ve ilişkiler gördüğünüz Yardım eşler.

**Tipik kullanır:**

-   Program kodunu İnceleme yapısı ve bağımlılıklarını daha iyi anlamak için önerilen değişiklikleri güncelleştirin ve maliyetini tahmin etme.

**Bkz.:**

-   [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)
-   [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)
-   [Kod haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)

### <a name="dependency-diagram"></a>Bağımlılık diyagramı
Bağımlılık diyagramları, açık bağımlılıkları sahip Katmanlar veya bloklar kümesi olarak uygulama yapısını tanımlamanıza olanak sağlar. Koddaki bağımlılıkları ve bir bağımlılık diyagramda açıklanan bağımlılıkları arasındaki çakışmaları bulmak için doğrulama çalıştırabilirsiniz.

**Tipik kullanır:**

-   Çok sayıda değişikliği üzerinden uygulama yapısını, kullanım ömrü boyunca Sabitle.
-   Kod değişiklikleri denetlemeden önce istenmeyen bağımlılık çakışmaları keşfedin.

**Bkz.:**

-   [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)
-   [Bağımlılık Diyagramları: Başvuru](../modeling/layer-diagrams-reference.md)
-   [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)

### <a name="domain-specific-language-dsl"></a>Etki alanına özgü dil (DSL)
DSL belirli bir amaca yönelik tasarım bir gösterimidir. Visual Studio'da genellikle grafik.

**Tipik kullanır:**

-   Oluşturmak veya uygulama bölümlerinin yapılandırın. İş gösterimi ve araçlar geliştirilmesi için gereklidir. Etki alanınız için daha iyi bir uyum bir UML özelleştirme daha sonucu olabilir.
-   Büyük projeler veya ürün hatları burada DSL ve araçlarını geliştirmeye yatırım tarafından döndürülen birden fazla proje kullanımı.

**Bkz.:**

-   [Visual Studio için Modelleme SDK'sı - Etki Alanına Özgü Diller](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)

## <a name="where-can-i-get-more-information"></a>Daha fazla bilgiyi nereden bulabilirim?

[Visual Studio Görselleştirme ve Modelleme Araçları Forumu](http://go.microsoft.com/fwlink/?LinkId=184720)

## <a name="see-also"></a>Ayrıca bkz.

- [Yenilikler](../modeling/what-s-new-for-design-in-visual-studio.md)
- [DevOps ve uygulama yaşam döngüsü yönetimi](http://msdn.microsoft.com/Library/74a1f71d-7f23-4c71-8fd7-89ede614fab6)
