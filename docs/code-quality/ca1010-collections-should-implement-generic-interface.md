---
title: "CA1010: Koleksiyonlar genel arabirim uygulamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
helpviewer_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f0cefdb203011a24769b5b180a442d22a90d0b5c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010: Koleksiyonlar genel arabirim uygulamalıdır
|||  
|-|-|  
|TypeName|CollectionsShouldImplementGenericInterface|  
|CheckId|CA1010|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Harici olarak görünen bir türü uygulayan <xref:System.Collections.IEnumerable?displayProperty=fullName> arabirim ancak uygulamayan <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> arabirimi ve içeren derleme hedefleri [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]. Bu kural uygulama türleri yoksayar <xref:System.Collections.IDictionary?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir koleksiyon kullanılabilirliğini genişletmek için genel koleksiyon arabirimlerinden birini uygulayın. Ardından koleksiyonu, aşağıdaki gibi genel koleksiyon türleri doldurmak için kullanılabilir:  
  
-   <xref:System.Collections.Generic.List%601?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için aşağıdaki genel koleksiyon arabirimleri birini uygulayın:  
  
-   <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.IList%601?displayProperty=fullName>  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan gizlemek güvenlidir; Ancak, koleksiyon daha kısıtlı kullanım sahip olur.  
  
## <a name="example-violation"></a>Örnek ihlali  
  
### <a name="description"></a>Açıklama  
 Genel olmayan türeyen bir sınıf (başvuru türü) aşağıdaki örnekte `CollectionBase` bu kuralını ihlal eden sınıf.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]  
  
### <a name="comments"></a>Açıklamalar  
 Bu ihlali ihlal düzeltmek için genel arabirimler uygulamak ya da zaten hem genel hem de genel olmayan arabirimleri gibi uygulayan bir tür için temel sınıf değiştirmek `Collection<T>` sınıfı.  
  
## <a name="fix-by-base-class-change"></a>Taban sınıfı değişiklikten Düzelt  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek genel olmayan koleksiyon temel sınıfını değiştirerek ihlali giderir `CollectionBase` genel sınıfına `Collection<T>` (`Collection(Of T)` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) sınıfı.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]  
  
### <a name="comments"></a>Açıklamalar  
 Zaten yayımlanmış bir sınıfın temel sınıf değiştirme varolan tüketiciye önemli bir değişiklik olarak kabul edilir.  
  
## <a name="fix-by-interface-implementation"></a>Arabirim uygulaması tarafından Düzelt  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnekte bu genel arabirimler uygulayarak ihlali giderir: `IEnumerable<T>`, `ICollection<T>`, ve `IList<T>` (`IEnumerable(Of T)`, `ICollection(Of T)`, ve `IList(Of T)` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1000: Genel türlerde statik üyeleri bildirme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: üye imzalarında genel türleri geçirmeyin](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: Genel yöntemler tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel türler](/dotnet/csharp/programming-guide/generics/index)