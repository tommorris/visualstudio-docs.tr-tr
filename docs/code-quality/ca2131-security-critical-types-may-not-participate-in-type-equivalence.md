---
title: 'CA2131: Güvenlik kritik türleri tür eşdeğerliğine katılamaz'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 681b2916ef6e6e5c90d98b7a88874a7fb0166549
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546713"
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131: Güvenlik kritik türleri tür eşdeğerliğine katılamaz
|||
|-|-|
|TypeName|CriticalTypesMustNotParticipateInTypeEquivalence|
|CheckId|CA2131|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Tür eşdeğerliği ve bir ya da türün kendisine bir tür katıldığı veya bir üye veya alan türü ile işaretlenmiş <xref:System.Security.SecurityCriticalAttribute> özniteliği.

## <a name="rule-description"></a>Kural açıklaması
 Bu kural, herhangi kritik türler veya kritik yöntemleri içeren türler veya tür eşdeğerliğine katılan alanlar tetiklendiğinde başlatılır. CLR böyle bir türü algıladığında, ile yüklemek başarısız bir <xref:System.TypeLoadException> çalışma zamanında. Tipik olarak bu kural, kullanıcılar tlbimp'e güvenmek yerine el ile tür eşdeğerliği uyguladığında başlar ve derleyiciler tür eşdeğerliği yapar.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Bu kural ihlalini düzeltmek için SecurityCritical özniteliği kaldırın.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnekler, bir arabirim, bir yöntem ve bu kural ateşlenmesine neden olacak bir alanı göstermektedir.

 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]

## <a name="see-also"></a>Ayrıca bkz.
 [Güvenliği saydam kod, Düzey 2](/dotnet/framework/misc/security-transparent-code-level-2)