---
title: 'CA1505: Bakımı yapılamayan kodlardan kaçının'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b65e6c8c7826887e411b2210b613633c1e963aaf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Bakımı yapılamayan kodlardan kaçının
|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|Kategori|Microsoft.Maintainability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir tür veya yöntemin düşük bakım dizin değeri vardır.

## <a name="rule-description"></a>Kural Tanımı
 Bakım dizini aşağıdaki ölçümleri kullanılarak hesaplanır: satırları program birim ve cyclomatic karmaşıklık kodu. Program, bir ölçü türü veya işleçler ve kodda işlenenler sayısına dayalı yöntemi anlayış zorluk birimdir. Cyclomatic karmaşıklık yapısal türü veya yöntemi karmaşıklığını ölçüsüdür. Kod ölçümleri hakkında daha fazla bilgi edinebilirsiniz [ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md).

 Düşük bakım dizin türü veya yöntemi korumak büyük olasılıkla zordur ve yeniden tasarlamanız için iyi bir aday olacağını gösterir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu ihlali düzeltmek için türü veya yöntemi yeniden tasarlamanız ve daha küçük ve daha odaklı türleri veya yöntemleri bölmek deneyin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu uyarı türü veya yöntemi hala büyük boyutuna rağmen veya türü veya yöntemi bölünemez sürdürülebilir olarak kabul edildiğinde dışlayın.

## <a name="see-also"></a>Ayrıca Bkz.
 [Bakım uyarıları](../code-quality/maintainability-warnings.md) [ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)