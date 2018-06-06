---
title: 'DA0022: Yüksek oranda Gen 2 çöp koleksiyonları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0022
- vs.performance.rules.DA0022
- vs.performance.22
ms.assetid: f871a547-0e6f-4b11-b2d7-174d30fc2ed8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bb8cf383008a45fee678b6d52909e14c4f060f1b
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750408"
---
# <a name="da0022-high-rate-of-gen-2-garbage-collections"></a>DA0022: Yüksek oranda Gen 2 çöp koleksiyonları
|||  
|-|-|  
|Kural Kimliği|DA0022|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Oldukça yüksek oranda Gen 2 çöp koleksiyonları gerçekleşen yoktur. Tasarım gereği, programınızın veri yapılarını çoğunu ayrılmasını ve uzun bir süredir kalıcı varsa, bu genellikle bir sorun değildir. Ancak, bu istenmeyen bir davranıştır, uygulamanızın nesneleri sabitleme. Emin değilseniz, uygulamanızın kullandığı bellek ayırma desenini anlamak için .NET bellek ayırma veri ve nesne yaşam süresi bilgileri toplayabilir.|  
|Kural türü|Uyarı|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 2. nesil nesil 0 karşılaştırıldığında çöp toplama ve nesil 1 çöp koleksiyonları içinde bellek for.NET Framework nesneleri önemli bir kısmının geri profil oluşturma sırasında toplanan sistem performans verilerini gösterir.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Microsoft .NET ortak dil çalışma zamanı (CLR) uygulama artık kullanır nesneleri belleği geri almasını atık toplayıcı kullanan bir otomatik bellek yönetimi mekanizması sağlar. Çöp toplayıcı nesil odaklı birçok ayırmaları kısa süreli duymadığını ' dir. Yerel değişkenler, örneğin, kısa süreli olmalıdır. Yeni oluşturulan nesneleri oluşturma 0 (gen 0) başlatın ve bunlar uygulama hala bunları kullanıyorsa, ne zaman bunlar bir atık toplama çalıştırın ve son olarak 2. nesil geçiş varlığını sürdürmesini 1. nesil için ilerleme durumu.  
  
 Kuşak 0 nesnelerinin sık ve genellikle çok verimli bir şekilde toplanır. 1. nesil nesneler daha az sıklıkta ve daha az verimli bir şekilde toplanır. Son olarak, 2. nesil uzun süreli nesneleri bile daha az sıklıkta toplanan. Çalıştır tam atık toplama olduğundan, 2. nesil koleksiyonu da en pahalı bir işlemdir.  
  
 Bu kuralın ne zaman orantılı olarak çok fazla nesil 2 çöp koleksiyonları yaşanan tetikler. Uyum gösteren .NET Framework uygulamaları birden çok 5 katı nesil 1 çöp koleksiyonları 2. nesil koleksiyon olarak sahip olur. (10 x faktörü büyük olasılıkla idealdir.)  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için Hata Listesi penceresi iletisinde çift [işaretleri Görünüm](../profiling/marks-view.md) profil oluşturma veri. Bul **.NET CLR bellek\\# Gen 0 koleksiyonları** ve **.NET CLR bellek\\# Gen 1 koleksiyonları** sütun. Olup olmadığını program yürütme belirli aşamaları çöp toplama daha sık oluştuğu belirler. Bu değerleri Karşılaştır **% GC zamanı** yönetilen bellek ayırmaları desenini aşırı bellek yönetim yükünü neden olup olmadığını görmek için sütun.  
  
 Yüksek oranda nesil 2 çöp koleksiyonları her zaman bir sorun değildir. Tasarım gereği olabilir. Yürütme sırasında uzun süreyle etkin kalması gereken büyük veri yapılarını ayıran bir uygulama bu kural tetikleyebilir. Bu tür bir uygulama bellek baskısı altında olduğunda, sık atık toplama işlemleri gerçekleştirmek için zorlanabilir. Ucuz kuşak 0 ve 1. kuşak atık toplama işlemleri yalnızca küçük bir miktar yönetilen belleği geri, daha sık nesil 2 çöp koleksiyonları zamanlanacak.  
  
 Çöp toplama sorunları belirlemenize yardımcı olabilir işaretleri görünümünde ek .NET CLR bellek sütunları vardır. **% GC zamanı** sütun ne kadar bellek yönetim yükünü oluştuğunu anlamanıza yardımcı olur. Uygulamanızı genellikle büyük ancak kalıcı nesneler oldukça az sayıda kullanıyorsa, ardından sık 2. nesil koleksiyonları aşırı miktarda CPU süresi tüketmemesi. Daha fazla fiziksel bellek (RAM) değerlendir gereken, ilgili kuralları olduğundan uygulama bellek baskısı altında ise **Bellek\Sayfa/sn** sütun değerleri de yangın.  
  
 Uygulamanın düzeni yönetilen bellek kullanımını anlamak için onu yeniden a.NET bellek ayırma profilini çalıştıran profil ve seçeneği profil nesne ömrü seçin.  
  
 Çöp toplama performansı hakkında daha fazla bilgi için bkz: [atık toplayıcı temel kavramları ve performans ipuçları](http://go.microsoft.com/fwlink/?LinkId=148226) Microsoft Web sitesinde. Otomatik çöp toplama yükü hakkında daha fazla bilgi için bkz: [büyük nesne yığın bitişik](http://go.microsoft.com/fwlink/?LinkId=177836).