---
title: 'DA0021: Yüksek oranda Gen 1 çöp koleksiyonları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.21
- vs.performance.DA0021
- vs.performance.rules.DA0021
ms.assetid: ebf5d9b3-a1ac-4688-8f0f-39a85f4dd15f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5602563c9d9cea9f1500c95f9a7df38a3f4184e3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="da0021-high-rate-of-gen-1-garbage-collections"></a>DA0021: Yüksek oranda Gen 1 çöp koleksiyonları
|||  
|-|-|  
|Kural Kimliği|DA0021|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Tümü|  
|İleti|Oldukça yüksek oranda Gen 1 çöp koleksiyonları gerçekleşen yoktur. Tasarım gereği, programınızın veri yapılarını çoğunu ayrılmasını ve uzun bir süredir kalıcı varsa, bu genellikle bir sorun değildir. Ancak, bu istenmeyen bir davranıştır, uygulamanızın nesneleri sabitleme. Emin değilseniz, uygulamanızın kullandığı bellek ayırma desenini anlamak için .NET bellek ayırma veri ve nesne yaşam süresi bilgileri toplayabilir.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 1. nesil nesil 0 veri koleksiyonuna karşılaştırıldığında atık toplama içinde bellek for.NET Framework nesneleri önemli bir kısmının geri profil oluşturma sırasında toplanan sistem performans verilerini gösterir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Microsoft .NET ortak dil çalışma zamanı (CLR) uygulama artık kullanır nesneleri belleği geri almasını atık toplayıcı kullanan bir otomatik bellek yönetimi mekanizması sağlar. Çöp toplayıcı nesil odaklı birçok ayırmaları kısa süreli duymadığını ' dir. Yerel değişkenler, örneğin, kısa süreli olmalıdır. Yeni oluşturulan nesneleri oluşturma 0 (gen 0) başlatın ve bunlar uygulama hala bunları kullanıyorsa, ne zaman bunlar bir atık toplama çalıştırın ve son olarak 2. nesil geçiş varlığını sürdürmesini 1. nesil için ilerleme durumu.  
  
 Kuşak 0 nesnelerinin sık ve genellikle çok verimli bir şekilde toplanır. 1. nesil nesneler daha az sıklıkta ve daha az verimli bir şekilde toplanır. Son olarak, 2. nesil uzun süreli nesneleri bile daha az sıklıkta toplanan. Çalıştır tam atık toplama olduğundan, 2. nesil koleksiyonu da en pahalı bir işlemdir.  
  
 Bu kuralın ne zaman orantılı olarak 1 çöp koleksiyonları oluşan çok sayıda oluşturma başlatılır. Çok fazla oldukça kısa süreli nesne oluşturma 0 koleksiyonu varlığını sürdürmesini ancak 1. nesil koleksiyonunda toplanmasını mümkün bellek yönetimi maliyetini aşırı hale gelebilir. Daha fazla bilgi için bkz: [Orta yaşam kriz](http://go.microsoft.com/fwlink/?LinkId=177835) sonrası Riko Mariani's performans ipuçları MSDN Web sitesinde üzerinde.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için Hata Listesi penceresi iletisinde çift [işaretleri Görünüm](../profiling/marks-view.md) profil oluşturma veri. Bul **.NET CLR bellek\\# Gen 0 koleksiyonları** ve **.NET CLR bellek\\# Gen 1 koleksiyonları** sütun. Olup olmadığını program yürütme belirli aşamaları çöp toplama daha sık oluştuğu belirler. Bu değerleri Karşılaştır **% GC zamanı** yönetilen bellek ayırmaları desenini aşırı bellek yönetim yükünü neden olup olmadığını görmek için sütun.  
  
 Uygulamanın düzeni yönetilen bellek kullanımını anlamak için yeniden a.NET bellek ayırma profili ve istek nesne ömrü ölçüleri çalışmasını profil.  
  
 Çöp toplama performansı hakkında daha fazla bilgi için bkz: [atık toplayıcı temel kavramları ve performans ipuçları](http://go.microsoft.com/fwlink/?LinkId=148226) Microsoft Web sitesinde. Otomatik çöp toplama yükü hakkında daha fazla bilgi için bkz: [büyük nesne yığın bitişik](http://go.microsoft.com/fwlink/?LinkId=177836).