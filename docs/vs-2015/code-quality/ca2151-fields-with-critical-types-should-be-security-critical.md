---
title: 'CA2151: Kritik türler içeren alanlar güvenlik açısından kritik olmalıdır. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09db9d25-7d58-4725-a252-4a07baadf046
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c2ce99a404dacdbcc82c628f8f682c53883948ff
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546229"
---
# <a name="ca2151-fields-with-critical-types-should-be-security-critical"></a>CA2151: Kritik türler içeren alanlar güvenlik açısından kritik olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2151: kritik türler içeren alanlar güvenlik açısından kritik olmalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca2151-fields-with-critical-types-should-be-security-critical).

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

 Bu örnekte, `m_field` güvenlik açısından kritik olan bir türü bir güvenlik saydam alanı.

## <a name="rule-description"></a>Kural Tanımı
 Kritik güvenlik türlerini kullanmak için türe başvuran kod güvenliği kritik veya güvenlik güvenli kritik olmalıdır. Dolaylı başvuru olsa bile bu doğrudur. Örneğin, kritik bir türü olan saydam alana başvuru yaptığınızda, kodunuz güvenlik açısından kritik veya güvenlik güvenli olmalıdır. Bu nedenle, bir güvenlik saydam veya güvenlik güvenli kritik alana erişmek mümkün olmayacaktır, çünkü saydam kod hala alana erişemeyecektir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için işaretleyin <xref:System.Security.SecurityCriticalAttribute> özniteliği veya kritik alan güvenlik tarafından saydam veya güvenli başvurulan türü yapın.

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
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2145.transparentmethodsshouldnotusesuppressunmanagedcodesecurity/cs/ca2145.cs#1)]

### <a name="comments"></a>Açıklamalar



