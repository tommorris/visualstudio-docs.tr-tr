---
title: 'CA2135: Düzey 2 derlemeler LinkDemands içermemelidir | Microsoft Docs'
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
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3222004e07ddcef6eb40e5894a566ad12f1b0b68
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634116"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: Düzey 2 derlemeler LinkDemands içermemelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2135: Düzey 2 derlemeler LinkDemands içermemelidir](https://docs.microsoft.com/visualstudio/code-quality/ca2135-level-2-assemblies-should-not-contain-linkdemands).  
  
TypeName | SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands |  
| Checkıd | CA2135 |  
| Kategori | Microsoft.Security|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir sınıf veya sınıf üyesi kullanarak bir <xref:System.Security.Permissions.SecurityAction> uygulamada Düzey 2 güvenlik kullanıyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 LinkDemands, düzey 2 güvenlik kural kümesinden kaldırılmıştır. Just-ın-time (JIT) derleme zamanında güvenliği zorlayan LinkDemands kullanmak yerine, yöntemleri, türleri ve alanlarını ile işaretle <xref:System.Security.SecurityCriticalAttribute> özniteliği.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için kaldırmak <xref:System.Security.Permissions.SecurityAction> ve türe veya üyeye ile işaretleyin <xref:System.Security.SecurityCriticalAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, <xref:System.Security.Permissions.SecurityAction> kaldırılmalıdır ve yöntem ile işaretlenmiş <xref:System.Security.SecurityCriticalAttribute> özniteliği.  
  
 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2135.securityrulesetlevel2methodsshouldnotbeprotectedwithlinkdemands/cs/ca2135 - securityrulesetlevel2methodsshouldnotbeprotectedwithlinkdemands.cs#1)]



