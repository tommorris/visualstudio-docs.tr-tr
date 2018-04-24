---
title: Kullanın ve Visual Studio Roslyn çözümleyiciler yapılandırın
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2eeebb1fb631c0890c7bcb11160109813a31eef1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="configure-and-use-roslyn-analyzer-rules"></a>Yapılandırma ve Roslyn çözümleyicisi kuralları kullanma

.NET derleme Platformu ("Roslyn") çözümleyicisi kuralları veya *tanılama*, siz yazarken, C# veya Visual Basic kodunuzun analiz edin. Her tanılama projeniz için geçersiz kılınabilir bir varsayılan önem derecesi ve gizleme durumuna sahip. Bu makalede, kural kümeleri kullanma ve ihlalleri gizleme, ayarı kural önem derecesi yer almaktadır.

## <a name="analyzers-in-solution-explorer"></a>Çözüm Gezgini'nde çözümleyiciler

Çözümleyici tanılama özelleştirme çoğunu yapmak için **Çözüm Gezgini**. Varsa, [çözümleyiciler yüklemek](../code-quality/install-roslyn-analyzers.md) bir NuGet paketi olarak bir **çözümleyiciler** düğümü altında görünmektedir **başvuruları** veya **bağımlılıkları** düğümünde **Çözüm Gezgini**. Genişletirseniz **çözümleyiciler**ve Çözümleyicisi derlemeleri birini genişletin, derlemedeki tüm tanılama bakın.

