---
title: 'DA0012: Önemli miktarda yansıma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAReflection
- vs.performance.12
- vs.performance.rules.DA0012
- vs.performance.DA0011
ms.assetid: c92a1d76-21fa-426e-8b1b-a3c08e9bcbca
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c5a5982fd194f86d2cfe2b63a564c0ce1ce90f8a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749833"
---
# <a name="da0012-significant-amount-of-reflection"></a>DA0012: Önemli miktarda Yansıma
|||  
|-|-|  
|Kural Kimliği|DA0012|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Örnekleme|  
|İleti|Yansıma aşırı kullanıyor olabilir. Bu pahalı bir işlemdir.|  
|Kural türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma verileri önemli bir kısmının çağrıları InvokeMember ve GetMember gibi System.Reflection yöntemleri veya MemberInvoke gibi türü yöntemleri için aynıdır. Mümkün olduğunda, bu yöntemleri bağımlı derlemeleri yöntemleri için erken bağlama değiştirerek göz önünde bulundurun.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Yansıma, uygulamanızın bağımlı bir çalışma zamanı derleme geç bağlama gerçekleştirmek ya da oluşturmak ve yeni türleri çalışma zamanı sırasında dinamik olarak çalıştırmak için kullanılan .NET Framework'ün esnek bir özelliğidir. Ancak, sık kullanılan veya sıkı Döngülerde adlı bu teknikler performansı düşürebilir.  
  
 Daha fazla bilgi için bkz: [yansıma ve geç bağlama](http://go.microsoft.com/fwlink/?LinkId=177826) bölüm 5 bölümünü — geliştirme yönetilen kod performans Microsoft Patterns and Practices geliştirme .NET uygulama performansı ve ölçeklenebilirliği hacmi MSDN Kitaplığı.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için Hata Listesi penceresi iletisinde çift [işlev Ayrıntıları görünümü](../profiling/function-details-view.md) profil oluşturma veri. İşlevleri çağırma .NET yansıma API'lerini en sık rastlanan kullanılmasını sağlamak program bölümlerini bulmak için System.Type veya System.Reflection yönteminin inceleyin. Meta veri döndüren yöntemler kullanmaktan kaçının. Uygulamanızın performansını önemli olduğunda geç bağlama ve çalışma zamanında dinamik olarak türleri oluşturma kullanmaktan kaçının gerekebilir.