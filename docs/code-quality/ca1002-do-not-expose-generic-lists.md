---
title: "CA1002: genel listeleri gösterme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotExposeGenericLists
- CA1002
helpviewer_keywords:
- CA1002
- DoNotExposeGenericLists
ms.assetid: 5caac810-1a79-47df-a27b-c46c5040bf34
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d98b088b663eca89b04ea264a582a062d324a473
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1002-do-not-expose-generic-lists"></a>CA1002: Genel listeleri gösterme
|||  
|-|-|  
|TypeName|DoNotExposeGenericLists|  
|CheckId|CA1002|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir türü olan bir harici olarak görünür üyeyi içeren bir <xref:System.Collections.Generic.List%601?displayProperty=fullName> türü, döndürür bir <xref:System.Collections.Generic.List%601?displayProperty=fullName> türü veya, imza içeren bir <xref:System.Collections.Generic.List%601?displayProperty=fullName> parametresi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Collections.Generic.List%601?displayProperty=fullName>Performans ve değil devralma için tasarlanmış genel bir koleksiyonudur. <xref:System.Collections.Generic.List%601?displayProperty=fullName>daha kolay devralınan bir sınıf davranışını değiştirmek için sanal üye içermiyor. Aşağıdaki genel koleksiyonlar için devralma tasarlanmıştır ve yerine açılmamalıdır <xref:System.Collections.Generic.List%601?displayProperty=fullName>.  
  
-   <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>  
  
-   <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için değiştirme <xref:System.Collections.Generic.List%601?displayProperty=fullName> devralma için tasarlanmış genel koleksiyonlar birine türü.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarı vereceğini derleme yeniden kullanılabilir bir kitaplık düşünülmemiştir sürece bu kuraldan bir uyarı bastırma değil. Örneğin, bu performans avantajı genel listeleri kullanımdan burada elde ayarlanmış performans uygulamasında bu uyarıyı gizlemek güvenli olacaktır.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](/dotnet/csharp/programming-guide/generics/index)