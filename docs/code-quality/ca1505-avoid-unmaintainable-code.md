---
title: "CA1505: Bakımı yapılamayan kodlardan kaçının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3f31e213d621b64143f17735874238432118fe57
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)