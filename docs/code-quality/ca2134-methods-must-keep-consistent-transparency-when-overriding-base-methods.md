---
title: 'CA2134: Yöntemler taban yöntemleri geçersiz kılarken tutarlı saydamlığı tutmalıdır'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e74eee5098b23d5e0adf94259aa6ce0b9f2f423e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: Yöntemler taban yöntemleri geçersiz kılarken tutarlı saydamlığı tutmalıdır
|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bu kural bir yöntem ile işaretlendiğinde harekete <xref:System.Security.SecurityCriticalAttribute> saydam veya ile işaretli bir yöntem geçersiz kılmaları <xref:System.Security.SecuritySafeCriticalAttribute>. Saydam veya ile işaretli bir yöntem, kural da ateşlenir <xref:System.Security.SecuritySafeCriticalAttribute> ile işaretli bir yöntem geçersiz kılan bir <xref:System.Security.SecurityCriticalAttribute>.

 Bu kural, sanal bir yöntemi geçersiz kılarken veya bir arabirim uygulanırken uygulanır.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural bir yöntemi daha fazla devralma zincirini güvenlik erişilebilirliğini değiştirme girişimleri üzerinde ateşlenir. Saydam veya güvenli kritik bir taban sınıf içinde sanal bir yöntem ise, örneğin, ardından türetilmiş sınıf onu saydam veya güvenli kritik yöntemiyle geçersiz kılmanız gerekir. Sanal güvenlik açısından kritik ise, buna karşılık, türetilmiş sınıf, bir güvenlik kritik yöntemi ile geçersiz kılmanız gerekir. Aynı kural arabirim yöntemleri uygulamak için geçerlidir.

 Böylece saydamlık hesaplama dinamik tür bilgileri yok kodu yerine çalışma zamanında derlenen JIT olduğunda saydamlık kurallar zorlanır. Bu nedenle, saydamlık hesaplamanın sonucu yalnızca JIT-derlenmiş dinamik türü ne olursa olsun, olan statik türlerinden belirlenemedi olmalıdır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için sanal bir yöntem geçersiz kılma veya sanal saydamlığını veya arabirim yöntemi eşleşecek şekilde arabirimi uygulama yöntemi saydamlığını değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıları bastırma değil. Bu kural ihlalleri, çalışma zamanı'nda sonuçlanacak <xref:System.TypeLoadException> Düzey 2 saydamlık kullanmak derlemeler için.

## <a name="examples"></a>Örnekler

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Güvenliği saydam kod, Düzey 2](/dotnet/framework/misc/security-transparent-code-level-2)