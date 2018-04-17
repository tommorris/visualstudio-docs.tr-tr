---
title: 'CA1046: başvuru türlerinde eşittir işlecini aşırı yüklemeyin | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e78217e2ce8613ca312a96058b4477d1da82a5e7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: Başvuru türlerinde eşittir işleçlerini aşırı yüklemeyin
|||  
|-|-|  
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|  
|CheckId|CA1046|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir genel veya iç içe geçmiş genel başvuru türü eşitlik işleci aşırı yüklemeler.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Başvuru türleri için, varsayılan eşitlik işleci neredeyse her zaman doğrudur. Varsayılan olarak, yalnızca aynı nesneye gelirseniz iki başvuru eşit olur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için eşitlik işleci uyarlamasını kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Başvuru türü bir yerleşik değer türü gibi davranır olduğunda bir uyarı bu kuraldan bastırmak güvenlidir. Ekleme veya çıkarma türü örneklerinde yapmak için anlamlı ise eşitlik işleci uygulamak ve ihlali bastırma muhtemelen doğrudur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki başvuru karşılaştırılırken varsayılan davranış gösterir.  
  
 [!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama bazı başvuruları karşılaştırır.  
  
 [!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_2.cs)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **bir yeni (2,2) ve b = = yeni (2,2) eşit? Yok**  
**c ve eşit bir misiniz? Evet**  
**b ve bir ==? Yok**  
**c ve bir ==? Evet**   
## <a name="related-rules"></a>İlgili kuralları  
 [CA1013: Eşittir işlecini ekleme ve çıkarmayı aşırı yükleyerek aşırı yükleyin](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [Eşitlik İşleçleri](/dotnet/standard/design-guidelines/equality-operators)