---
title: 'DA0011: Pahalı CompareTo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0011
- vs.performance.rules.DAExpensiveCompareTo
- vs.performance.11
- vs.performance.rules.DA0011
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f7ef867fc40a93948e4de4f5410609ef03aff19
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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