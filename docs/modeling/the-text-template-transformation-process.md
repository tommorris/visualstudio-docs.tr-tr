---
title: Metin Şablonu Dönüştürme Süreci
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, transformation process
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 322a8aac233f739180de903779210e1446306166
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="the-text-template-transformation-process"></a>Metin Şablonu Dönüştürme Süreci
Metin şablonu dönüştürme süreci metin şablonu dosyası giriş olarak alır ve çıktı olarak yeni bir metin dosyası oluşturur. Örneğin, Visual Basic veya C# kodu oluşturmak için metin şablonlarını kullanabilir veya bir HTML raporu oluşturabilirsiniz.

 Bu işlemde üç bileşeni ele bölümü: altyapı, ana bilgisayar ve yönerge işlemcileri. Altyapı işlemini denetler; çıktı dosyası üretmek için ana bilgisayar ve yönerge işlemcisi ile etkileşime girer. Ana bilgisayar dosyaları ve derlemeleri bulma ortamıyla herhangi bir etkileşimi sağlar. Yönerge işlemcisi bir XML dosyası veya bir veritabanından veri okumak gibi işlevlerini ekler.

 Metin şablonu dönüştürme süreci iki adımda gerçekleştirilir. İlk olarak, altyapı oluşturulan dönüşüm sınıfı olarak bilinen bir geçici sınıf oluşturur. Bu sınıf yönergeleri ve denetim blokları tarafından oluşturulan kodu içerir. Bundan sonra altyapısı derler ve çıktı dosyası üretmek için oluşturulan dönüşüm sınıfı yürütür.

## <a name="components"></a>Bileşenler

|Bileşen|Açıklama|Özelleştirilebilir (Evet/Hayır)|
|---------------|-----------------|------------------------------|
|Altyapısı|Metin şablonu dönüştürme süreci Altyapısı bileşeni denetler|Hayır.|
|Ana bilgisayar|Ana bilgisayar altyapısı ve kullanıcı ortamını arasındaki arabirimdir. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] metin dönüştürme süreci yöneticisidir.|Evet. Özel bir ana bilgisayar yazabilirsiniz.|
|Yönerge işlemcileri|Yönerge işlemcileri metin şablonlarındaki yönergeleri işlemek sınıflarıdır. Metin şablonu için bir giriş kaynağından veri sağlamak için yönergeleri kullanın.|Evet. Özel yönerge işlemcileri yazma|

## <a name="the-engine"></a>Altyapısı
 Altyapı şablonu dönüştürme işleminde kullanılan tüm dosyaları işler ana bilgisayardan bir dize olarak alır. Altyapı sonra herhangi bir özel yönerge işlemcileri ve ortam diğer yönlerini bulmak için ana sorar. Altyapı derler ve oluşturulan dönüşüm sınıfı çalıştırır. Altyapısı normal metin bir dosyaya kaydeder ana bilgisayar için oluşturulan metin döndürür.

## <a name="the-host"></a>Ana bilgisayar
 Ana bilgisayar ortamı aşağıdakiler de dahil olmak üzere dönüştürme süreci dışında ilişkili herhangi bir şey sorumludur:

-   Metin ve ikili dosyaları altyapısı veya bir yönerge işlemcisi tarafından istenen bulunuyor. Konak, dizinler ve genel derleme önbelleğinde derlemeleri bulmak için arama yapabilirsiniz. Özel yönerge işlemcisi kod altyapısı için ana bulabilir. Konak ayrıca bulun ve metin dosyalarını okuma ve içeriklerini dize olarak döndürür.

-   Standart derlemeler ve altyapısı tarafından oluşturulan dönüşüm sınıfı oluşturmak için kullanılan ad alanları listesi sağlama.

-   Altyapı derler ve oluşturulan dönüşüm sınıfı yürütür kullanılan uygulama etki alanı sağlama. Ayrı uygulama etki alanı ana bilgisayar uygulaması şablonu kod hataları korumak için kullanılır.

-   Oluşturulan çıktı dosyası yazılıyor.

-   Oluşturulan çıktı dosyası için varsayılan uzantısı ayarlama.

-   Metin şablonu dönüştürme hataları işleme. Örneğin, ana bilgisayar kullanıcı arabiriminde hataları görüntüleyin veya bunları bir dosyaya yazar. (İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], hatalar, hata ileti penceresinde görüntülenir.)

-   Bir kullanıcı bir değer sağlamadan bir yönerge olarak adlandırılan, gerekli bir parametre sağlama. Yönerge işlemcisi yönergesi ve parametre adını belirtin ve varsa, varsayılan bir değer sağlamak için konak isteyin.

## <a name="directives-and-directive-processors"></a>Yönergeleri ve yönerge işlemcileri
 Bir yönerge metin şablonunuzda bir komuttur. Oluşturma işlemi parametreleri sağlar. Genellikle kaynak ve türünü modelin veya diğer giriş ve çıkış dosyasının dosya adı uzantısı yönergeleri tanımlar.

 Bir yönerge işlemcisi, bir veya daha fazla yönergeleri işleyebilir. Bir şablon dönüştürme, şablonunuzda yönergeleri uğraşmanız bir yönerge işlemcisi yüklenmiş olması gerekir.

 Yönergeleri oluşturulan dönüşüm sınıfında kodu ekleyerek çalışır. Oluşturulan dönüşüm sınıfı oluşturduğunda, bir metin şablonu ve yönerge tüm çağrıları motoru işlemleri yönergeleri çağırın. Bir yönerge başarıyla çağrısından sonra metin şablonu yazma kodu kalan yönergesi sağlayan işlevselliğini güvenebilirsiniz. Örneğin, aşağıdaki çağrıyı yapabilir `import` şablonunuzda yönerge:

 `<#@ import namespace="System.Text" #>`

 Bu standart yönerge işlemcisi dönüştürür bir `using` oluşturulan dönüşüm sınıfı deyiminde. Daha sonra `StringBuilder` olarak niteleme olmadan şablon kodunuzu rest sınıfında `System.Text.StringBuilder`.