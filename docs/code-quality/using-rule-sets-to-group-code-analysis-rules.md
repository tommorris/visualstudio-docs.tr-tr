---
title: Kod analizi kural kümeleri
ms.date: 04/02/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: fa287570213e6238d0a8dffc9f6e70367b133591
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204433"
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>Kural Kod Analizi kurallarını gruplandırmak için kümeleri kullanma

Visual Studio'da Kod Analizi yapılandırdığınızda, yerleşik bir listeden seçebilirsiniz *kural kümeleri*. Bir kural kümesi bir proje için de geçerlidir ve bir kod hedeflenen sorunlar ve bu proje için belirli koşullar belirlemek çözümleme kurallarını gruplandırmasıdır. Örneğin, kod genel kullanıma açık API'leri taramak için tasarlanmış bir kural kümesi uygulayabilir veya önerilen minimum kurallar. İçeren tüm kurallar kural kümesi de uygulayabilirsiniz.

Bir kural uyarılar veya hatalar olarak görüntülenecek kümesi ekleyerek veya silerek kural veya kural önem dereceleri değiştirerek özelleştirebilirsiniz **hata listesi**. Özel kural kümeleri belirli geliştirme ortamınızı gereksinimini karşılayabilir. Bir kural kümesi özelleştirdiğinizde, kural kümesi Düzenleyici'sini arama ve filtreleme süreçte yardımcı olacak araçlar sağlar.

Kural kümeleri için kullanılabilir [yönetilen kodu statik analizini](how-to-configure-code-analysis-for-a-managed-code-project.md), [C++ Kod Analizi](using-rule-sets-to-specify-the-cpp-rules-to-run.md), ve [Roslyn Çözümleyicileri](analyzer-rule-sets.md).

## <a name="rule-set-format"></a>Kural kümesi biçimi

XML biçiminde kural kümesi belirtilen bir *.ruleset* dosya. Kuralları, bir kimliği oluşur ve bir *eylem*, çözümleyici kimliği ve ad alanı dosyasındaki göre gruplandırılır.

İçeriği bir *.ruleset* dosya bu XML'e benzer görünür:

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
> Kolaydır [bir kural kümesini Düzenle](../code-quality/working-in-the-code-analysis-rule-set-editor.md) grafik **kural kümesi Düzenleyicisi** el ile daha.

Kural için bir proje tarafından belirtilen kümesi **CodeAnalysisRuleSet** Visual Studio Proje dosyasındaki özellik. Örneğin:

```xml
<CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Kod çözümleme kural kümesi başvurusu](../code-quality/rule-set-reference.md)