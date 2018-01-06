---
title: "CA1006: üye imzalarında genel türleri iç içe | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotNestGenericTypesInMemberSignatures
- CA1006
helpviewer_keywords:
- CA1006
- DoNotNestGenericTypesInMemberSignatures
ms.assetid: dfc867bc-f4af-45d7-b071-db04a248f9fc
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cd72555ff9877c9142057f04b9ff5881a4fe5932
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1006-do-not-nest-generic-types-in-member-signatures"></a>CA1006: Üye imzalarında genel türleri iç içe kullanmayın
|||  
|-|-|  
|TypeName|DoNotNestGenericTypesInMemberSignatures|  
|CheckId|CA1006|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür bir üye iç içe geçmiş tür bağımsız değişkeni içeren bir imza içeriyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir yuvalanmış bağımsız değişken aynı zamanda genel tip olan bir tip bağımsız değişkendir. Yuvalanmış tip bağımsız değişkeni içeren imzası olan bir üye çağırmak için, kullanıcı bir genel tipi örneklemeli ve bu tipi ikinci bir genel tipin yapıcısına geçirmelidir. Gerekli yordam ve sözdizimi karmaşıktır ve kaçınılmalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için iç içe geçmiş tür bağımsız değişkeni kaldırmak için tasarım değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Genel türler anlamak ve kullanmak kolay bir sözdiziminde sağlama öğrenmek için gerekli olan ve yeni kitaplıklar benimseme oranı artırır süreyi azaltır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir yöntem ve ihlal eden yöntemini çağırmak için gerekli sözdizimi gösterilmektedir.  
  
 [!code-vb[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/VisualBasic/ca1006-do-not-nest-generic-types-in-member-signatures_1.vb)]
 [!code-csharp[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/CSharp/ca1006-do-not-nest-generic-types-in-member-signatures_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](/dotnet/csharp/programming-guide/generics/index)