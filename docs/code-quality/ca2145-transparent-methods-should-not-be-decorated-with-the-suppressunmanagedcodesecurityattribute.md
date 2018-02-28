---
title: "CA2145: Saydam yöntemler SuppressUnmanagedCodeSecurityAttribute ile donatılmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c6fcfc32dc8ab8a90ea555f43c253a5d93e72a3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145: Saydam yöntemler SuppressUnmanagedCodeSecurityAttribute ile donatılmamalıdır
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|  
|CheckId|CA2145|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Saydam bir yöntemi, ile işaretli bir yöntem <xref:System.Security.SecuritySafeCriticalAttribute> yöntemi ya da bir yöntem içeren bir türü ile işaretlenmiş <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Yöntemleri donatılmış ile <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> özniteliğine sahip çağıran herhangi bir yöntemini yerleştirilen bir örtük LinkDemand. Bu LinkDemand, çağıran kodun kritik güvenlikli olmasını gerektirir. İle SuppressUnmanagedCodeSecurity kullandığı yöntem işaretleme <xref:System.Security.SecurityCriticalAttribute> özniteliği yapar bu gereksinim daha belirgin yöntemini arayanlar için.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yöntemini işaretlemek veya ile yazın <xref:System.Security.SecurityCriticalAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]  
  
### <a name="comments"></a>Açıklamalar