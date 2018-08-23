---
title: 'CA2143: Saydam yöntemler güvenlik taleplerini kullanmamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 91d54d7b8376d5abd0916516bdd9e8049744a37d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696065"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143: Saydam yöntemler güvenlik taleplerini kullanmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2143: saydam yöntemler güvenlik taleplerini kullanmamanız](https://docs.microsoft.com/visualstudio/code-quality/ca2143-transparent-methods-should-not-use-security-demands).  
  
TypeName | TransparentMethodsShouldNotDemand |  
| Checkıd | CA2143 |  
| Kategori | Microsoft.Security|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir logoyu türün veya yöntemin bildirimli olarak ile işaretlenen bir <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand` isteğe bağlı veya yöntem çağrılarını <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> yöntemi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Saydam güvenlik kodu, bir işlemin güvenlik doğrulaması için sorumlu olmamalıdır ve bu nedenle izin talep edilmemelidir. Saydam güvenlik kodu, güvenlik kararını vermek için tüm talepleri kullanmalıdır ve güvenli kritik kod, saydam koda tüm talepleri vermek için güvenmemelidir. Bunun yerine bir güvenlik talebi gibi güvenlik denetimleri gerçekleştirir herhangi bir kod güvenli kritik olmalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Genel olarak, bu kural ihlalini düzeltmek için yöntemi işaretlemek <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği. Ayrıca, isteğe bağlı kaldırabilirsiniz.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Kural aşağıdaki koda dosyaları bir bildirim temelli güvenlik talebi saydam bir yöntem sağlar.  
  
 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2143.transparentmethodsshouldnotdemand/cs/ca2143 - transparentmethodsshouldnotdemand.cs#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2142: Saydam kod LinkDemands ile korunmamalıdır](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)



