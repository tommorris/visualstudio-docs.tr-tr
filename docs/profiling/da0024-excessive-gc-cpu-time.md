---
title: 'DA0024: Aşırı GC CPU süresi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0024
- vs.performance.24
- vs.performance.rules.DA0024
ms.assetid: 228872da-77d0-4da5-b455-ac57fb1867c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9abd80ff9d29c558f50eef0f80ad46e868180596
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766122"
---
# <a name="da0024-excessive-gc-cpu-time"></a>DA0024: Aşırı GC CPU süresi
|||  
|-|-|  
|Kural Kimliği|DA0024|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|GC % zamanı çok yüksek. Çöp toplama yükünü aşırı miktarda yoktur.|  
|Kural türü|Uyarı|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma sırasında toplanan sistem performans verileri, toplam uygulama işleme zamanı ile karşılaştırıldığında, çöp toplama harcanan süre miktarını aşırı yüksek olduğunu gösterir.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Microsoft .NET ortak dil çalışma zamanı (CLR) uygulama artık kullanır nesneleri belleği geri almasını atık toplayıcı kullanan bir otomatik bellek yönetimi mekanizması sağlar. Çöp toplayıcı nesil odaklı birçok ayırmaları kısa süreli duymadığını ' dir. Yerel değişkenler, örneğin, kısa süreli olmalıdır. Yeni oluşturulan nesneleri oluşturma 0 (gen 0) başlatın ve bunlar uygulama hala bunları kullanıyorsa, ne zaman bunlar bir atık toplama çalıştırın ve son olarak 2. nesil geçiş varlığını sürdürmesini 1. nesil için ilerleme durumu.  
  
 Kuşak 0 nesnelerinin sık ve genellikle çok verimli bir şekilde toplanır. 1. nesil nesneler daha az sıklıkta ve daha az verimli bir şekilde toplanır. Son olarak, 2. nesil uzun süreli nesneleri bile daha az sıklıkta toplanan. Çalıştır tam atık toplama olduğundan, 2. nesil koleksiyonu da en pahalı bir işlemdir.  
  
 Çöp toplama harcanan süre miktarını toplam uygulama işleme süresi ile karşılaştırıldığında aşırı yüksek olduğunda bu kural ateşlenir.  
  
> [!NOTE]
>  Çöp Toplama süresi oranını zaman harcanan önemlidir, ancak değil aşırı toplam uygulama işleme süresi ile karşılaştırıldığında [DA0023: yüksek GC CPU süresi](../profiling/da0023-high-gc-cpu-time.md) yerine bu kural uyarı etkinleşir.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için Hata Listesi penceresi iletisinde çift [işaretleri Görünüm](../profiling/marks-view.md) profil oluşturma veri. Bul **.NET CLR bellek\\% GC zamanı** sütun. Olup olmadığını program yürütme belirli aşamaları yönetilen bellek çöp toplama yükü diğer aşamalar ağır olduğu belirler. % GC zamanı değerlerini çöp toplama oranını değer karşılaştırma bildirilen **# Gen 0 koleksiyonları**, **# Gen 1 koleksiyonları**, **# Gen 2 koleksiyonları** değerleri .  
  
 % GC değerindeki zamanı uygulamanın gerçekleştirme çöp toplama işleme toplam miktarı için orantılı geçirdiği süreyi rapor dener. Bazı durumlarda % GC değerindeki zamanı yüksek bir değer bildirebilirsiniz, ancak aşırı çöp toplama nedeniyle değil unutmayın. % GC değerindeki zamanı hesaplanan biçimi hakkında daha fazla bilgi için bkz: [fark arasındaki performans verileri tarafından bildirilen farklı araçları - 4](http://go.microsoft.com/fwlink/?LinkId=177863) girişi **Maoni'nın blog** MSDN'de. Sayfa hataları oluşan ya da uygulama diğer daha yüksek öncelik iş makinedeki tarafından çöp toplama sırasında biterse, % GC sayaçtaki zamanı bu ek gecikmeler yansıtır.