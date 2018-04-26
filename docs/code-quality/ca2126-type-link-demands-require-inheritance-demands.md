---
title: 'CA2126: Tür bağlantı talepleri devralma taleplerini gerektirir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d3143bb7508af1fcb0a946ce7e3a3f0a8697b204
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126: Tür bağlantı talepleri devralma taleplerini gerektirir
|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Ortak korumasız tür korumalı bir bağlantı isteği ile geçersiz kılınabilir bir yöntemi vardır ve türünün veya yöntemi ile bir devralma isteğe korunur.

## <a name="rule-description"></a>Kural Tanımı
 Bir bağlantı isteği bir yöntem veya bildiri türü üzerinde belirtilen izninin anında arayanlar yönteminin gerektirir. Bir devralma isteğe bağlı bir yöntem olarak belirtilen izninizin olması için bir geçersiz kılma yöntemi gerektirir. Bir devralma isteğe bağlı bir türü olarak belirtilen izne sahip bir türetilen sınıf gerektirir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için türü veya yöntemi bir devralma isteğe bağlı bağlantı isteğe bağlı olarak aynı izni ile güvenli hale getirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CPP/ca2126-type-link-demands-require-inheritance-demands_1.cpp)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/VisualBasic/ca2126-type-link-demands-require-inheritance-demands_1.vb)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2126-type-link-demands-require-inheritance-demands_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2108: Değer türleri üzerinde bildirimsel güvenliği gözden geçirin](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA2112: Güvenli türler alanları açığa çıkarmamalıdır](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA2122: Bağlantı talepleri olan yöntemleri dolaylı olarak açığa çıkarmayın](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123: Geçersiz kılan bağlantı talepleri taban ile özdeş olmalıdır](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines) [bağlantı talepleri](/dotnet/framework/misc/link-demands)