![Çözüm Gezgini'nde çözümleyiciler düğümü](media/analyzers-expanded-in-solution-explorer.png)

Açıklaması ve varsayılan önem dahil olmak üzere bir tanılama özelliklerini görüntüleyebilirsiniz **özellikleri** penceresi. Özelliklerini görüntülemek için kuralı sağ tıklatın ve **özellikleri**, veya kuralı seçin ve sonra basın **Alt**+**Enter**.

![Özellikler penceresindeki tanılama özellikleri](media/analyzer-diagnostic-properties.png)

Bir tanılama için çevrimiçi belgeleri görmek için tanı üzerinde sağ tıklatın ve seçin **Yardımı Görüntüle**.

Her tanılama yanındaki simge **Çözüm Gezgini** kural Düzenleyicisi'nde açtığınızda kümesi içinde gördüğünüz simgeler karşılık gelir:

- bir daire "i" gösteren bir [önem](#rule-severity) , **bilgisi**
- "!" bir üçgen gösteren bir [önem](#rule-severity) , **uyarı**
- bir daire "x" gösteren bir [önem](#rule-severity) , **hata**
- açık renkli arka plan üzerinde bir daire "i" gösteren bir [önem](#rule-severity) , **gizli**
- Tanı gizlendiğinden bir daire içinde aşağıyı gösteren ok gösterir

![Çözüm Gezgini'nde tanılama simgeler](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-sets"></a>Kural kümeleri

A [kural kümesi](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) tek tek tanılama için önem derecesi ve gizleme durumunu depolayan bir XML dosyasıdır. Kural kümeleri tek bir projeye uygulamak ve bir proje birden çok kural kümeleri olabilir. Etkin kural Düzenleyicisi'nde kümesini görüntülemek için sağ **çözümleyiciler** düğümünde **Çözüm Gezgini** seçip **açık etkin kural kümesi**. Bu kural erişimi ilk kez ayarlayın, adında bir dosya  *\<projectname > .ruleset* projeye eklendi ve görünür **Çözüm Gezgini**.

> [!NOTE]
> Kural kümeleri statik (ikili) Kod Analizi ve Roslyn analyzer kuralları içerir.

Etkin kural için bir proje üzerinde kümesi değiştirebileceğiniz **Kod Analizi** bir projenin özellikleri. Kural kümesi seçin **bu kural kümesini çalıştırmak** aşağı açılan liste. Kümeden kuralı da açabilirsiniz **Kod Analizi** seçerek özellik sayfası **açmak**.

## <a name="rule-severity"></a>Kural önem derecesi

Önem derecesi analyzer kuralları yapılandırabilirsiniz veya *tanılama*, varsa, [çözümleyiciler yüklemek](../code-quality/install-roslyn-analyzers.md) bir NuGet paketi olarak. Aşağıdaki tabloda tanılama için önem derecesi seçenekleri gösterir:

|Önem Derecesi|Derleme zamanı davranışı|Düzenleyici davranışı|
|-|-|-|
|Hata|İhlalleri görünür olarak *hataları* içinde **hata listesi** ve komut satırı çıkışı yapı ve derlemeleri başarısız olmasına neden.|Kod sorunlu altı çizili bir kırmızı dalgalı ve küçük kırmızı kutu kaydırma çubuğu olarak işaretli.|
|Uyarı|İhlalleri görünür olarak *uyarıları* içinde **hata listesi** ve komut satırı çıkışı yapı, ancak derlemeleri başarısız olmasına neden olmaz.|Kod sorunlu dalgalı ve küçük yeşil kutu kaydırma çubuğu olarak işaretlenmiş bir yeşil ile altı çizili olur.|
|Bilgi|İhlalleri görünür olarak *iletileri* içinde **hata listesi**ve komut satırı derleme çıktısındaki hiç.|Kod sorunlu dalgalı ve küçük gri kutu kaydırma çubuğu olarak işaretlenmiş bir gri ile altı çizili olur.|
|Hidden|Non-kullanıcıya görünür.|Non-kullanıcıya görünür. Tanı IDE Tanılama Altyapısı ancak raporlanır.|
|Yok.|Tamamen engellenir.|Tamamen engellenir.|

Ayrıca, "bir kuralın önem ayarlayarak sıfırlayabilirsiniz" **varsayılan**. Her tanılama görülebilir bir varsayılan önem derecesine sahip **özellikleri** penceresi.

Aşağıdaki ekran görüntüsünde, Kod düzenleyicisinde, üç farklı önem derecelerine sahip üç farklı tanılama ihlalleri gösterir. Dalgalı yanı sıra küçük bir kutu sağa kaydırma çubuğunda rengi dikkat edin.

![Kod düzenleyicisinde hata, uyarı ve bilgi ihlali](media/diagnostics-severity-colors.png)

İçinde göründükleri gibi aynı üç ihlalleri aşağıdaki ekran gösterilir **hata listesi**:

![Hata Listesi dosyasında hata, uyarı ve bilgi ihlali](media/diagnostics-severities-in-error-list.png)

Bir kuraldan önemi değiştirebilirsiniz **Çözüm Gezgini**, veya içinde  *\<projectname > .ruleset* kuralındaöneminideğiştirdiktensonraçözümeeklenendosya **Çözüm Gezgini**.

![Çözüm Gezgini'nde RuleSet dosyası](media/ruleset-in-solution-explorer.png)

### <a name="to-set-rule-severity-from-solution-explorer"></a>Çözüm Gezgini'nde kural önem ayarlamak için

1. İçinde **Çözüm Gezgini**, genişletin **başvuruları** > **çözümleyiciler** (**bağımlılıkları**  >  **Çözümleyiciler** .NET Core projeleri için).

1. Önem derecesi için ayarlamak istediğiniz kuralı içeren derlemenin genişletin.

1. Sağ tıklatın ve kural **kural kümesi önem derecesi ayarlanmıştır**. Uçarak çıkış menüde önem seçeneklerden birini belirleyin.

   Kural için önem derecesi etkin kural kümesi dosyasında kaydedilir.

### <a name="to-set-rule-severity-in-the-rule-set-file"></a>Kural kümesi için dosya kuralında önem derecesini belirle

1. Açık kural dosyasını çift tıklatarak kümesi **Çözüm Gezgini**, seçme **açık etkin kural kümesi** sağ tıklatma menüsünden **çözümleyiciler** düğümü veya seçerek **Açık** üzerinde **Kod Analizi** projesi için özellik sayfası.

1. Kural için kendi içeren derleme genişleterek göz atın.

1. İçinde **eylem** sütunu açılan listesini açmak için bir değer seçin ve listeden istediğiniz önem derecesini seçin.

   ![RuleSet dosyayı düzenleyicide Aç](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>İhlali bastırma

Kural ihlallerinin gizlemek için birden çok yolu vardır:

- Tüm geçerli ihlalleri gizlemek üzere seçin **Çözümle** > **Kod Analizi çalıştırmak ve bastırmak etkin sorunlar** menü çubuğunda. Bu bazen "taban çizgisi oluşturma" adlandırılır.

- Gelen bir tanılama gizlemek için **Çözüm Gezgini**, önemine kümesine **hiçbiri**.

- Bir tanılama kural kümesi düzenleyicisinden gizlemek için adının yanındaki onay kutusunu temizleyin veya ayarlayın **eylem** için **hiçbiri**.

- Bir tanılama kod düzenleyicisinden gizlemek için basın ve ihlali ile kod satırı imleci yerleştirin. **Ctrl**+**.** açmak için **hızlı Eylemler** menüsü. Seçin **CAxxxx bastırmak** > **kaynağındaki** veya **CAxxxx bastırmak** > **gizleme dosyasında**.

   ![Hızlı Eylemler menüsünden tanılama gösterme](media/suppress-diagnostic-from-editor.png)

- Gelen bir tanılama gizlemek için **hata listesi**, hata, uyarı veya ileti sağ tıklatın ve seçin **bastır** > **içinde kaynak** veya **Bastırmak** > **gizleme dosyasında**.

   - Seçerseniz **içinde kaynak**, **Değişiklikleri Önizle** iletişim kutusu açılır ve C# önizlemesini [#pragma Uyarısı](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) veya Visual Basic [#Disable uyarı](/dotnet/visual-basic/language-reference/directives/directives) kaynak koduna eklenen yönergesi.

      ![#Pragma uyarısı kod dosyasında ekleme Önizleme](media/pragma-warning-preview.png)

   - Seçerseniz **gizleme dosyasını**, **Değişiklikleri Önizle** iletişim kutusu açılır ve önizlemesini <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> genel suppressions dosyasına eklenen özniteliği.

      ![SuppressMessage özniteliği gizleme dosyasına ekleme Önizleme](media/preview-changes-in-suppression-file.png)

   İçinde **Değişiklikleri Önizle** iletişim kutusunda **Uygula**.

> [!NOTE]
> NuGet çözümleyiciler sahip olan bir projeyi bir başvuru ekleyin bir .NET Core projesinde bu çözümleyiciler otomatik olarak bağımlı projeye çok eklenir. Bağımlı proje birim testi projesi, örneğin bu davranışı devre dışı bırakmak için NuGet paketi olarak içinde özel işaretle *.csproj* veya *.vbproj* başvuruda bulunulan proje dosyası:
>
> ```xml
> <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.6.0" PrivateAssets="all" />
> ```

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Roslyn çözümleyiciler genel bakış](../code-quality/roslyn-analyzers-overview.md)
- [Roslyn Çözümleyicisi hata gönderme](https://github.com/dotnet/roslyn-analyzers/issues)
- [Kural kümeleri kullanma](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [Kod çözümleme uyarılarını bastırma](../code-quality/in-source-suppression-overview.md)