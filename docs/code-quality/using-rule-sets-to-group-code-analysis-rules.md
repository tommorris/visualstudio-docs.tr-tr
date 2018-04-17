---
title: Kod çözümleme kural kümesi Visual Studio'da | Microsoft Docs
ms.date: 04/02/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b8db113ef3e86fce0a3359a98a7641c47b67ae0c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>Kod çözümleme kurallarını gruplandırmak için kullanım kural kümesi

Visual Studio'da Kod Analizi yapılandırdığınızda, yerleşik listesinden seçebilirsiniz *kural kümeleri*. Bir kural kümesi bir proje için de geçerlidir ve kod hedeflenen sorunlar ve bu proje için belirli koşullar tanımlamak çözümleme kurallarını grubudur. Örneğin, genel kullanıma açık API'ler kodu taramak için tasarlanmış bir kural kümesi uygulayabilir veya kuralları yalnızca en düşük önerilir. Tüm kuralları içeren bir kural kümesi de uygulayabilirsiniz.

Bir kural uyarı veya hata olarak görünmesi ekleyerek veya silerek kuralları ya da kural önem derecelerine değiştirerek kümesini özelleştirebilirsiniz **hata listesi**. Özelleştirilmiş kural kümeleri belirli geliştirme ortamınızı gereksinimini karşılayabilir. Bir kural kümesi özelleştirdiğinizde, kural kümesi Düzenleyici arama ve filtreleme süreçte yardımcı olacak araçlar sağlar.

## <a name="rule-set-format"></a>Kural kümesi biçimi

Bir kural kümesi XML biçiminde belirtilen bir *.ruleset* dosya. Kimliği oluşur kuralları ve bir *eylem*, Çözümleyicisi kimliği ve ad alanı dosyasındaki göre gruplandırılır.

XML içeriğini bir *.ruleset* dosyası şuna benzer görünür:

```xml
<RuleSet Name="Rules for Hello World project" Description="These rules focus on critical issues for the Hello World app." ToolsVersion="10.0">
  <Localization ResourceAssembly="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.dll" ResourceBaseName="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.Localized">
    <Name Resource="HelloWorldRules_Name" />
    <Description Resource="HelloWorldRules_Description" />
  </Localization>
  <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
    <Rule Id="CA1001" Action="Warning" />
    <Rule Id="CA1009" Action="Warning" />
    <Rule Id="CA1016" Action="Warning" />
    <Rule Id="CA1033" Action="Warning" />
  </Rules>
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1802" Action="Error" />
    <Rule Id="CA1814" Action="Info" />
    <Rule Id="CA1823" Action="None" />
    <Rule Id="CA2217" Action="Warning" />
  </Rules>
</RuleSet>
```

> [!TIP]
> Daha kolay [bir kural kümesi Düzenle](../code-quality/working-in-the-code-analysis-rule-set-editor.md) grafik **kural kümesi düzenleyici** el ile daha.

Kural tarafından belirtilen proje için kümesi `CodeAnalysisRuleSet` Visual Studio Proje dosyasında özellik. Örneğin:

```xml
<CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Kod çözümleme kural kümesi başvurusu](../code-quality/rule-set-reference.md)
