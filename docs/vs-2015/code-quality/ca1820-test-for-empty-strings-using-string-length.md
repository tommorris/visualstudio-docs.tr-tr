---
title: 'CA1820: Dize uzunluğunu kullanarak boş dizeler için sınayın | Microsoft Docs'
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
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 448d5dfd7c3e0b26291cf51e3d8d7dcf6c73d2e5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689440"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820: Dize uzunluğunu kullanarak boş dizeler için sınayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1820: dize uzunluğunu kullanarak boş dizeleri Test](https://docs.microsoft.com/visualstudio/code-quality/ca1820-test-for-empty-strings-using-string-length).  
  
TypeName | TestForEmptyStringsUsingStringLength |  
| Checkıd | CA1820 |  
| Kategori | Microsoft.Performance|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Bir dize kullanarak boş bir dize karşılaştırma <xref:System.Object.Equals%2A?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Karşılaştırma dizeleri kullanarak <xref:System.String.Length%2A?displayProperty=fullName> özelliği veya <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> yöntemdir kullanılmasından önemli ölçüde daha hızlı <xref:System.Object.Equals%2A>. Bunun nedeni, <xref:System.Object.Equals%2A> ya da daha fazla MSIL yönergeleri yürüten <xref:System.String.IsNullOrEmpty%2A> veya yönerge almak için yürütülen sayısını <xref:System.String.Length%2A> özellik değer ve sıfır olarak karşılaştırır.  
  
 Bilmeniz gereken, <xref:System.Object.Equals%2A> ve <xref:System.String.Length%2A> == 0 null dizeler için farklı davranır. Değeri alınacak çalışırsanız <xref:System.String.Length%2A> boş bir dize özelliği, ortak dil çalışma zamanı oluşturur bir <xref:System.NullReferenceException?displayProperty=fullName>. Boş bir dize ve boş bir dize arasında bir karşılaştırma gerçekleştirmek, ortak dil çalışma zamanı bir özel durum oluşturmaz; Karşılaştırma döndürür `false`. Null sınaması, bu iki yaklaşımı göreli performansını önemli ölçüde etkilemez. Hedeflenirken [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], kullanın <xref:System.String.IsNullOrEmpty%2A> yöntemi. Aksi takdirde kullanın <xref:System.String.Length%2A> karşılaştırma mümkün olduğunca ==.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için kullanılacak karşılaştırma değiştirme <xref:System.String.Length%2A> özelliği ve test için boş bir dize. Hedefleme, [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], kullanın <xref:System.String.IsNullOrEmpty%2A> yöntemi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Performans sorunu değilse bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, boş bir dize aramak için kullanılan farklı teknikleri gösterir.  
  
 [!code-csharp[FxCop.Performance.StringTest#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.StringTest/cs/FxCop.Performance.StringTest.cs#1)]



