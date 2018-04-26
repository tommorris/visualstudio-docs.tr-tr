---
title: Visual Studio'da kod çözümleme uyarılarını bastırma
ms.date: 01/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: aec11e54547f05e3ac7babae29e0c95737bc725e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="suppress-code-analysis-warnings"></a>Kod çözümleme uyarılarını bastırma

Genellikle, bir uyarı geçerli olmadığını göstermek kullanışlıdır. Bu kodu gözden ve uyarı gizlenebilir ekip üyelerine gösterir. Kaynak gizleme (ISS) kullanan <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> bir gizlemek için öznitelik. Öznitelik uyarı oluşturulan kod kesimi yakın yerleştirilebilir. Ekleyebileceğiniz <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> özniteliği kaynak dosyasını, yazarak veya kısayol menüsünden bir uyarı kullanabilirsiniz **hata listesi** otomatik olarak eklemek için.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> Özniteliktir, yönetilen kod derlemenizi IL meta verilerine dahil bir koşullu özniteliği yalnızca derleme zamanında CODE_ANALYSIS derleme simgenin tanımlanmışsa.

C + +/ CLI, CA makroları kullanmak\_BASTIR\_ileti veya CA\_genel\_öznitelik eklemek için üstbilgi dosyasında SUPPRESS_MESSAGE.

> [!NOTE]
> Kaynak suppressions yayın derlemeleri üzerinde kaynak gizleme meta verileri yanlışlıkla sevkiyat önlemek için kullanmamanız gerekir. Ayrıca, kaynak gizleme işleme maliyetini nedeniyle, uygulamanızın performansı düşebilir.

> [!NOTE]
> Bir proje için Visual Studio 2017 geçirirseniz, aniden zorlamayı bir kod çözümleme uyarıları sayısıyla karşılaştığı. Uyarıları gidermek ve Kod Analizi geçici olarak devre dışı istediğiniz hazır değilseniz, proje özellik sayfalarını açın (**proje** > ***proje* özellikler...** ) ve Git **Kod Analizi** sekmesi. Seçimini **etkinleştirmek Kod Analizi derlemede**ve projenizi yeniden derleyin. Alternatif olarak, farklı, daha küçük kural kodu çalıştırmak için kümesini seçebilirsiniz. Kod çözümleme uyarıları gidermek hazır olduğunuzda geri üzerinde açmayı unutmayın.

## <a name="suppressmessage-attribute"></a>SuppressMessage özniteliği

Seçtiğinizde **bastır** bir kod çözümleme uyarı bağlamı veya sağ tıklama menüsünden **hata listesi**, <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> özniteliği kodunuzda veya projenin genel gizleme eklenir dosya.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> Özniteliği şu biçime sahiptir:

```vb
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>
```

```csharp
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]
```

```cpp
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")
```

Öznitelik özellikleri içerir:

- **Kural kategori** -kural tanımlanır kategorisi. Kod çözümleme kural kategorileri hakkında daha fazla bilgi için bkz: [kod uyarıları yönetilen](../code-quality/code-analysis-for-managed-code-warnings.md).

- **Kural Kimliği** -kuralının tanıtıcısı. Hem kısa ve uzun ad kuralı tanımlayıcısı için destek içerir. Kısa ad CAXXXX olur; uzun CAXXXX:FriendlyTypeName adıdır.

- **Düzeltme** -ileti gizleme nedenini belgelemek için kullanılan metin.

- **İleti kimliği** -her ileti için sorun benzersiz tanıtıcısı.

- **Kapsam** -üzerinde uyarı geçersiz kılınır hedef. Hedef belirtilmezse, özniteliğin hedef ayarlanır. Desteklenen kapsamları aşağıdakileri içerir:

    - Modül

    - Ad Alanı

    - Kaynak

    - Tür

    - Üye

- **Hedef** - üzerinde uyarı geçersiz kılınır hedef belirtmek için kullanılan tanımlayıcı bir. Bir tam öğesi adı içermelidir.

## <a name="suppressmessage-usage"></a>SuppressMessage kullanımı

Kod çözümleme uyarıları hangi düzeyde gizlenir <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> özniteliği uygulanır. Örneğin, öznitelik derleme, modül, türü, üye veya parametre düzeyinde uygulanabilir. Bunun amacı, sıkı bir şekilde kod gizleme bilgileri eşleştiği için burada ihlali gerçekleşir.

Gizleme genel biçiminde kural kategorisini ve kural adı isteğe bağlı bir kullanıcı tarafından okunabilen gösterimini içeren bir kural tanımlayıcısını içerir. Örneğin:

`[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`

Kaynak gizleme meta verileri en aza indirmek için katı Performans nedeniyle varsa, kural adı atlanabilir. Kural kategorisini ve kendi kural kimliği birlikte yeterince benzersiz kural tanımlayıcısını oluşturur. Örneğin:

`[SuppressMessage("Microsoft.Design", "CA1039")]`

Bakım nedeniyle, kural adı atlama önerilmez.

