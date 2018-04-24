---
title: DSL Kitaplığı Kullanarak DSL'ler Arasında Sınıfları Paylaşma
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: e0fffc0b370575c29c059542f859765e8af6b3f9
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>DSL Kitaplığı Kullanarak DSL'ler Arasında Sınıfları Paylaşma
İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Görselleştirme ve modelleme SDK, başka bir DSL aktarabilirsiniz tamamlanmamış bir DSL tanımı oluşturabilirsiniz. Bu, ortak bölümleri benzer modellerin faktörü sağlar.

## <a name="creating-and-using-dsl-libraries"></a>Oluşturma ve DSL kitaplıkları kullanma

#### <a name="to-create-a-dsl-library"></a>DSL kitaplığı oluşturmak için

1.  Yeni bir DSL projesi oluşturun ve DSL kitaplığı çözüm şablonu seçin.

     Tek bir DSL proje boş bir modelle oluşturulur.

2.  Etki alanı sınıfları, ilişkileri, şekiller vb. ekleyebilirsiniz.

     Öğeleri Kitaplığı'nda tek bir katıştırma ağaç form gerekmez.

     Importers kullanabileceğiniz bir ilişki tanımlamak için iki etki alanı sınıf oluşturun ve bunları arasında ilişki oluşturun.

     Ayar göz önünde bulundurun **devralma değiştiricisi** için etki alanı sınıfların `Abstract`.

3.  Bağlantı oluşturucular gibi DSL Explorer'da tanımlayan öğeleri ekleyebilirsiniz.

4.  Doğrulama kısıtlamaları gibi ek kod gerektiren özelleştirmeler ekleyebilirsiniz.

5.  Tıklatın **tüm şablonları dönüştürme**.

6.  Projeyi oluşturun.

7.  Kullanmak için diğer kişileri DSL dağıttığınızda, hem derlenmiş derleme (DLL) hem de dosya sağlamalıdır `DslDefinition.dsl`. Derlenmiş derleme altında bir klasör bulabilirsiniz `Dsl\bin\*`

#### <a name="to-import-a-dsl-library"></a>DSL kitaplığı içeri aktarmak için

1.  Başka bir DSL tanımındaki içinde **DSL Explorer**DSL kök sınıfının sağ tıklayın ve ardından **ekleme yeni DslLibrary alma**.

2.  Özellikler penceresinde ayarlayın **dosya yolu** kitaplığı. Bir göreli veya mutlak bir yol kullanabilirsiniz.

     İçeri aktarılan kitaplık salt okunur modda DSL Gezgini'nde görünür.

3.  İçeri aktarılan sınıflarını temel sınıflar olarak kullanabilirsiniz. Bir etki alanı sınıfı alma DSL oluşturun ve özellikleri penceresinde ayarlayın **temel sınıf** içeri aktarılan bir sınıfa.

4.  Tüm Şablonları dönüştürme tıklatın.

5.  DSL projeye DSL kitaplığı projenin oluşturduğu derleme (DLL) için bir başvuru ekleyin.

6.  Çözümü oluşturun.

 DSL kitaplığı diğer kitaplıkları içeri aktarabilirsiniz. Bir kitaplık içeri aktardığınızda, içeri aktarmalar DSL Explorer'da da otomatik olarak görünür.

## <a name="see-also"></a>Ayrıca Bkz.

- [Nasıl yapılır: Etki Alanına Özgü bir Dili Tanımlama](../modeling/how-to-define-a-domain-specific-language.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
