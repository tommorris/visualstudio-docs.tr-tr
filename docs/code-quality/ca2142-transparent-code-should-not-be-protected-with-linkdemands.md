---
title: "CA2142: Saydam kod LinkDemands ile korunmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5d0094d8afa2dcf59efe0aace8514979d73ac921
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: Saydam kod LinkDemands ile korunmamalıdır
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|  
|CheckId|CA2142|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Saydam bir yöntemi gerektiren bir <xref:System.Security.Permissions.SecurityAction> veya diğer güvenlik isteğe bağlı.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, bunlara erişen LinkDemands gerektiren saydam yöntemleri tetikler. Saydam güvenlik kodu, bir işlemin güvenlik doğrulaması için sorumlu olmamalıdır ve bu nedenle izin talep edilmemelidir. Saydam yöntemler güvenlik dilden bağımsız olması gereken çünkü bunlar tüm güvenlik kararları değil. Ayrıca, güvenlik kararlar, güvenli kritik kod böyle bir karar daha önce yaptığınız saydam kod bağlı olan değil.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için saydam yöntemi bağlantı talebe kaldırın veya yöntemiyle işaretlemek <xref:System.Security.SecuritySafeCriticalAttribute> güvenlik yapılıyorsa özniteliği denetimleri, güvenlik taleplerini gibi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, kural harekete yöntemi yöntemi saydam ve LinkDemand ile işaretlenmiş olduğundan <xref:System.Security.PermissionSet> içeren bir <xref:System.Security.Permissions.SecurityAction>.  
  
 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]  
  
 Bu kuraldan uyarıyı bastırmayın.