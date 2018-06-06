---
title: 'DA0023: Yüksek GC CPU süresi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0023
- vs.performance.23
- vs.performance.rules.DA0023
ms.assetid: aba875fe-9cbc-418d-a2c4-6eb47519a5bb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 26b5296dcbd2630d70bae91c539df36a30e97722
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750148"
---
# <a name="da0023-high-gc-cpu-time"></a>DA0023: Yüksek GC CPU süresi
|||  
|-|-|  
|Kural Kimliği|DA0023|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|GC % zaman oldukça yüksektir. Çöp toplama yükünü aşırı miktarda bu göstergesi, uygulamanızın yanıtlama etkileyen. Uygulamanızın daha iyi kullandığı bellek ayırma desenini anlamak için .NET bellek ayırma veri ve nesne yaşam süresi bilgileri toplayabilir.|  
|Kural türü|Bilgi|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma sırasında toplanan sistem performans verileri, toplam uygulama işleme süresi ile karşılaştırıldığında, çöp toplama harcanan süreyi önemli olduğunu gösterir.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Microsoft .NET ortak dil çalışma zamanı (CLR) uygulama artık kullanır nesneleri belleği geri almasını atık toplayıcı kullanan bir otomatik bellek yönetimi mekanizması sağlar. Çöp toplayıcı nesil odaklı birçok ayırmaları kısa süreli duymadığını ' dir. Yerel değişkenler, örneğin, kısa süreli olmalıdır. Yeni oluşturulan nesneleri oluşturma 0 (gen 0) başlatın ve bunlar uygulama hala bunları kullanıyorsa, ne zaman bunlar bir atık toplama çalıştırın ve son olarak 2. nesil geçiş varlığını sürdürmesini 1. nesil için ilerleme durumu.  
  
 Kuşak 0 nesnelerinin sık ve verimli bir şekilde toplanır. 1. nesil nesneler daha az sıklıkta ve daha az verimli bir şekilde toplanır. Son olarak, 2. nesil uzun süreli nesneleri bile daha az sıklıkta toplanan. Çalıştır tam atık toplama olduğundan, 2. nesil koleksiyonu da en pahalı bir işlemdir.  
  
 Çöp toplama harcanan süreyi toplam uygulama işleme zamanı ile karşılaştırıldığında önemli olduğunda bu kural ateşlenir.  
  
> [!NOTE]
>  Çöp toplama harcanan zamanı oranını aşırı olduğunda toplam uygulama işleme zamanı ile karşılaştırıldığında [DA0024: aşırı GC CPU süresi](../profiling/da0024-excessive-gc-cpu-time.md) yerine bu kural uyarı etkinleşir.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için Hata Listesi penceresi iletisinde çift [işaretleri Görünüm](../profiling/marks-view.md) profil oluşturma veri. Bul **.NET CLR bellek\\% GC zamanı** sütun. Olup olmadığını program yürütme belirli aşamaları yönetilen bellek çöp toplama yükü diğer aşamalar ağır olduğu belirler. % GC zamanı değerlerini çöp toplama oranını değer karşılaştırma bildirilen **# Gen 0 koleksiyonları**, **# Gen 1 koleksiyonları**, **# Gen 2 koleksiyonları** değerleri .  
  
 % GC değerindeki zamanı uygulamanın gerçekleştirme çöp toplama işleme toplam miktarı için orantılı geçirdiği süreyi rapor dener. Bazı durumlarda % GC değerindeki zamanı yüksek bir değer raporlayabilirsiniz ancak aşırı çöp toplama nedeniyle değil unutmayın. % GC değerindeki zamanı hesaplanan biçimi hakkında daha fazla bilgi için bkz: [fark arasındaki performans verileri tarafından bildirilen farklı araçları - 4](http://go.microsoft.com/fwlink/?LinkId=177863) girişi **Maoni'nın blog** MSDN'de. Sayfa hataları yaşanan veya uygulama tarafından diğer daha yüksek öncelik iş makinedeki çöp toplama sırasında geçersiz kılınırsa, GC sayaç zamanında % bu ek gecikmeler yansıtır.