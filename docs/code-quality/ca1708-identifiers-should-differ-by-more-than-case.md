---
title: "CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5ed0b47255fb34f50b79913e8ce417c29302f10b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır
|||  
|-|-|  
|TypeName|IdentifiersShouldDifferByMoreThanCase|  
|CheckId|CA1708|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Küçük harfe dönüştürüldüğünde iki tür, üyeler, parametreleri ya da tam ad alanları adlarını aynıdır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Ortak dil çalışma zamanı hedef dilleri büyük/küçük harf duyarlı olması gerekmediğinden ad alanları, türler, üyeler ve parametreler için tanımlayıcılar yalnızca büyük/küçük harfe göre farklılık göstermeyebilir. Örneğin, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] yaygın olarak kullanılan bir büyük küçük harf duyarsız dildir.  
  
 Bu kural yalnızca herkese görünür üyelere ateşlenir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Büyük küçük harf duyarsız bir biçimde diğer tanımlayıcıları ile karşılaştırıldığında, benzersiz bir ad seçin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Kitaplık tüm kullanılabilir dilde kullanılamayabilir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
## <a name="example-of-a-violation"></a>Bir ihlali örneği  
 Aşağıdaki örnek, bu kural ihlal gösterir.  
  
 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)