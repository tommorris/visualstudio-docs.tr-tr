---
title: "DA0011: Pahalı CompareTo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0011
- vs.performance.rules.DAExpensiveCompareTo
- vs.performance.11
- vs.performance.rules.DA0011
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 197d5402d935d7e1b377b6ec037535fbc2f65cfa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="da0011-expensive-compareto"></a>DA0011: Pahalı CompareTo
|||  
|-|-|  
|Kural Kimliği|DA0011|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Örnekleme<br /><br /> .NET bellek|  
|İleti|CompareTo işlevleri, ucuz ve tüm belleği ayırmaya değil. CompareTo işlevi karmaşıklığını mümkünse azaltın.|  
|Kural türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 CompareTo Yöntemi türü pahalıdır veya bellek ayırır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 CompareTo yöntemleri verimli olması gerekir ve bellek tahsis değil.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 CompareTo Yöntemi karmaşıklığını azaltın.