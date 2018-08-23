---
title: 'CA1505: kodlardan kaçının | Microsoft Docs'
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
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 158b833acc2405335ba76f29163837925bd25ebc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687305"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Bakımı yapılamayan kodlardan kaçının
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1505: kodlardan kaçının](https://docs.microsoft.com/visualstudio/code-quality/ca1505-avoid-unmaintainable-code).  
  
TypeName | AvoidUnmantainableCode |  
| Checkıd | CA1505 |  
| Kategori | Microsoft.Maintainability|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Bir tür veya yöntemin düşük bakım dizin değeri vardır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bakım dizini aşağıdaki ölçümleri kullanarak hesaplanır: kod, programın toplu ve döngüzel karmaşıklığına satır. Programın toplu bir türün veya yöntemin işleçler ve işlenenleri kodda sayısını temel alan bir anlayış zorluk ölçüsüdür. Döngüsel karmaşıklık yapısal türü veya yönteminde karmaşıklığını ölçüsüdür. Kod ölçümleri hakkında daha fazla bilgi [ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md).  
  
 Düşük bakım dizini bir türün veya yöntemin korumak muhtemelen koruması zor olan ve yeniden tasarlamanız için iyi bir aday olabilir gösterir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu ihlali gidermek için tür veya yöntem yeniden tasarlayın ve daha küçük ve daha fazla odaklanmış türleri veya yöntemleri bölmek deneyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarı, bir türün veya yöntemin hala en büyük boyutuna rağmen veya türü veya yönteminde bölünemez sürdürülebilir edildiği durumlarda hariç tutun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bakım uyarıları](../code-quality/maintainability-warnings.md)   
 [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



