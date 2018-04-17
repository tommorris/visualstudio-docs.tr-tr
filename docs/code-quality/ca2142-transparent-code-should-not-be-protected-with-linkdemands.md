---
title: 'CA2142: Saydam kod LinkDemands ile korunmamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c598a6aff671f0ce3ce489a203805e77eda7183
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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