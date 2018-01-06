---
title: "CA1005: Genel türlerde aşırı parametrelerden kaçının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3bbf8dae17c9f0fd257388d8520485bf1a5d6970
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005: Genel türlerde aşırı parametrelerden kaçının
|||  
|-|-|  
|TypeName|AvoidExcessiveParametersOnGenericTypes|  
|CheckId|CA1005|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür bir genel tür ikiden fazla tür parametresi var.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Daha çok tip parametresi, genel tip içerir, bilmek daha zordur ve hangi tip parametrelerinin temsil ettiğini anımsamak zordur. Giriş olarak bir tür parametresi ile genellikle belirgin `List<T>`ve bazı durumlarda da olarak iki tür parametreleri ile `Dictionary<TKey, TValue>`. İkiden fazla tür parametreleri varsa zorluk çoğu kullanıcı için çok büyük olur (örneğin, `TooManyTypeParameters<T, K, V>` C# veya `TooManyTypeParameters(Of T, K, V)` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için ikiden fazla tür parametreleri kullanmak için tasarımı değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Tasarım kesinlikle ikiden fazla tür parametreleri gerektirmedikçe bu kuraldan bir uyarı bastırma değil. Genel türler anlamak ve kullanmak kolay bir sözdiziminde sağlama öğrenmek için gerekli olan ve yeni kitaplıklar benimseme oranı artırır süreyi azaltır.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](/dotnet/csharp/programming-guide/generics/index)