---
title: 'CA1505: Bakımı yapılamayan kodlardan kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: 4338b73aab38b1d63f4d4015c3a1fe1e1d292932
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Bakım uyarıları](../code-quality/maintainability-warnings.md)   
 [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)