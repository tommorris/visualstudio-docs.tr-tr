---
title: 'CA1708: Tanımlayıcılar daha fazla farklı olmalıdır | Microsoft Docs'
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
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 03be4d303ba52e9b3f4e4b8112c4760839f01d8d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683612"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1708: tanımlayıcılar farklı büyük küçük harf](https://docs.microsoft.com/visualstudio/code-quality/ca1708-identifiers-should-differ-by-more-than-case).  
  
TypeName | IdentifiersShouldDifferByMoreThanCase |  
| Checkıd | CA1708 |  
| Kategori | Microsoft.Naming|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 İki tür, üye, parametre veya tam ad alanları adları, küçük harfe dönüştürüldüğünde aynıdır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Ortak dil çalışma zamanı hedef dilleri büyük/küçük harf duyarlı olması gerekmediğinden ad alanları, türler, üyeler ve parametreler için tanımlayıcılar yalnızca büyük/küçük harfe göre farklılık göstermeyebilir. Örneğin, [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] yaygın olarak kullanılan bir büyük küçük harf duyarsız dilidir.  
  
 Bu kural yalnızca herkese görünür üyelere tetikler.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Büyük küçük harf duyarlı bir şekilde diğer tanımlayıcılarla karşılaştırılır, benzersiz bir ad seçin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Kitaplık tüm kullanılabilir dilde kullanılabilir olmayabilir [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].  
  
## <a name="example-of-a-violation"></a>Bir ihlali örneği  
 Aşağıdaki örnek, bu kural ihlalini gösterir.  
  
 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Naming.IdentifiersShouldDifferByMoreThanCase/cs/FxCop.Naming.IdentifiersShouldDifferByMoreThanCase.cs#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)



