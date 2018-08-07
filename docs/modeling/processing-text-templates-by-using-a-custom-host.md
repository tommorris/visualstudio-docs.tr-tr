---
title: Bir Özel Konak kullanarak Metin Şablonlarını İşleme
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e4546c75f424f5091a22e9acd6cceb72f5d8038c
ms.sourcegitcommit: ef828606e9758c7a42a2f0f777c57b2d39041ac3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39567096"
---
# <a name="process-text-templates-by-using-a-custom-host"></a>Özel bir Konak kullanarak Metin Şablonlarını İşleme

*Metin şablonu dönüştürme* işlem alır bir *metin şablonu* dosyası olarak girdi ve çıktı olarak bir metin dosyası oluşturur. Metin dönüştürme altyapısı çağırabilirsiniz bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı, veya bir makine üzerinde çalışan bir tek başına uygulamasından [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklenir. Ancak, sağlamanız gereken bir *metin şablonu oluşturma barındırıcısı*. Bu sınıf, derlemeler ve ekleme dosyaları gibi kaynakları bularak ve çıktı ve hata iletilerini işleme alarak şablonu ortama bağlar.

> [!TIP]
> Bir paket ya da içinde çalışacak uzantısı yazıyorsanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], kendi ana bilgisayarınızı yazmak yerine metin şablonu oluşturma hizmetini kullanmayı düşünün. Daha fazla bilgi için [bir VS uzantısında metin dönüştürmeyi çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md).

> [!NOTE]
> Metin şablonu dönüştürmelerinin sunucu uygulamalarında kullanılması önerilmez. Metin şablonu dönüştürmelerinin tek bir iş parçacığı dışında kullanılması önerilmez. Bunun nedeni, metin şablonu oluşturma motorunun şablonları çevirmek, derlemek ve yürütmek için tek bir AppDomain öğesini yeniden kullanmasıdır. Çevrilen kod, iş parçacığı açısından güvenli olmak üzere tasarlanmamıştır. Altyapı olduğu gibi seri olarak, dosyalarını işlemek için tasarlanmış bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesinde tasarım zamanında.
>
> Çalışma zamanı uygulamaları için önceden işlenmiş metin şablonlarını kullanmayı: bkz [T4 metin şablonları ile çalışma süresi metni oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).

Uygulamanız, derleme zamanında sabitlenmiş bir grup şablon kullanıyorsa, Önceden İşlenmiş Metin Şablonlarının kullanılması daha kolaydır. Uygulamanızı bir makine üzerinde çalıştırılacaksa da bu yaklaşımı kullanabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklü değil. Daha fazla bilgi için [T4 metin şablonları ile çalışma süresi metni oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).

## <a name="execute-a-text-template-in-your-application"></a>Uygulamanızda metin şablonu yürütme

Bir metin şablonu yürütmek için ProcessTemplate yöntemini çağırırsınız <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>:

```csharp
using Microsoft.VisualStudio.TextTemplating;
...
Engine engine = new Engine();
string output = engine.ProcessTemplate(templateString, host);
```

 Uygulamanızın şablonu bularak sağlaması ve çıktı ile işlem yapması gerekir. 

 İçinde `host` parametresi uygulayan bir sınıf sağlamanız gerekir <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Bu, Motor tarafından geri çağrılır.

 Ana bilgisayar hataları günlüğe kaydedebilmeli, derleme ve ekleme dosyalarına yapılan başvuruları çözümleyebilmeli, şablonun yürütülebileceği bir Uygulama Etki Alanı sağlayabilmeli ve her yönerge için uygun işlemciyi çağırabilmelidir.

 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> tanımlanan **Microsoft.VisualStudio.TextTemplating.\*. 0. dll**, ve <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> tanımlanan **Microsoft.VisualStudio.TextTemplating.Interfaces.\*. 0. dll**.

## <a name="in-this-section"></a>Bu Bölümde
 [İzlenecek yol: bir özel metin şablonu konağı oluşturma](../modeling/walkthrough-creating-a-custom-text-template-host.md) metin şablon işlevi dışında kullanılabilir hale getiren bir özel metin şablonu konağı oluşturma işlemi gösterilmektedir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

## <a name="reference"></a>Başvuru
 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>

## <a name="related-sections"></a>İlgili Bölümler

- [Metin şablonu dönüştürme süreci](../modeling/the-text-template-transformation-process.md) metin dönüştürmenin nasıl çalıştığını açıklar ve hangi kısımları özelleştirebilirsiniz.
- [Özel T4 metin şablonu yönerge işlemcileri oluşturma](../modeling/creating-custom-t4-text-template-directive-processors.md) şablonu yönerge işlemcileri metin genel bir bakış sağlar.