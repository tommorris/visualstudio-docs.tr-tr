---
title: 'CA1028: Numaralandırma depolaması Int32 olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f0f9dec006f3684259541811e905eaf75a790c3a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900294"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: Numaralandırma depolaması Int32 olmalıdır
|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Genel sabit listesi, temel alınan tür değil <xref:System.Int32?displayProperty=fullName>.

## <a name="rule-description"></a>Kural Tanımı
 Bir numaralandırma ilişkili adlandırılmış sabitler kümesini tanımlayan değer türüdür. Varsayılan olarak, <xref:System.Int32?displayProperty=fullName> veri türü, sabit değeri depolamak için kullanılır. Bu temel alınan tür değişiklik olsa bile, çoğu senaryoları için gerekli veya önerilen değil. Önemli performans kazancı değerinden küçük bir veri türü kullanılarak sağlanır Not <xref:System.Int32>. Varsayılan veri türü kullanamıyorsanız, bir ortak dil sistem (CLS), kullanmanız gereken-uyumlu tam sayı türleri <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32>, veya <xref:System.Int64> tüm numaralandırma değerlerini de gösterilebilir emin olmak için CLS uyumlu programlama dili.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal boyutu veya uyumluluk sorunları var sürece düzeltmek için kullanın <xref:System.Int32>. Durumlar için burada <xref:System.Int32> değerleri tutun, kullanmak için yeterince büyük değil <xref:System.Int64>. Geriye dönük uyumluluk küçük bir veri türü gerektiriyorsa, kullanın <xref:System.Byte> veya <xref:System.Int16>.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Yalnızca geriye dönük uyumluluk sorunları gereksinim duyuyorsanız bir uyarı bu kuraldan engelleyin. Uygulamalarda, genellikle bu kurala uygun hatası sorununa neden olmaz. Diller arası birlikte çalışabilirlik gerekli olduğu kitaplıklarda, bu kurala uygun hatası kullanıcılarınızın olumsuz yönde etkileyebilir.

## <a name="example-of-a-violation"></a>Bir ihlali örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, önerilen temel alınan veri türünü kullanmayın iki numaralandırmalar gösterir.

### <a name="code"></a>Kod
 [!code-vb[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_1.vb)]
 [!code-csharp[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_1.cs)]

## <a name="example-of-how-to-fix"></a>Nasıl bir örneği için düzeltme

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, temel alınan veri türünü değiştirerek önceki ihlali giderir <xref:System.Int32>.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_2.cs)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_2.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1008: Numaralandırmalar sıfır değerine sahip olmalıdır](../code-quality/ca1008-enums-should-have-zero-value.md)

 [CA1027: Numaralandırmaları FlagsAttribute ile işaretleyin](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1700: Numaralandırma değerlerini 'Ayrılmış' olarak adlandırmayın](../code-quality/ca1700-do-not-name-enum-values-reserved.md)

 [CA1712: Numaralandırma değerleri için tür adıyla önek kullanmayın](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Byte?displayProperty=fullName> <xref:System.Int16?displayProperty=fullName> <xref:System.Int32?displayProperty=fullName> <xref:System.Int64?displayProperty=fullName>