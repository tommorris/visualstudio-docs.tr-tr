---
title: 'CA1043: Dizin oluşturucular için tamsayı veya dize bağımsız değişkeni kullanın'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 91437defeaebddd176dd23732aa40e76522bfeb6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: Dizin oluşturucular için tamsayı veya dize bağımsız değişkeni kullanın
|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir genel ya da korumalı türü dışındaki bir dizin türünü kullanan bir ortak veya korumalı dizin oluşturucu içeren <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, veya <xref:System.String?displayProperty=fullName>.

## <a name="rule-description"></a>Kural Tanımı
 Dizin Oluşturucular, diğer bir deyişle, Dizinli Özellikler tamsayı veya dize türü için dizin kullanmanız gerekir. Bu tür genellikle veri yapılarını dizin oluşturma işlemi için kullanılır ve kitaplık kullanılabilirliğini artırın. Kullanımı <xref:System.Object> türü burada belirli bir tamsayı veya dize türü belirtilemez tasarım zamanında bu gibi durumlarda için kısıtlanmış. Tasarım dizini diğer türleri gerektiriyorsa, bir mantıksal veri deposu türü temsil eder olup olmadığını alan. Bir mantıksal veri deposu göstermiyor bir yöntem kullanın.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için dizin bir tamsayı veya dize türü değiştirin veya dizin oluşturucu yerine bir yöntem kullanın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Standart olmayan dizin oluşturucu gereksinimini dikkatle düşünüldükten sonra yalnızca bu kural bir uyarıdan engelleyin.

## <a name="example"></a>Örnek
 Kullanan bir dizin oluşturucu aşağıdaki örnekte bir <xref:System.Int32> dizini.

 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1023: Dizin oluşturucular çok boyutlu olmamalıdır](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)

 [CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)