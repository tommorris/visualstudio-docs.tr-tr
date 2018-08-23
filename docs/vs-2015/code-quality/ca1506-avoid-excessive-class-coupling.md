---
title: 'CA1506: aşırı sınıf bağlantısından kaçının | Microsoft Docs'
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
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1611c1861b9961fd953d63cb4d45a5c4e3b276db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674762"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Aşırı sınıf bağlantısından kaçın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1506: aşırı sınıf bağlantısından kaçının](https://docs.microsoft.com/visualstudio/code-quality/ca1506-avoid-excessive-class-coupling).  
  
TypeName | AvoidExcessiveClassCoupling |  
| Checkıd | CA1506 |  
| Kategori | Microsoft.Maintainability|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir türün veya yöntemin birçok diğer türleri ile birleştirilmiştir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural türü veya yöntemini içeren benzersiz türde başvuru sayısı belirlenerek eşlenmesiyle sınıfı ölçer.  
  
 Türler ve bir sınıf bağlantısı yüksek ölçüde içeren yöntemlerin bakımını yapmak zor olabilir. Türler ve düşük eşleştirme ve yüksek uyum göstermesi yöntemler için iyi bir uygulamadır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu ihlali gidermek için tür veya yöntem bağlı türler sayısını azaltmak için yeniden tasarlayabilir deneyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarı, tür veya yöntem hala rağmen bağımlılıklar diğer türleri üzerinde çok fazla sürdürülebilir edildiği durumlarda hariç tutun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bakım uyarıları](../code-quality/maintainability-warnings.md)   
 [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



