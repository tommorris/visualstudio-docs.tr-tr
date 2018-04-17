---
title: 'DA0013: Yüksek kullanım String.Split veya String.Substring kullanımı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 6fd50e084753e57793447e6cf3bc5c1c3f070e80
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 Profil oluşturma verileri önemli bir kısmını System.String.Split veya System.String.Substring yöntemi çağrıları aynıdır. Bir alt dizesi dize varlığı için sınıyorsanız System.String.IndexOf veya System.String.IndexOfAny kullanmayı düşünün.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Split yöntemini bir dize nesnesi üzerinde çalışır ve özgün alt dizeler içeren yeni bir dizi dizisini döndürür. İşlev verilen dizi nesnesi için bellek ayırır ve bulduğu her dizi öğesi için yeni bir dize nesnesi ayırır. Benzer şekilde, Substr yöntemi bir dize nesnesi üzerinde çalışır ve istenen alt dizeyi eşdeğer olan yeni bir dize döndürür.  
  
 Bellek ayırma yönetme uygulamanızda kritik öneme sahipse String.Split ve String.Substr yöntemleri alternatifleri kullanmayı düşünün. Örneğin, dize sınıfının yeni bir örneğini oluşturmak zorunda kalmadan bir karakter dizesi içinde belirli bir alt dizeyi bulmak için IndexOf veya IndexOfAny yöntemi kullanabilirsiniz.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için hata listesi penceresini iletisinde çift [işlev Ayrıntıları görünümü](../profiling/function-details-view.md) örnekleme, profil verileri. En sık rastlanan System.String.Split veya System.String.Substr yöntemi kullanılmasını sağlamak program bölümlerini bulmak için arama işlevleri inceleyin. Mümkünse, dize sınıfının yeni bir örneğini oluşturmak zorunda kalmadan bir karakter dizesi içindeki belirli bir alt dizenin bulmak için IndexOf veya IndexOfAny yöntemi kullanın.