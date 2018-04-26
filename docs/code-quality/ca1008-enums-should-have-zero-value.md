---
title: 'CA1008: Numaralandırmalar sıfır değerine sahip olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f35fc55d9baa59481647ee82aee5ccdeb84e7196
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: Numaralandırmalar sıfır değerine sahip olmalıdır
|||
|-|-|
|TypeName|EnumsShouldHaveZeroValue|
|CheckId|CA1008|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Eklemeniz istendiğinde bölünemez - bir **hiçbiri** bayrağı olmayan numaralandırma değeri. Yeniden adlandırmak veya herhangi bir numaralandırma değeri kaldırmak için istendiğinde - kesiliyor.|

## <a name="cause"></a>Sebep
 Uygulanan bir olmadan numaralandırma <xref:System.FlagsAttribute?displayProperty=fullName> ; sıfır veya bir uygulanmış olan numaralandırma değerine sahip bir üye tanımlamıyor <xref:System.FlagsAttribute> üyesi tanımlar sıfır değerine sahip ancak adını 'None' değil ya da birden çok sıfır değerli numaralandırması tanımlar Üyeler.

## <a name="rule-description"></a>Kural Tanımı
 Sıfır diğer değer türleri gibi başlatılmamış bir numaralandırmanın varsayılan değerdir. Varsayılan değer geçerli bir değer numaralandırma; böylece sıfır değerine sahip bir üye bayrakları öznitelikli numaralandırması tanımlamanız gerekir. Uygunsa, üye 'None' adı. Aksi takdirde, en sık kullanılan üye sıfıra atayın. İlk Numaralandırma üye değeri bildiriminde ayarlanmazsa varsayılan olarak, değeri sıfır olduğuna dikkat edin.

 Sahip numaralandırma varsa <xref:System.FlagsAttribute> uygulanan sıfır değerli bir üye tanımlar adını hiçbir değer numaralandırmada ayarlanan belirtmek için ' None' olmalıdır. Herhangi bir amaçla kullanılması aykırı için sıfır değerli üyesi kullanarak <xref:System.FlagsAttribute> içeren ve ve bit düzeyinde işleçler üyesiyle yaramaz. Bu, yalnızca bir üye sıfır değeri atanması anlamına gelir. Birden çok üye varsa, sıfır değeri bir bayrakları öznitelikli sıralamasında ortaya Not `Enum.ToString()` sıfır olmayan üyeler için hatalı sonuçlar döndürür.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural bayrakları öznitelikli numaralandırmalar için ihlal düzeltmek için sıfır değerine sahip bir üye tanımlayın; Bu bölünemez farklıdır. Bayrakları öznitelikli numaralandırmalar sıfır değerli üyesi tanımlayan bu üye 'None' adı ve sıfır değerine sahip diğer üyeleri silin; önemli bir değişiklik budur.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural daha önce gönderilen bayrakları öznitelikli numaralandırmalar dışında bir uyarıdan engelleme.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, kural karşılamak iki numaralandırmalar ve bir numaralandırma gösterir `BadTraceOptions`, kural, ihlal ediyor.

 [!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
 [!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
 [!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2217: Numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1700: Numaralandırma değerlerini 'Ayrılmış' olarak adlandırmayın](../code-quality/ca1700-do-not-name-enum-values-reserved.md)

 [CA1712: Numaralandırma değerleri için tür adıyla önek kullanmayın](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

 [CA1028: Numaralandırma depolaması Int32 olmalıdır](../code-quality/ca1028-enum-storage-should-be-int32.md)

 [CA1027: Numaralandırmaları FlagsAttribute ile işaretleyin](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Enum?displayProperty=fullName>