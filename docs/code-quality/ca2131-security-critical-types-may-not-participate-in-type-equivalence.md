---
title: 'CA2131: Güvenlik kritik türleri tür eşdeğerliğine katılamaz'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6e7033416a9941cadaec8b250bee0717b5fa265a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131: Güvenlik kritik türleri tür eşdeğerliğine katılamaz
|||
|-|-|
|TypeName|CriticalTypesMustNotParticipateInTypeEquivalence|
|CheckId|CA2131|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Tür denkliği ve bir ya da türde bir türü katılmakta ya da bir üye ya da alan türü ile işaretlenmiş <xref:System.Security.SecurityCriticalAttribute> özniteliği.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural, herhangi kritik türler veya kritik yöntemleri içeren türler veya tür eşdeğerliğine katılan alanlar tetiklendiğinde başlatılır. Bu tür bir türü CLR algıladığında, ile yüklemek başarısız bir <xref:System.TypeLoadException> çalışma zamanında. Tipik olarak bu kural, kullanıcılar tlbimp'e güvenmek yerine el ile tür eşdeğerliği uyguladığında başlar ve derleyiciler tür eşdeğerliği yapar.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için SecurityCritical özniteliği kaldırın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnekler, bir arabirim, yöntemi ve bu kural yangın neden olacak bir alan gösterir.

 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Güvenliği saydam kod, Düzey 2](/dotnet/framework/misc/security-transparent-code-level-2)