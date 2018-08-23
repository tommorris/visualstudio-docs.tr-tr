---
title: 'CA1724: Tür adları, ad alanları ile eşleşmemelidir | Microsoft Docs'
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
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 437499bd915df4ce8bdd22641435d751670d0cf5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691091"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: Tür Adları Ad Alanlarıyla Eşleşmemelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1724: Tür adları gerektiğini değil eşleşme ad alanları](https://docs.microsoft.com/visualstudio/code-quality/ca1724-type-names-should-not-match-namespaces).  
  
TypeName | TypeNamesShouldNotMatchNamespaces |  
| Checkıd | CA1724 |  
| Kategori | Microsoft.Naming|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir tür adıyla eşleşen bir [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] büyük küçük harf duyarsız bir karşılaştırma ad alanı adları.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Tür adları içinde tanımlı ad alanlarının adları değil eşleşmelidir [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sınıf kitaplığı. Bu kuralın ihlali kitaplığın kullanılabilirliğini azaltabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Belirleyin adı eşleşmiyor bir tür adı bir [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sınıf kitaplığı ad alanı.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yeni geliştirme, hiçbir bilinen senaryolar ortaya burada bu kuraldan bir uyarıyı bastırmak gerekir. Uyarının gösterilmemesi önce kitaplığınızın kullanıcılar tarafından eşleşen adı nasıl yanıltıcı dikkatlice düşünün. Kitaplıkları sevk edilmesi için bu kuraldan bir uyarıyı bastırmak gerekebilir.



