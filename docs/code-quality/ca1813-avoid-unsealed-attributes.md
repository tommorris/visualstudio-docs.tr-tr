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
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b7b5b360a6288b6ff2e13b6d7fc29df6728fad6f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546255"
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813: Korumasız özniteliklerden kaçının

|||
|-|-|
|TypeName|AvoidUnsealedAttributes|
|CheckId|CA1813|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep

Bir ortak türün devraldığı <xref:System.Attribute?displayProperty=fullName>soyut ve korumalı değil (`NotInheritable` Visual Basic'te).

## <a name="rule-description"></a>Kural açıklaması

[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Sınıf kitaplığı özel öznitelikleri almak için yöntemler sağlar. Varsayılan olarak, bu yöntemleri öznitelik devralma hiyerarşisinde arar. Örneğin, <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> belirtilen öznitelik türünün veya belirtilen öznitelik türü genişleten herhangi bir öznitelik türü arar. Öznitelik mühürleme kalıtım hiyerarşisi aracılığıyla aramayı ortadan kaldırır ve performansı artırabilir.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?

Bu kural ihlalini düzeltmek için öznitelik türünü mühürleyin veya soyut olun.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında

Bu kuraldan bir uyarıyı bastırmak güvenlidir. Yalnızca bir öznitelik hiyerarşisi tanımlıyorsanız gösterme ve öznitelik mühürleme ya da soyut kolaylaştırır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bu kural karşılayan özel bir öznitelik gösterir.

[!code-csharp[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/CSharp/ca1813-avoid-unsealed-attributes_1.cs)]
[!code-vb[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/VisualBasic/ca1813-avoid-unsealed-attributes_1.vb)]

## <a name="related-rules"></a>İlgili kuralları

- [CA1019: Öznitelik bağımsız değişkenleri için erişimcileri tanımlayın](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)
- [CA1018: Öznitelikleri AttributeUsageAttribute ile işaretleyin](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Öznitelikler](/dotnet/standard/design-guidelines/attributes)