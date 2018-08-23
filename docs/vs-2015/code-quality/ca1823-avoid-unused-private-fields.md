---
title: 'CA1823: kullanılmayan özel alanlardan kaçının | Microsoft Docs'
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
- AvoidUnusedPrivateFields
- CA1823
helpviewer_keywords:
- AvoidUnusedPrivateFields
- CA1823
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 306c587daa63089114d2bceefda42b064f8cc6fc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682420"
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823: Kullanılmayan özel alanlardan kaçının
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1823: kullanılmayan özel alanlardan kaçının](https://docs.microsoft.com/visualstudio/code-quality/ca1823-avoid-unused-private-fields).  
  
TypeName | AvoidUnusedPrivateFields |  
| Checkıd | CA1823 |  
| Kategori | Microsoft.Performance|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Bu kural, kodunuzda bir özel alan var ancak herhangi bir kod yolu tarafından kullanılmayan bildirilir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Derlemede erişimi görülmeyen özel alanlar algılandı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için alanı kaldırın veya onu kullanan kodu ekleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1812: Örneklendirilmemiş iç sınıflardan kaçının](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1801: Kullanılmayan parametreleri gözden geçir](../code-quality/ca1801-review-unused-parameters.md)  
  
 [CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)  
  
 [CA1811: Çağrılmayan özel kodlardan kaçının](../code-quality/ca1811-avoid-uncalled-private-code.md)



