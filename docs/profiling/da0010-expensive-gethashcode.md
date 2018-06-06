---
title: 'DA0010: Pahalı GetHashCode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAExpensiveGetHashCode
- vs.performance.DA0010
- vs.performance.rules.DA0010
- vs.performance.10
ms.assetid: 3987e21a-5b4f-45e4-8a33-6b3f0a472c08
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a670eb3145f3fd2ab9478dc68e0490cdeda8ac56
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749966"
---
# <a name="da0010-expensive-gethashcode"></a>DA0010: Pahalı GetHashCode
|||  
|-|-|  
|Kural Kimliği|DA0010|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Örnekleme<br /><br /> .NET bellek|  
|İleti|GetHashCode işlevleri, ucuz ve tüm belleği ayırmaya değil. Karma kod işlevi karmaşıklığını mümkünse azaltın.|  
|İleti türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma verileri önemli bir kısmının türü GetHashCode yöntemi çağrıları aynıdır veya yöntemi bellek ayırır.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Karma, hızlı bir şekilde büyük bir koleksiyondaki belirli bir öğe bulmak için bir tekniktir. Karma tabloları büyük ve çok yüksek hızda erişim desteklemek zorunda olduğundan, karma tabloları verimli olması gerekir. Bu gereksinim, bir uygulanır, .NET Framework'teki GetHashCode yöntemleri bellek ayırmanız değil ' dir. Bellek ayırma atık toplayıcı üzerindeki yükü artırır ve atık toplama ayırma isteğinin sonucu olarak çalıştırmak gerekli hale gelirse olası gecikmelere yöntemi gösterir.  
  
## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl  
 Yöntem karmaşıklığını azaltın.