## <a name="suppress-selective-violations-within-a-method-body"></a>Yöntem gövdesi içinde seçmeli ihlali bastırma

Gizleme öznitelikler için bir yöntem uygulanabilir, ancak bir yöntem gövdesinde katıştırılmış. Bu, eklerseniz, belirli bir kural tüm ihlalleri bastırılan anlamına gelir <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> özniteliği yöntemi.

Bazı durumlarda, böylece gelecekteki kod Kod Analizi kural dışında otomatik olarak muafiyet değil ihlali, örneğin belirli bir örneği bastırmak isteyebilirsiniz. Belirli kod çözümleme kurallarını kullanarak bunu izin `MessageId` özelliğinin <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> özniteliği. Genel olarak, belirli simgesi (yerel değişken veya parametre) saygı üzerinde ihlalleri için eski kuralları `MessageId` özelliği. [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md) böyle bir kural örneğidir. Ancak, eski kuralları yürütülebilir kod (symbol olmayan) üzerinde ihlalleri için saygı `MessageId` özelliği. Ayrıca, .NET derleme Platformu ("Roslyn") çözümleyiciler saygı `MessageId` özelliği.

Bir kural belirli sembol ihlal gizlemek için sembol adını belirtin `MessageId` özelliğinin <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> özniteliği. Aşağıdaki örnek, iki ihlalleri koduyla gösterir [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)&mdash;için bir tane `name` değişkeni, diğeri de `age` değişkeni. Yalnızca ihlali için `age` simgesi geçersiz kılınır.

```vb
Public Class Animal
    Dim age As Integer
    Dim name As String

    <CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId:="age")>
    Sub PrintInfo()
        Dim age As Integer = 5
        Dim name As String = "Charlie"

        Console.WriteLine("Age {0}, Name {1}", age, name)
    End Sub

End Class
```

```csharp
public class Animal
{
    int age;
    string name;

    [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId = "age")]
    private void PrintInfo()
    {
        int age = 5;
        string name = "Charlie";

        Console.WriteLine($"Age {age}, Name {name}");
    }
}
```

## <a name="generated-code"></a>Oluşturulan kod

Yönetilen kod derleyicileri ve bazı üçüncü taraf araçları hızlı kod geliştirme kolaylaştırmak için kod oluşturur. Kaynak dosyaları görünür derleyici tarafından üretilen kod ile genellikle işaretlenir `GeneratedCodeAttribute` özniteliği.

Kod çözümleme uyarıları ve hataları üretilen kod için engellenip engellenmeyeceğini seçebilirsiniz. Bu tür uyarılar ve hatalar gizlemek hakkında daha fazla bilgi için bkz: [nasıl yapılır: üretilen kod için uyarıları bastırma](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md).

> [!NOTE]
> Kod çözümleme yoksayar `GeneratedCodeAttribute` zaman uygulandığı tüm bütünleştirilmiş veya tek bir parametre.

## <a name="global-level-suppressions"></a>Genel düzey suppressions

Yönetilen kod çözümleme aracı inceler `SuppressMessage` derleme modül türü üye veya parametre düzeyinde uygulanır öznitelikleri. Ayrıca, kaynakları ve ad alanları karşı ihlalleri ateşlenir. Bu ihlalleri genel düzeyde uygulanmış olması gerekir ve kapsamlı ve hedeflenen. Örneğin, aşağıdaki ileti, bir ad alanı ihlali gizler:

`[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`

> [!NOTE]
> Ad alanı kapsamlı bir uyarı bastırma olduğunda uyarı ad karşı gizler. Ad alanı içindeki türleriyle uyarı bastırma değil.

Tüm gizleme açık bir kapsam belirterek ifade edilebilir. Bu suppressions genel düzeyde bulunmalıdır. Üye düzeyi gizleme türü tasarlayarak belirtemezsiniz.

Genel düzey suppressions açıkça sağlanan kullanıcı kaynağına eşlemiyor derleyici tarafından üretilen kod başvurmak iletileri bastırmak için tek yoludur. Örneğin, aşağıdaki kod bir ihlali derleyici yayılan Oluşturucusu karşı gizler:

`[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`

> [!NOTE]
> `Target` her zaman tam öğe adı içerir.

## <a name="global-suppression-file"></a>Genel gizleme dosyası

Genel gizleme dosyası genel düzeyde suppressions ya da bir hedef belirtmeyin suppressions suppressions sağlar. Örneğin, suppressions derleme düzeyi ihlalleri için bu dosyada depolanır. Ayrıca, proje düzeyi ayarlarla bir form arka plan kod için kullanılabilir olmadığından bazı ASP.NET suppressions bu dosyada depolanır. Bir genel gizleme dosyası oluşturulur ve seçtiğiniz ilk kez projenize eklenir **proje gizleme dosyasını** seçeneği **bastır** komutunu **hata listesi**penceresi.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Diagnostics.CodeAnalysis>
- [Roslyn çözümleyiciler kullanın](../code-quality/use-roslyn-analyzers.md)