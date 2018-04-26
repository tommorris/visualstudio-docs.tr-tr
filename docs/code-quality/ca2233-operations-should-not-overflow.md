---
title: 'CA2233: İşlemler taşmamalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OperationsShouldNotOverflow
- CA2233
helpviewer_keywords:
- OperationsShouldNotOverflow
- CA2233
ms.assetid: 3a2b06ba-6d1b-4666-9eaf-e053ef47ffaa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93d4fc872f14a63eeec446d8e6d1f9a2c7acf7ff
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2233-operations-should-not-overflow"></a>CA2233: İşlemler taşmamalıdır
|||
|-|-|
|TypeName|OperationsShouldNotOverflow|
|CheckId|CA2233|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Bir yöntem aritmetik işlemi gerçekleştirir ve işlenen önceden taşmayı engellemek için doğrulamaz.

## <a name="rule-description"></a>Kural Tanımı
 Aritmetik işlemler işleminin sonucu dahil edilen veri türleri için olası değerler aralığının dışında olduğundan emin olmak için işlenen doğrulamadan gerçekleştirilmemelidir. Yürütme bağlamı ve söz konusu veri türlerine bağlı olarak, aritmetik taşma ya da sonuçlanabilir bir <xref:System.OverflowException?displayProperty=fullName> veya sonucunun en önemli BITS atılır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için işlemi gerçekleştirmeden önce işlenen doğrulayın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan işlenenler olası değerler hiçbir zaman aritmetik işlemin dışına taşmasına neden olup olmayacağını gizlemek güvenlidir.

## <a name="example-of-a-violation"></a>Bir ihlali örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnekte bir yöntem bu kuralını ihlal eden bir tamsayı yönetir. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] gerektirir **kaldırmak** tamsayı taşma seçeneği bu tetiklenecek devre dışı.

### <a name="code"></a>Kod
 [!code-vb[FxCop.Usage.OperationOverflow#1](../code-quality/codesnippet/VisualBasic/ca2233-operations-should-not-overflow_1.vb)]
 [!code-csharp[FxCop.Usage.OperationOverflow#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_1.cs)]

### <a name="comments"></a>Açıklamalar
 Bu örnekte yöntemi aktarılırsa <xref:System.Int32.MinValue?displayProperty=fullName>, underflow işlemi gerekir. Bu, en önemli bit atılmak üzere sonucunun neden olur. Aşağıdaki kod bu nasıl gerçekleştiğini gösterir.

 [C#]

```
public static void Main()
{
    int value = int.MinValue;    // int.MinValue is -2147483648
    value = Calculator.Decrement(value);
    Console.WriteLine(value);
}
```

 [VB]

```
Public Shared Sub Main()
    Dim value = Integer.MinValue    ' Integer.MinValue is -2147483648
    value = Calculator.Decrement(value)
    Console.WriteLine(value)
End Sub
```

### <a name="output"></a>Çıkış

```
2147483647
```

## <a name="fix-with-input-parameter-validation"></a>Giriş parametresi doğrulama ile Düzelt

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, önceki ihlali giriş değerini doğrulayarak giderir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.OperationOverflowFixed#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_2.cs)]
 [!code-vb[FxCop.Usage.OperationOverflowFixed#1](../code-quality/codesnippet/VisualBasic/ca2233-operations-should-not-overflow_2.vb)]

## <a name="fix-with-a-checked-block"></a>Checked bloğu ile Düzelt

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, önceki ihlali checked bloğunda kaydırılan işlem giderir. İşlemi, taşmaya neden olursa bir <xref:System.OverflowException?displayProperty=fullName> oluşturulur.

 Checked blokları içinde desteklenmez Not [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)].

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.OperationOverflowChecked#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_3.cs)]

## <a name="turn-on-checked-arithmetic-overflowunderflow"></a>Aritmetik Taşma/Underflow etkinleştirin işaretli
 Checked aritmetik taşma/underflow C# üzerinde kapatırsanız, her tamsayı işlemi checked bloğunda kaydırma eşdeğerdir.

 **Checked aritmetik taşma/underflow C# etkinleştirmek için**

1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve seçin **özellikleri**.

2.  Seçin **yapı** sekmesinde **Gelişmiş**.

3.  Seçin **denetlemek için aritmetik taşma/underflow** tıklatıp **Tamam**.

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.OverflowException?displayProperty=fullName> [C# işleçleri](/dotnet/csharp/language-reference/operators/index) [Checked ve Unchecked](/dotnet/csharp/language-reference/keywords/checked-and-unchecked)