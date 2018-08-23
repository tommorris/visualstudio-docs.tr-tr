---
title: 'CA1716: Tanımlayıcılar, anahtar sözcükler ile eşleşmemelidir | Microsoft Docs'
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
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f3d83fcf02f8467fe6552420146ce106677fdcfd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694642"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Tanımlayıcılar anahtar sözcüklerle eşleşmemelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1716: tanımlayıcılar anahtar sözcükler değil eşleşmelidir](https://docs.microsoft.com/visualstudio/code-quality/ca1716-identifiers-should-not-match-keywords).  
  
TypeName | IdentifiersShouldNotMatchKeywords |  
| Checkıd | CA1716 |  
| Kategori | Microsoft.Naming|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir ad alanı, bir tür veya viritual veya arabirim üye adı ayrılmış bir anahtar sözcük bir programlama dili ile eşleşir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Tanımlayıcı ad alanları, türler, için ve sanal ve arabirim üyeleri olmayan ortak dil çalışma zamanını hedefleyen diller tarafından tanımlanan anahtar sözcükleri eşleşmelidir. Kullanılan dil ve anahtar sözcüğü bağlı olarak, derleyici hataları ve belirsizlikler kitaplığı kullanmak zorlaştırabilir.  
  
 Bu kural, anahtar sözcükleri şu dillerde karşı denetler:  
  
-   Visual Basic  
  
-   C#  
  
-   C++/CLI  
  
 Büyük küçük harf duyarsız bir karşılaştırma için kullanılan [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] anahtar sözcükleri ve büyük küçük harfe duyarlı karşılaştırma diğer diller için kullanılır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Anahtar sözcükler listesinde görünmeyen bir adı seçin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Tanımlayıcı kullanıcılara API'nin karıştırır değil ve kitaplık tüm kullanılabilir dilde kullanılabilir olduğunu ikna varsa bu kuraldan bir uyarıyı bastırmak [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].



