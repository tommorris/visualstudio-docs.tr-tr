---
title: 'DA0012: Önemli miktarda yansıma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: a03415695da5f23e6e4f487574376172db9b40f0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
## <a name="rule-description"></a>Kural Tanımı  
 Yansıma, uygulamanızın bağımlı bir çalışma zamanı derleme geç bağlama gerçekleştirmek ya da oluşturmak ve yeni türleri çalışma zamanı sırasında dinamik olarak çalıştırmak için kullanılan .NET Framework'ün esnek bir özelliğidir. Ancak, sık kullanılan veya sıkı Döngülerde adlı bu teknikler performansı düşürebilir.  
  
 Daha fazla bilgi için bkz: [yansıma ve geç bağlama](http://go.microsoft.com/fwlink/?LinkId=177826) bölüm 5 bölümünü — geliştirme yönetilen kod performans Microsoft Patterns and Practices geliştirme .NET uygulama performansı ve ölçeklenebilirliği hacmi MSDN Kitaplığı.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için Hata Listesi penceresi iletisinde çift [işlev Ayrıntıları görünümü](../profiling/function-details-view.md) profil oluşturma veri. İşlevleri çağırma .NET yansıma API'lerini en sık rastlanan kullanılmasını sağlamak program bölümlerini bulmak için System.Type veya System.Reflection yönteminin inceleyin. Meta veri döndüren yöntemler kullanmaktan kaçının. Uygulamanızın performansını önemli olduğunda geç bağlama ve çalışma zamanında dinamik olarak türleri oluşturma kullanmaktan kaçının gerekebilir.