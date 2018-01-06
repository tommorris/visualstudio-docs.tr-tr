---
title: "CA2151: Kritik türler içeren alanlar güvenlik açısından kritik olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09db9d25-7d58-4725-a252-4a07baadf046
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 76a763e2adcf8af588d08a9cd443a4eaf6e36e0c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2151-fields-with-critical-types-should-be-security-critical"></a>CA2151: Kritik türler içeren alanlar güvenlik açısından kritik olmalıdır
|||  
|-|-|  
|TypeName||  
|CheckId|CA2151|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Güvenlik saydam alanı veya güvenli kritik alanı bildirilir. Türü güvenlik açısından kritik olarak belirtilir. Örneğin:  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers]  
  
   [SecurityCritical]  
   class Type1 { } // Security Critical type  
  
   class Type2 // Security transparent type  
   {  
      Type1 m_field; // CA2151, transparent field of critical type  
   }  
  
```  
  
 Bu örnekte, `m_field` güvenlik saydam güvenlik açısından kritik olan bir türde bir alandır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kritik güvenlik türlerini kullanmak için türe başvuran kod güvenliği kritik veya güvenlik güvenli kritik olmalıdır. Dolaylı başvuru olsa bile bu doğrudur. Örneğin, kritik bir türü olan saydam alana başvuru yaptığınızda, kodunuz güvenlik açısından kritik veya güvenlik güvenli olmalıdır. Bu nedenle, bir güvenlik saydam veya güvenlik güvenli kritik alana erişmek mümkün olmayacaktır, çünkü saydam kod hala alana erişemeyecektir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için alanıyla işaretlemek <xref:System.Security.SecurityCriticalAttribute> özniteliği ya da alan eith güvenlik saydam veya güvenli tarafından başvurulan türünün kritik olmasını sağlayın.  
  
```csharp  
// Fix 1: Make the referencing field security critical  
[assembly: AllowPartiallyTrustedCallers]  
  
   [SecurityCritical]  
   class Type1 { } // Security Critical type  
  
   class Type2 // Security transparent type  
   {  
      [SecurityCritical]  
      Type1 m_field; // Fixed: critical type, critical field  
   }  
  
// Fix 2: Make the referencing field security critical  
[assembly: AllowPartiallyTrustedCallers]  
  
   class Type1 { } // Type1 is now transparent  
  
   class Type2 // Security transparent type  
   {  
      [SecurityCritical]  
      Type1 m_field; // Fixed: critical type, critical field  
   }  
  
```  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2151-fields-with-critical-types-should-be-security-critical_1.cs)]  
  
### <a name="comments"></a>Açıklamalar