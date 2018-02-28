---
title: "CA2138: Saydam yöntemler SuppressUnmanagedCodeSecurity özniteliğine sahip yöntemleri çağırmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2138
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0cef17ce232582cd23f961850bd52c048479e849
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute"></a>CA2138: Saydam yöntemler SuppressUnmanagedCodeSecurity özniteliğine sahip yöntemleri çağırmamalıdır
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|  
|CheckId|CA2138|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Güvenliği saydam yöntemi ile işaretli bir yöntem çağırır <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural harekete kullanarak doğrudan yerel kod içine, örneğin, çağıran herhangi bir saydam yöntemi üzerinde bir P/Invoke aracılığıyla (platform çağırma) çağırın. İle işaretlenen P/Invoke ve COM birlikte çalışma yöntemlerini <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> özniteliği arama yöntemi karşı gerçekleştirilen LinkDemand sonuçlanır. Güvenliği saydam kod LinkDemands gerçekleştiremiyor çünkü kod ayrıca SuppressUnmanagedCodeSecurity özniteliğiyle işaretlenmiş yöntemler veya yöntemler SuppressUnmanagedCodeSecurity özniteliği ile işaretlenmiş sınıfının çağrılamaz. Yöntem başarısız olur veya isteğe bağlı tam istek dönüştürülür.  
  
 Bu kural ihlalleri neden bir <xref:System.MethodAccessException> Düzey 2 güvenlik saydamlık modeli ve tam bir talep <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> düzey 1 saydamlık modeli.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kaldırmak <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> özniteliği ve yöntemiyle işaretlemek <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../code-quality/codesnippet/CSharp/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute_1.cs)]