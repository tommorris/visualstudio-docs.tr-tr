---
title: 'CA1813: Korumasız özniteliklerden kaçının'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1813
- AvoidUnsealedAttributes
helpviewer_keywords:
- CA1813
- AvoidUnsealedAttributes
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b861591355a47d38beec921a13643841b40e4465
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813: Korumasız özniteliklerden kaçının
|||
|-|-|
|TypeName|AvoidUnsealedAttributes|
|CheckId|CA1813|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Ortak tür devraldığı <xref:System.Attribute?displayProperty=fullName>, Özet olmayan ve korumalı değil (`NotInheritable` Visual Basic'te).

## <a name="rule-description"></a>Kural Tanımı
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Sınıf kitaplığı özel öznitelikleri alma için yöntemler sağlar. Varsayılan olarak, bu yöntemleri özniteliği devralma hiyerarşisinde aramaya; Örneğin <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> belirtilen öznitelik türünün veya belirtilen öznitelik türünün genişletir herhangi bir öznitelik türü arar. Öznitelik mühürleme devralma hiyerarşisi aracılığıyla arama ortadan kaldırır ve performansı artırabilir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için öznitelik türü korumaya veya soyut olun.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan gizlemek güvenlidir. Yalnızca, bir öznitelik hiyerarşisi tanımlama ve öznitelik korumaya veya soyut olun varsa bunu yapmanız gerekir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural karşılayan özel bir öznitelik gösterir.

 [!code-csharp[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/CSharp/ca1813-avoid-unsealed-attributes_1.cs)]
 [!code-vb[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/VisualBasic/ca1813-avoid-unsealed-attributes_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1019: Öznitelik bağımsız değişkenleri için erişimcileri tanımlayın](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

 [CA1018: Öznitelikleri AttributeUsageAttribute ile işaretleyin](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Öznitelikler](/dotnet/standard/design-guidelines/attributes)