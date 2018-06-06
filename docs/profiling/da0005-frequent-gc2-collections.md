---
title: 'DA0005: Sık sık kullanılan GC2 koleksiyonları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0005
- vs.performance.rules.DAManyGC2Collections
- vs.performance.5
- vs.performance.rules.DA0005
ms.assetid: 8d3f267c-8a74-4cf4-91a5-0b06a76dc2bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 697a060399fa17321f30ccb92ad3617e99ca106f
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749339"
---
# <a name="da0005-frequent-gc2-collections"></a>DA0005: Sık kullanılan GC2 koleksiyonları
|||  
|-|-|  
|RuleId|DA0005|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemi|.NET bellek|  
|İleti|Birçok nesnelerinin nesil 2 çöp toplama toplanmakta olan.|  
|İleti türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Çok sayıda .NET bellek nesneleri nesil 2 çöp toplama kazanılır.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Microsoft .NET ortak dil çalışma zamanı (CLR) uygulama artık kullanır nesneleri belleği geri almasını atık toplayıcı kullanan bir otomatik bellek yönetimi mekanizması sağlar. Çöp toplayıcı nesil odaklı birçok ayırmaları kısa süreli duymadığını ' dir. Yerel değişkenler, örneğin, kısa süreli olmalıdır. Yeni oluşturulan nesneleri oluşturma 0 (gen 0) başlatın ve bunlar uygulama hala bunları kullanıyorsa, ne zaman bunlar bir atık toplama çalıştırın ve son olarak 2. nesil geçiş varlığını sürdürmesini 1. nesil için ilerleme durumu.  
  
 Kuşak 0 nesnelerinin sık ve genellikle çok verimli bir şekilde toplanır. 1. nesil nesneler daha az sıklıkta ve daha az verimli bir şekilde toplanır. Son olarak, 2. nesil uzun süreli nesneleri bile daha az sıklıkta toplanan. Çalıştır tam atık toplama olduğundan, 2. nesil koleksiyonu da en pahalı bir işlemdir.  
  
 Bu kuralın ne zaman orantılı olarak 2 çöp koleksiyonları oluşan çok sayıda oluşturma başlatılır. Çok fazla görece kısa süreli nesne 1. nesil koleksiyonu varlığını sürdürmesini ancak 2. nesil tam koleksiyonunda toplanmasını mümkün, bellek yönetimi maliyetini kolayca aşırı haline gelebilir. Daha fazla bilgi için bkz: [Orta yaşam kriz](http://go.microsoft.com/fwlink/?LinkId=177835) sonrası Riko Mariani's performans ipuçları MSDN Web sitesinde üzerinde.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gözden geçirme [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md) bellek ayırma uygulama desenini anlamak için raporlar. Kullanım [nesne ömrü görünümü](../profiling/object-lifetime-view.md) 2. nesil ve buradan sonra geri nesneleri geri kalan hangi programın veri belirleme. Kullanım [ayırmalar görünümü](../profiling/dotnet-memory-allocations-view.md) bu ayırma sonuçlandı yürütme yolu belirlenemedi.  
  
 Çöp toplama performansı hakkında daha fazla bilgi için bkz: [atık toplayıcı temel kavramları ve performans ipuçları](http://go.microsoft.com/fwlink/?LinkId=148226) Microsoft Web sitesinde. Otomatik çöp toplama yükü hakkında daha fazla bilgi için bkz: [büyük nesne yığın bitişik](http://go.microsoft.com/fwlink/?LinkId=177836).