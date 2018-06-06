---
title: 'DA0013: Yüksek kullanım String.Split veya String.Substring kullanımı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.13
- vs.performance.rules.DAAvoidStringSubstr
- vs.performance.DA0013
- vs.performance.rules.DA0013
helpviewer_keywords:
- vs.performance.13
- vs.performance.rules.DA0013
ms.assetid: f501f423-bef9-4e08-bf96-c9ac9957e5a2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c218dd9a7ee3266de2cf9e07933ed69aa23e73e7
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749888"
---
# <a name="da0013-high-usage-of-stringsplit-or-stringsubstring"></a>DA0013: Yüksek oranda String.Split veya String.Substring kullanımı
|||  
|-|-|  
|Kural Kimliği|DA0013|  
|Kategori|.NET framework Kullanım Kılavuzu|  
|Profil oluşturma yöntemleri|Örnekleme|  
|İleti|String.Split veya String.Substring işlevindeki kullanımını azaltmayı deneyin.|  
|Kural türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma verileri önemli bir kısmını System.String.Split veya System.String.Substring yöntemi çağrıları aynıdır. Bir alt dizesi dize varlığı için test ediyorsanız System.String.IndexOf veya System.String.IndexOfAny kullanmayı düşünün.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Split yöntemini bir dize nesnesi üzerinde çalışır ve özgün alt dizeler tutan yeni dizeler dizisi döndürür. İşlev verilen dizi nesnesi için bellek ayırır ve bulduğu her dizi öğesi için yeni bir dize nesnesi ayırır. Benzer şekilde, Substr yöntemi bir dize nesnesi üzerinde çalışır ve istenen alt dizeyi eşdeğer olan yeni bir dize döndürür.  
  
 Bellek ayırma yönetme uygulamanızda kritik öneme sahipse String.Split ve String.Substr yöntemleri alternatifleri kullanmayı düşünün. Örneğin, dize sınıfının yeni bir örneğini oluşturmak zorunda kalmadan bir karakter dizesi içinde belirli bir alt dizeyi bulmak için IndexOf veya IndexOfAny yöntemini kullanabilirsiniz.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 İletide çift **hata listesi** gitmek için pencere [işlev Ayrıntıları görünümü](../profiling/function-details-view.md) örnekleme, profil verileri. En sık rastlanan System.String.Split veya System.String.Substr yöntemi kullanılmasını sağlamak program bölümlerini bulmak için arama işlevleri inceleyin. Mümkünse, dize sınıfının yeni bir örneğini oluşturmak zorunda kalmadan bir karakter dizesi içinde belirli bir alt dizeyi bulmak için IndexOf veya IndexOfAny yöntemini kullanın.