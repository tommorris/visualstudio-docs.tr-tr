---
title: 'CA2133: Temsilciler tutarlı saydamlığı olan yöntemlere bağlanmalıdır'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eee7b4857f91d4d201b79e0814113b36b03fc151
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133: Temsilciler tutarlı saydamlığı olan yöntemlere bağlanmalıdır
|||
|-|-|
|TypeName|DelegatesMustBindWithConsistentTransparency|
|CheckId|CA2133|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

> [!NOTE]
>  Bu uyarı yalnızca CoreCLR (Silverlight Web uygulamalarına özeldir CLR sürüm) çalıştıran kod uygulanır.

## <a name="cause"></a>Sebep
 Bu uyarı harekete ile işaretli bir temsilci bağlayan bir yöntemde <xref:System.Security.SecurityCriticalAttribute> saydam veya ile işaretlenmiş bir yönteme <xref:System.Security.SecuritySafeCriticalAttribute>. Uyarı, saydam veya kritik bir yöntem için kritik güvenli temsilciyi bağlayan yöntemi de tetikler.

## <a name="rule-description"></a>Kural Tanımı
 Temsilci türleri ve bunlar bağlamak yöntemleri tutarlı saydamlığı olması gerekir. Saydam ve güvenli kritik temsilcileri yalnızca diğer saydam veya güvenli kritik yöntemleri bağlayabilirsiniz. Benzer şekilde, kritik temsilcileri yalnızca kritik yöntemlere bağlayabilirsiniz. Bu bağlama kuralları bir temsilci aracılığıyla bir yöntemi çağırmak yalnızca kod de aynı yöntemi doğrudan emin olun. Örneğin, bağlama kuralları, kritik kodu saydam bir temsilci aracılığıyla doğrudan çağırma saydam kod engeller.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu uyarı ihlal düzeltmek için saydamlığı temsilci veya iki saydamlığını eşdeğer ve böylece bu bağlar yöntemi değiştirebilirsiniz.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2133-delegates-must-bind-to-methods-with-consistent-transparency_1.cs)]