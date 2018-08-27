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
ms.openlocfilehash: ee836af1ee0030c3eea56e12ea5fe767c4b7255b
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902005"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Bakımı yapılamayan kodlardan kaçının
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1505: kodlardan kaçının](https://docs.microsoft.com/visualstudio/code-quality/ca1505-avoid-unmaintainable-code).

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|Kategori|Microsoft.Maintainability|
|Yeni Değişiklik|Bölünemez|

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
 [Bakım uyarıları](../code-quality/maintainability-warnings.md) [ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



