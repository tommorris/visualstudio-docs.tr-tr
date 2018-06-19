---
title: 'CA2143: Saydam yöntemler güvenlik taleplerini kullanmamalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e6e4bad795ccf89b36d4fc6a12b29ba4ada7fbb9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917586"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143: Saydam yöntemler güvenlik taleplerini kullanmamalıdır
|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Tranparent türü veya yöntemi bildirimli olarak işaretlenmiş bir <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand` isteğe bağlı veya yöntem çağrılarını <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> yöntemi.

## <a name="rule-description"></a>Kural Tanımı
 Saydam güvenlik kodu, bir işlemin güvenlik doğrulaması için sorumlu olmamalıdır ve bu nedenle izin talep edilmemelidir. Saydam güvenlik kodu, güvenlik kararını vermek için tüm talepleri kullanmalıdır ve güvenli kritik kod, saydam koda tüm talepleri vermek için güvenmemelidir. Güvenlik taleplerini gibi güvenlik denetimleri gerçekleştirir herhangi bir kod, bunun yerine güvenli kritik olmalıdır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Genel olarak, bu kural ihlal düzeltmek için yöntemiyle işaretlemek <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği. Ayrıca, isteğe bağlı kaldırabilirsiniz.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Kural aşağıdaki kod dosyaları bildirimsel güvenliği isteğe bağlı saydam bir yöntem sağlar.

 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 [CA2142: Saydam kod LinkDemands ile korunmamalıdır](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)