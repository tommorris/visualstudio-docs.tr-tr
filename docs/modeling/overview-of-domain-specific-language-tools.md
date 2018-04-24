---
title: Etki Alanına Özgü Dil Araçlarına Genel Bakış
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0962ee3fb780b1634438af48766f2ba086e9f4b2
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="overview-of-domain-specific-language-tools"></a>Etki Alanına Özgü Dil Araçlarına Genel Bakış
İçinde barındırılan etki alanına özgü dil Araçları (DSL araçları) [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], let bir etki alanına özgü dil tasarlama ve kullanıcıların diline dayalı modelleri oluşturmak için gereken her şeyi oluşturur.

 Aşağıdaki araçlar DSL araçlarında bulunmaktadır:

-   Etki alanına özgü dil geliştirme başlamanıza yardımcı olması için farklı çözüm şablonlar kullanır projesi Sihirbazı.

-   Oluşturma ve etki alanına özgü dil tanımınızı düzenleme için grafik Tasarımcı.

-   Etki alanına özgü dil tanımı doğru biçimlendirildiğinden ve sorunları olduğunda hataları ve uyarıları görüntüler emin olur doğrulama motoru.

-   Bir etki alanına özgü dil tanımı giriş olarak alır ve kaynak kodu çıktı olarak üretir Kod Oluşturucu.

## <a name="the-dsl-tools-solution"></a>DSL araçları çözümü
 Etki alanına özgü Designer Sihirbazı aşağıdaki çözüm şablonları sağlar:

-   Görev akışı

-   Sınıf diyagramları

-   En az bir dil

-   Bileşen modelleri

-   En az WPF

-   En az Windows.Forms

-   DSL kitaplığı

 Daha fazla bilgi için bkz: [bir etki alanına özgü dil çözüm şablonu seçme](../modeling/choosing-a-domain-specific-language-solution-template.md).

 Sihirbazın oluşturduğu bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şu projeler bulunduğu çözümü:

-   DSL

     Etki alanına özgü dil ve işlemek ve düzenleme araçları Dsl proje tanımlar.

-   **DslPackage**

     Dil araçları nasıl entegre DslPackage proje belirler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

## <a name="the-dsl-tools-graphical-interface"></a>DSL araçları grafik arabirimi
 DSL araçları grafik arabirim öğeleri ve ilişkileri, etki alanına özgü dil eklemek için kullanabilirsiniz. Öğeleri ekledikten sonra bunları şekillere eşleme renkleri özelleştirme ve dekoratörler ekleyerek görünümlerini tanımlayabilirsiniz. Araç kutusu öğelerini de ekleyebilirsiniz.

## <a name="validation-in-dsl-tools"></a>Doğrulama DSL araçları
 Bir etki alanı modeli için kod oluşturmanın temel gereksinimleri karşıladığından emin olmak için doğrulama düzeyini DSL sağlar. Genellikle, kendi etki alanına özgü dil oluşturduğunuzda, iş mantığı kurallarınızı ifade etmek için kendi doğrulama ekleyin. Özel doğrulama hakkında daha fazla bilgi için bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md).

 Bunu tasarlarken, etki alanına özgü dil genellikle doğrulamak önerilir. Etki alanına özgü dil doğrulama hatası varsa, kaynak kodu oluşturulamıyor. Şablonlardan kaynak kodu oluşturma işleminin tıklayarak gerçekleştirilen **tüm şablonları dönüştürme** Çözüm Gezgini araç. Dil tanımını değiştirmek olduğunda da emin olun **tüm şablonları dönüştürme**. Daha fazla bilgi için bkz: [nasıl yapılır: bir etki alanına özgü dil çözümü oluşturma](../modeling/how-to-create-a-domain-specific-language-solution.md).

## <a name="customization-of-dsl-tools"></a>DSL araçları özelleştirme
 Model davranışını daraltın ve dilinizi kısıtlamaları tanımlamak için ek kod sağlayabilir. Gerekirse, metin şablonlarını değiştirerek önemli değişiklikler yapabilirsiniz.

## <a name="distributing-your-dsl-solution"></a>DSL çözümünüzü dağıtma
 DSL araçları içinde barındırılan bir paket oluşturur [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Paket bir araç kutusu, DSL Gezgini ve etki alanına özgü dil kullanarak modelleri oluşturmak, kullanıcıların izin diğer UI öğelerini görüntüler.

 Ne zaman yapı ve DSL araçları çözüm Çalıştır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ikinci bir örneğini [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , etki alanına özgü dil dil kullanıcıya nasıl göründüğünü gösterir. Her şeyin doğru şekilde çalıştığını doğruladıktan sonra dağıtabilirsiniz `.vsix` dosya DslPackage proje oluşturma klasöründe bulabilirsiniz. Bu dosya DSL olarak yüklemek için kullanılan bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] diğer bilgisayarlar üzerinde uzantısı.  Daha fazla bilgi için bkz: [etki alanına özgü dil çözümleri dağıtma](../modeling/deploying-domain-specific-language-solutions.md).

## <a name="see-also"></a>Ayrıca Bkz.

- [Deneysel Örnek](../extensibility/the-experimental-instance.md)
- [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)