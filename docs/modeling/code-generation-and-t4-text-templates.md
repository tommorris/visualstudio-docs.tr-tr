---
title: Kod Oluşturma ve T4 Metin Şablonları
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 2f4fed2cbf00717e4eaf9c1353370dbd96037491
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32425507"
---
# <a name="code-generation-and-t4-text-templates"></a>Kod Oluşturma ve T4 Metin Şablonları

Visual Studio'da bir *T4 metin şablonu* metin blokları ve bir metin dosyası oluşturabilirsiniz Denetim mantığı bileşimi değil. Program kodunda parçalarını olarak Denetim mantığı yazılır [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. Visual Studio 2015 güncelleştirme 2 ve daha sonra T4 şablonları yönergeleri C# sürüm 6.0 özelliklerini kullanabilirsiniz. Oluşturulan dosyanın bir Web sayfası veya bir kaynak dosya veya program herhangi bir dilde kaynak kodu gibi herhangi bir türde metin olabilir.

T4 metin şablonları iki tür vardır: zamanı hem tasarım zamanı çalıştırın.

## <a name="run-time-t4-text-templates"></a>Çalıştırma zamanı T4 metin şablonları

Olarak da bilinen metin dizelerini çıktısını bir parçası olarak genellikle üretmek için uygulamanızda zamanı şablonları Çalıştır 'önceden işlenmiş' şablonları yürütülür. Örneğin, bir HTML sayfası tanımlamak için bir şablon oluşturabilirsiniz:

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

Uygulamanızı Visual Studio yüklü olmayan bir bilgisayarda çalıştırabilirsiniz.

Bir çalışma zamanı şablonu oluşturmak için Ekle bir **Preprocessed metin şablonu** projenize dosya. Alternatif olarak, düz metin dosyası ekleyin ve ayarlayın, **özel araç** özelliğine **TextTemplatingFilePreprocessor**.

Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md). Şablon söz dizimi hakkında daha fazla bilgi için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).

## <a name="design-time-t4-text-templates"></a>Tasarım zamanı T4 metin şablonları

Tasarım zamanı tempaltes kaynak kodun bir parçası ve diğer kaynakları, uygulamanızın tanımlayın. Genellikle, bir tek girdi dosyası veya veritabanı verileri okuma çeşitli şablonlar kullanın ve bazı oluşturur, *.cs*, *.vb*, veya diğer kaynak dosyaları. Her şablon bir dosya oluşturur. Bunlar, Visual Studio veya MSBuild içinde yürütülür.

Örneğin, giriş verilerinizi yapılandırma verilerini bir XML dosyası olabilir. XML dosyasını geliştirme sırasında düzenlediğinizde, metin şablonları uygulama kod parçası, yeniden oluşturun. Aşağıdaki örnek şablonlarından birini benzer:

```
<#@ output extension=".cs" #>
<#@ assembly name="System.Xml" #>
<#
 System.Xml.XmlDocument configurationData = ...; // Read a data file here.
#>
namespace Fabrikam.<#= configurationData.SelectSingleNode("jobName").Value #>
{
  ... // More code here.
}
```

Oluşturulan XML dosyasını değerlerde bağlı olarak *.cs* dosya aşağıdaki benzer:

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
> Terim *modeli* bazen bir veya daha fazla şablonları tarafından okunan veriler açıklamak için kullanılır. Model, herhangi bir dosya veya veritabanı biçimi olabilir. UML modelini veya bir etki alanına özgü dil modeli yok. 'Model' yalnızca veri kod benzeyen yerine iş kavramları şartlarında tanımlanabilir gösterir.

Metin şablonu dönüştürme özelliği adlı *T4*.

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki Alanına Özgü Dilden Kod Oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)