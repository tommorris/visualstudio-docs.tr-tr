---
title: "CA1023: Dizin oluşturucular çok boyutlu olmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2a3cf9ecfc25fc14fafceb1f36d8a02756e739b8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023: Dizin oluşturucular çok boyutlu olmamalıdır
|||  
|-|-|  
|TypeName|IndexersShouldNotBeMultidimensional|  
|CheckId|CA1023|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir genel ya da korumalı türü birden fazla dizin kullanan bir ortak veya korumalı dizin oluşturucu içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Dizin Oluşturucular, diğer bir deyişle, Dizinli Özellikler tek bir dizin kullanmanız gerekir. Çok boyutlu dizin oluşturucular kitaplığı kullanılabilirliğini önemli ölçüde azaltabilir. Tasarım birden çok dizin gerektiriyorsa, bir mantıksal veri deposu türü temsil eder olup olmadığını alan. Aksi durumda, bir yöntem kullanın.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için bir silmenizin tamsayı veya dize dizini kullanmak için tasarım değiştirin veya dizin oluşturucu yerine bir yöntem kullanın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Standart olmayan dizin oluşturucu gereksinimini dikkatle düşünüldükten sonra yalnızca bu kural bir uyarıdan engelleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `DayOfWeek03`, kural ihlal çok boyutlu bir dizin oluşturucu ile. Dizin Oluşturucu dönüştürme bir tür olarak görülebilir ve bu nedenle daha uygun bir yöntem olarak kullanıma sunulur. Türü de yeniden tasarlanmıştır `RedesignedDayOfWeek03` kural karşılamak için.  
  
 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/VisualBasic/ca1023-indexers-should-not-be-multidimensional_1.vb)]
 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CPP/ca1023-indexers-should-not-be-multidimensional_1.cpp)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CSharp/ca1023-indexers-should-not-be-multidimensional_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1043: Dizin oluşturucular için tamsayı veya dize bağımsız değişkeni kullanın](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)  
  
 [CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)