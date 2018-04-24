---
title: Kod Oluşturma ve T4 Metin Şablonları
ms.date: 11/04/2016
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.TextTemplating.TextTemplating
helpviewer_keywords:
- generating text
- .tt files
- code generation
- text templates
- generating code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d3864a1dbf468cbef19b5da4ca95577db59a02e6
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="code-generation-and-t4-text-templates"></a>Kod Oluşturma ve T4 Metin Şablonları
İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], *T4 metin şablonu* metin blokları ve bir metin dosyası oluşturabilirsiniz Denetim mantığı bileşimi değil. Program kodunda parçalarını olarak Denetim mantığı yazılır [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. Visual Studio 2015 güncelleştirme 2 ve daha sonra T4 şablonları yönergeleri C# sürüm 6.0 özelliklerini kullanabilirsiniz. Oluşturulan dosyanın bir Web sayfası veya bir kaynak dosya veya program herhangi bir dilde kaynak kodu gibi herhangi bir türde metin olabilir.

 T4 metin şablonları iki tür vardır:

 **Çalıştırma zamanı T4 metin şablonları** ('şablonları ön işlemesi yapılan') metin dizelerini çıktısını bir parçası olarak genellikle üretmek için uygulamanızda yürütüldüğünde.
Örneğin, bir HTML sayfası tanımlamak için bir şablon oluşturabilirsiniz:

```
<html><body>
 The date and time now is: <#= DateTime.Now #>
</body></html>
```

 Şablon oluşturulan çıktı benzer dikkat edin. Sonuçta çıktı şablona benzerlik değiştirmek istediğinizde hataları önlemenize yardımcı olur.

 Ayrıca, şablon program kod parçalarını içerir. Metin, koşullu bölümleri olmak ve uygulamanızı verilerini gösterecek biçimde bölümlerini yinelemek için bu parçasının kullanabilirsiniz.

 Çıktı üretmek için uygulamanızı şablon tarafından oluşturulan bir işlevi çağırır. Örneğin:

```csharp
string webResponseText = new MyTemplate().TransformText();

```

 Uygulamanızı sahip olmayan bir bilgisayarda çalıştırabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklü.

 Bir çalışma zamanı şablonu oluşturmak için Ekle bir **Preprocessed metin şablonu** projenize dosya. Alternatif olarak, düz metin dosyası ekleyin ve ayarlayın, **özel araç** özelliğine **TextTemplatingFilePreprocessor**.

 Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md). Şablon söz dizimi hakkında daha fazla bilgi için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).

 **Tasarım zamanı T4 metin şablonları** yürütülür [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kaynak kodun bir parçası ve uygulamanızın diğer kaynakları tanımlamak için.
Genellikle, tek girdi dosyası veya veritabanında veri okuma çeşitli şablonlar kullanın ve bazı oluşturur, `.cs`, `.vb`, veya diğer kaynak dosyaları. Her şablon bir dosya oluşturur. İçinde yürütülen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].

 Örneğin, giriş verilerinizi yapılandırma verilerini bir XML dosyası olabilir. Metin şablonları, geliştirme sırasında XML dosyasını düzenlediğinizde, uygulama kod parçası, yeniden. Aşağıdaki örnek şablonlarından birini benzer:

```
<#@ output extension=".txt" #>
<#@ assembly name="System.Xml" #>
<#
 System.Xml.XmlDocument configurationData = ...; // Read a data file here.
#>
namespace Fabrikam.<#= configurationData.SelectSingleNode("jobName").Value #>
{
  ... // More code here.
}

```

 Oluşturulan XML dosyasını değerlerde bağımlı `.cs` dosya aşağıdaki benzer:

```
namespace Fabrikam.FirstJob
{
  ... // More code here.
}
```

 Başka bir örnek olarak, bir iş etkinliği iş akışı diyagramı giriş olabilir. Kullanıcılar kendi iş akışı değiştirdiğinizde ya da farklı bir iş akışı yeni kullanıcılar ile iş başlattığınızda, yeni modeline uyacak şekilde kodu yeniden oluşturmak kolaydır.

 Tasarım zamanı şablonları daha hızlı ve daha güvenilir gereksinimleri değiştiğinde yapılandırmasını değiştirmek için kolaylaştırır. Giriş iş akışı örnekte olduğu gibi iş gereksinimleri açısından tanımlanır. Bu, Kullanıcılarınızla değişiklikleri tartışmak kolaylaştırır. Tasarım zamanı bu nedenle bir Çevik geliştirme işleminde yararlı bir aracı şablonlarıdır.

 Tasarım zamanı şablonu oluşturmak için Ekle bir **metin şablonu** projenize dosya. Alternatif olarak, düz metin dosyası ekleyin ve ayarlayın, **özel araç** özelliğine **TextTemplatingFileGenerator**.

 Daha fazla bilgi için bkz: [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md). Şablon söz dizimi hakkında daha fazla bilgi için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).

> [!NOTE]
>  Terim *modeli* bazen bir veya daha fazla şablonları tarafından okunan veriler açıklamak için kullanılır. Model, herhangi bir dosya veya veritabanı biçimi olabilir. UML modelini veya bir etki alanına özgü dil modeli yok. 'Model' yalnızca veri kod benzeyen yerine iş kavramları şartlarında tanımlanabilir gösterir.

 Metin şablonu dönüştürme özelliği adlı *T4*.

## <a name="in-this-section"></a>Bu Bölümde
 [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md) metin tanımlamanın kolay ve güvenilir bir yöntem metin dosyaları oluşturan herhangi bir uygulama, önceden derlenmiş metin şablonlarıdır. Ancak, bu yöntem, çalışma zamanında değiştirme metin şablonları için kullanılamaz.

 [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md) oluşturma kod ve diğer kaynakları modelden sağlar, uygulamanız tarafından modeli güncelleştirmek.

 [Kod derleme sürecinde oluşturma](../modeling/code-generation-in-a-build-process.md) yüklediyseniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Görselleştirme ve modelleme SDK, sağlamak oluşturulan yazılım tutar değişikliklerle güncel modelde.

 [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md) metin şablonu dosyasının söz dizimi.

 [İzlenecek yol: Metin şablonları kullanarak kod oluşturma](../modeling/walkthrough-generating-code-by-using-text-templates.md) kod oluşturma kullanmanın tek yolu Tanıtımı.

 [T4 metin şablonuna ilişkin hata ayıklama](../modeling/debugging-a-t4-text-template.md) metin şablonları ve bazı genel metin şablonu hatalarını ayıklamak üzere nasıl.

 [TextTransform yardımcı programı ile dosyalar oluşturma](../modeling/generating-files-with-the-texttransform-utility.md) metin şablonu dönüştürme çalıştırmak için kullanabileceğiniz komut satırı aracı.

 [T4 metin dönüştürmeyi özelleştirme](../modeling/customizing-t4-text-transformation.md) yönerge işlemcileri ve kendi veri kaynakları için özel şablon konaklar Yaz nasıl.

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki Alanına Özgü Dilden Kod Oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)