---
title: Visual Studio'da Roslyn çözümleyiciler
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: overview
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: aaa989347744e015b90cca186c6aa9756dfe90fe
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922303"
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>.NET derleme platformu çözümleyiciler genel bakış

Visual Studio 2017 yazarken, C# veya Visual Basic kodu çözümleyen .NET derleyici platformu çözümleyiciler yerleşik bir dizi içerir. Visual Studio uzantısı olarak veya bir proje başına temelinde ek çözümleyiciler bir NuGet paketi olarak yükleyebilirsiniz. Çözümleyiciler kod stili, kod kalitesini ve Bakım, kod tasarım ve diğer sorunları arayın.

Kural ihlallerinin bir Çözümleyicisi tarafından bulunursa, raporlanan Kod düzenleyicisinde hem de bir *dalgalı* soruna neden olan kod altında ve buna **hata listesi**.

Birçok analyzer kuralları veya *tanılama*, sahip bir veya daha fazla ilişkili *kod düzeltmeleri* sorunu düzeltmek için geçerli olabilir. Visual Studio'ya her yerleşik Çözümleyicisi tanılama ilişkili kodu düzeltme vardır. Kod düzeltmeleri ampul simgesi menüsünde diğer türleri ile birlikte gösterilir *hızlı Eylemler*. Bu kod düzeltmeler hakkında daha fazla bilgi için bkz: [ortak hızlı Eylemler](../ide/common-quick-actions.md).

![Çözümleyici ihlali ve hızlı eylem kodu Düzelt](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>Roslyn çözümleyiciler statik kod analizi karşılaştırması

.NET derleme Platformu ("Roslyn") çözümleyiciler sonunda yerini alacak [statik kod analizi](../code-quality/code-analysis-for-managed-code-overview.md) yönetilen kod için. Statik kod çözümleme kurallarını çoğunu zaten olarak Roslyn Çözümleyicisi tanılama yeniden yazılmıştır.

Roslyn Çözümleyicisi ihlalleri statik kod analizi kural ihlallerinin gibi görünen **hata listesi**. Ayrıca, Roslyn Çözümleyicisi ihlalleri ayrıca Kod Düzenleyicisi olarak görünmesini *squigglies* soruna neden olan kodu altında. Dalgalı rengi bağlıdır [önem derecesi ayarına](../code-quality/use-roslyn-analyzers.md#rule-severity) kural. Aşağıdaki ekran görüntüsü üç ihlalleri gösterir&mdash;bir kırmızı bir yeşil ve bir gri:

![Kod düzenleyicisinde Squigglies](media/diagnostics-severity-colors.png)

Roslyn çözümleyiciler etkin ancak siz yazarken de canlı statik kod analizi gibi derleme zamanında kod çözümleme! Roslyn çözümleyiciler de etkinleştirirseniz, düzenleyicide açık olmayan kod dosyaları tasarım zamanı analizini sağlar [tam çözüm analizini](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis).

> [!NOTE]
> Derleme hataları ve Uyarıları Roslyn çözümleyiciler gelen yalnızca çözümleyiciler bir NuGet paketi olarak yüklenip yüklenmediğini gösterilmektedir.

Yalnızca aynı türdeki statik kod analizi mu sorunları Roslyn çözümleyiciler rapor, ancak bunların birini veya tümünü, dosya veya proje ihlali oluşumları gidermenizi kolaylaştırır. Bu eylemler adlı *kod düzeltmeleri*. Kod düzeltmeleri IDE özgüdür; Visual Studio'da, bunlar olarak uygulanan [hızlı Eylemler](../ide/quick-actions.md). Tüm Çözümleyicisi tanılama ilişkili kodu düzeltme vardır.

> [!NOTE]
> Menü seçeneği **Çözümle** > **Kod Analizi çalıştırmak** yalnızca statik kod analizi uygular. Ayrıca, bir projenin üzerinde **Kod Analizi** özellik sayfası, **etkinleştirmek Kod Analizi derlemede** ve **bastırmak oluşturulan kod sonuçlarından** onay kutularını uygulamak yalnızca statik kod çözümleme. Bunlar Roslyn çözümleyiciler üzerinde hiçbir etkisi yoktur.

Roslyn çözümleyiciler gelen ihlalleri ve statik kod analizi birbirinden ayırmak için **hata listesi**, bakmak **aracı** sütun. Aracı değeri Çözümleyicisi derlemelerde birini eşleşip eşleşmediğini **Çözüm Gezgini**, örneğin **Microsoft.CodeQuality.Analyzers**, ihlalin Roslyn Çözümleyicisi'nden gelir. Aksi takdirde, ihlalin statik kod çözümlemesinden kaynaklanır.

![Aracı sütununda hata listesi](media/code-analysis-tool-in-error-list.png)

## <a name="nuget-package-vs-extension"></a>NuGet paketi uzantısı karşılaştırması

Çözümleyiciler olabilir .NET derleyici platformu başına-proje bir NuGet paketi ya da Visual Studio genelinde aracılığıyla Visual Studio uzantısı olarak yüklü. Bu iki yöntemden arasındaki bazı anahtar davranış farklılıkları vardır [çözümleyiciler yükleme](../code-quality/install-roslyn-analyzers.md).

### <a name="scope"></a>Kapsam

Visual Studio uzantısı olarak çözümleyiciler yüklerseniz, Visual Studio tüm örneklerini çözüm düzeyinde uygulanır. Çözümleyiciler tercih edilen yöntemdir, bir NuGet paketi olarak yüklerseniz, bunlar NuGet paketi yüklendiği projeye geçerlidir. Takım ortamlarda, kapsam için NuGet paketleri olarak yüklü çözümleyiciler bulunan *tüm geliştiriciler* bu proje üzerinde çalışır.

### <a name="build-errors"></a>Derleme hataları

Komut satırı aracılığıyla veya sürekli tümleştirme parçası olarak (CI) yapı dahil olmak üzere derleme zamanında zorlanan kuralları için bir NuGet paketi olarak çözümleyiciler yükleyin. Bir uzantısı olarak çözümleyiciler yüklerseniz Çözümleyicisi uyarıları ve hataları yapı raporda görünmüyor.

Aşağıdaki ekran görüntüsünde Çözümleyicisi Kuralı ihlali içeren bir proje derleme gelen komut satırı derleme çıkış şunları gösterir:

![MSBuild çıktı kuralı ihlali ile](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>Kural önem derecesi

Visual Studio uzantısı olarak yüklenen çözümleyiciler gelen kuralları önemini ayarlanamıyor. Yapılandırmak için [kural önem](../code-quality/use-roslyn-analyzers.md#rule-severity), çözümleyiciler bir NuGet paketi olarak yükleyin.

## <a name="next-steps"></a>Sonraki adımlar

- [Visual Studio'da Roslyn çözümleyiciler yükleyin](../code-quality/install-roslyn-analyzers.md)
- [Visual Studio'da Roslyn çözümleyiciler kullanın](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da hızlı Eylemler](../ide/quick-actions.md)
- [Kendi Roslyn Çözümleyicisi yazma](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET derleme Platform SDK'sı](/dotnet/csharp/roslyn-sdk/)