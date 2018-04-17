---
title: 'CA2231: ValueType.Equals geçersiz kılma üzerinde aşırı işleci eşittir | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
- OverrideOperatorEqualsOnOverridingValueTypeEquals
helpviewer_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 881b3d9761f19b4e8364f585480d8b055d076a38
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231: ValueType.Equals değerini geçersiz kılmada eşittir işlecini aşırı yükle
|||  
|-|-|  
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|  
|CheckId|CA2231|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Değer türü geçersiz kılmaları <xref:System.Object.Equals%2A?displayProperty=fullName> ancak eşitlik işleci uygulamaz.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Çoğu programlama dillerinde hiçbir değer türleri için eşitlik işleci (==) varsayılan uygulaması yoktur. Programlama diliniz işlecin destekliyorsa, eşitlik işleci uygulama düşünmelisiniz. Davranışını olarak aynı olmalıdır <xref:System.Object.Equals%2A>.  
  
 Varsayılan eşitlik işleci aşırı yüklenmiş bir eşitlik işleci uygulamasında kullanamazsınız. Bunun yapılması bir yığın taşması neden olur. Eşitlik işleci uygulamak için uygulamanızda Object.Equals yöntemini kullanın. Örneğin:  
  
```vb  
If (Object.ReferenceEquals(left, Nothing)) Then  
    Return Object.ReferenceEquals(right, Nothing)  
Else  
    Return left.Equals(right)  
End If  
```  
  
```csharp  
if (Object.ReferenceEquals(left, null))   
    return Object.ReferenceEquals(right, null);  
return left.Equals(right);  
```  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için eşitlik işleci uygulayın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan gizlemek güvenlidir; Ancak, mümkünse eşitlik işleci sağlamanızı öneririz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal eden bir türü tanımlar.  
  
 [!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../code-quality/codesnippet/CSharp/ca2231-overload-operator-equals-on-overriding-valuetype-equals_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1046: Başvuru türlerinde eşittir işleçlerini aşırı yüklemeyin](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: İşleç aşırı yüklemeleri adlandırılmış alternatiflere sahiptir](../code-quality/ca2225-operator-overloads-have-named-alternates.md)  
  
 [CA2226: İşleçler simetrik aşırı yüklemelere sahip olmalıdır](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)  
  
 [CA2224: Eşittir işlecini aşırı yükleyerek eşittiri geçersiz kılın](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2218: GetHashCode'u Eşittir'i geçersiz kılarak geçersiz kılın](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Object.Equals%2A?displayProperty=fullName>