---
title: 'CA2133: Temsilciler tutarlı saydamlığı olan yöntemlere bağlanmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 389de424c3d9e2cd0e12431e857983b267213f9c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31920925"
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