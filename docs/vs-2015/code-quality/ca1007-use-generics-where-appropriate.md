---
title: 'CA1007: uygun yerlerde genel türleri kullanın | Microsoft Docs'
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
- CA1007
- UseGenericsWhereAppropriate
helpviewer_keywords:
- CA1007
- UseGenericsWhereAppropriate
ms.assetid: eab780ea-3b1f-4d32-b15a-5d48da2df46b
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b0fecf0c8221e9e83a42c131e5b77de7beef0c4b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693844"
---
# <a name="ca1007-use-generics-where-appropriate"></a>CA1007: Uygun yerlerde genel türler kullanın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1007: uygun yerlerde genel türleri kullanın](https://docs.microsoft.com/visualstudio/code-quality/ca1007-use-generics-where-appropriate).  
  
TypeName | UseGenericsWhereAppropriate |  
| Checkıd | CA1007 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Türü bir başvuru parametresi dışarıdan görünen bir yöntem içeren <xref:System.Object?displayProperty=fullName>ve içeren derleme hedefleri [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)].  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir başvuru parametresi kullanılarak değiştirilebilir bir parametredir `ref` (`ByRef` içinde [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) anahtar sözcüğü. Bir başvuru parametresi için sağlanan bağımsız değişken türü başvuru parametresi türünü tam olarak eşleşmelidir. Başvuru parametre türünden türetilmiş bir tür kullanmak için türü ilk dönüştürme ve başvuru parametresi türünü bir değişkene atanır. Genel yöntem tüm türleri ve başvuru parametresi türünü türüne atmadan yönteme iletilecek kısıtlamaları, izin verir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için yöntem genel yapın ve Değiştir <xref:System.Object> bir tür parametresini kullanarak parametre.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, jenerik olmayan ve genel yöntemler olarak uygulanan bir genel amaçlı takas yordam gösterir. Jenerik olmayan bir yönteme göre genel yöntemini kullanarak dizeleri nasıl verimli bir şekilde değiştirilir unutmayın.  
  
 [!code-csharp[FxCop.Design.UseGenerics#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.UseGenerics/cs/FxCop.Design.UseGenerics.cs#1)]
 [!code-vb[FxCop.Design.UseGenerics#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.UseGenerics/vb/FxCop.Design.UseGenerics.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](http://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)



