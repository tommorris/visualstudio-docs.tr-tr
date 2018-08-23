---
title: 'CA1043: Dizin oluşturucular için tamsayı veya dize bağımsız değişkeni kullanın. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 92e527f895a2dde1f422ab95f8a1ead2585e4e74
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688955"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: Dizin oluşturucular için tamsayı veya dize bağımsız değişkeni kullanın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1043: Dizin oluşturucular için tamsayı veya dize bağımsız değişkeni kullanın](https://docs.microsoft.com/visualstudio/code-quality/ca1043-use-integral-or-string-argument-for-indexers).  
  
TypeName | UseIntegralOrStringArgumentForIndexers |  
| Checkıd | CA1043 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Ortak veya korumalı tür dışındaki bir dizin türü kullanan bir ortak veya korumalı dizin oluşturucu içeren <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, veya <xref:System.String?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Dizin Oluşturucular, diğer bir deyişle, Dizinlenmiş özelliklere dizin için tamsayı veya dize türleri kullanmalıdır. Bu türler, genellikle veri yapılarını dizinleme için kullanılır ve kitaplığın kullanılabilirliğini artırın. Kullanım <xref:System.Object> türü burada belirli bir tamsayı veya dize türü belirtilemez tasarım zamanında, bu gibi durumlarda sınırlı olmalıdır. Tasarım dizini diğer türleri gerektiriyorsa, bir mantıksal veri deposu türü temsil edip etmediğini yeniden belirleyin. Bir mantıksal veri deposunu temsil etmez, bir yöntem kullanın.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için dizini bir tamsayı veya dize türü değiştirmek veya bir yöntem yerine dizin oluşturucuyu kullanın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Standart olmayan bir dizin oluşturucu için gereken dikkatle ele sonra yalnızca bu kuraldan bir uyarıyı gizler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir dizin oluşturucu kullanan gösterir. bir <xref:System.Int32> dizini.  
  
 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/cpp/FxCop.Design.IntegralOrStringIndexers.cpp#1)]
 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/cs/FxCop.Design.IntegralOrStringIndexers.cs#1)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.IntegralOrStringIndexers/vb/FxCop.Design.IntegralOrStringIndexers.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1023: Dizin oluşturucular çok boyutlu olmamalıdır](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)  
  
 [CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)



