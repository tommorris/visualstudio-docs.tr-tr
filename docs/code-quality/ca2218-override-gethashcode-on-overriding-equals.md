---
title: "CA2218: gethashcode'u eşittir'i geçersiz kılarak geçersiz kılın | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2218
- OverrideGetHashCodeOnOverridingEquals
helpviewer_keywords:
- OverrideGetHashCodeOnOverridingEquals
- CA2218
ms.assetid: 69b020cd-29e8-45a6-952e-32cf3ce2e21d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a7844f4bc10acabeef81001a0c0890c603410ec5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2218-override-gethashcode-on-overriding-equals"></a>CA2218: GetHashCode'u Eşittir'i geçersiz kılarak geçersiz kılın
|||  
|-|-|  
|TypeName|OverrideGetHashCodeOnOverridingEquals|  
|CheckId|CA2218|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Ortak tür geçersiz kılmaları <xref:System.Object.Equals%2A?displayProperty=fullName> ancak geçersiz <xref:System.Object.GetHashCode%2A?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Object.GetHashCode%2A> karma algoritmaları ve veri yapıları gibi bir karma tablosu için uygun geçerli örnek, temel bir değer döndürür. Aynı türde olan ve eşit olan iki nesne türlerinden birini örnekleri düzgün çalışmasını sağlamak için aynı karma koda döndürmesi gerekir:  
  
-   <xref:System.Collections.Hashtable?displayProperty=fullName>  
  
-   <xref:System.Collections.SortedList?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.HybridDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.ListDictionary?displayProperty=fullName>  
  
-   <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=fullName>  
  
-   Uygulama türleri <xref:System.Collections.Generic.IEqualityComparer%601?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için uygulama sağlayın <xref:System.Object.GetHashCode%2A>. Aynı türde nesneleri çifti için uygulama aynı değeri döndürdüğünü emin olmalısınız uygulamanıza <xref:System.Object.Equals%2A> döndürür `true` çifti için.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="class-example"></a>Sınıf örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, bu kural ihlal eden bir sınıfı (başvuru türü) gösterir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Usage.GetHashCodeErrorClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_1.cs)]  
  
### <a name="comments"></a>Açıklamalar  
 Aşağıdaki örnek, geçersiz kılarak ihlali giderir <xref:System.Object.GetHashCode>.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Usage.GetHashCodeFixedClass#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_2.cs)]  
  
## <a name="structure-example"></a>Yapısı örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, bu kural ihlal eden bir yapı (değer türü) gösterir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Usage.GetHashCodeErrorStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_3.cs)]  
  
### <a name="comments"></a>Açıklamalar  
 Aşağıdaki örnek, geçersiz kılarak ihlali giderir <xref:System.Object.GetHashCode>.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Usage.GetHashCodeFixedStruct#1](../code-quality/codesnippet/CSharp/ca2218-override-gethashcode-on-overriding-equals_4.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1046: Başvuru türlerinde eşittir işleçlerini aşırı yüklemeyin](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: İşleç aşırı yüklemeleri adlandırılmış alternatiflere sahiptir](../code-quality/ca2225-operator-overloads-have-named-alternates.md)  
  
 [CA2226: İşleçler simetrik aşırı yüklemelere sahip olmalıdır](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2224: Eşittir işlecini aşırı yükleyerek eşittiri geçersiz kılın](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2231: ValueType.Equals değerini geçersiz kılmada eşittir işlecini aşırı yükle](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Collections.Hashtable?displayProperty=fullName>   
 [Eşitlik İşleçleri](/dotnet/standard/design-guidelines/equality-operators)