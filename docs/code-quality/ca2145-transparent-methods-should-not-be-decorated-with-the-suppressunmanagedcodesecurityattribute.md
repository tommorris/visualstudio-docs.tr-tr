---
title: 'CA2145: Saydam yöntemler SuppressUnmanagedCodeSecurityAttribute ile donatılmamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: e0571656905642b9f8bdd12a93a8aa83256124f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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