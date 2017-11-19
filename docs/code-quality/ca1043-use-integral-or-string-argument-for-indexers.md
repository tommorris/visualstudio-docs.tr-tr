---
title: "CA1043: Dizin oluşturucular için tamsayı veya dize bağımsız değişkeni kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: aeaaf07dd3590e4dd703cfa239c48cb7e86b7f43
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
  
 [CA1024: uygun yerlerde özellikler kullan](../code-quality/ca1024-use-properties-where-appropriate.md)