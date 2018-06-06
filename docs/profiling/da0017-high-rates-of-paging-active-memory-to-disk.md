---
title: 'DA0017: diske etkin bellek Sayfalaması yüksek hızda | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.17
- vs.performance.rules.DA0017
- vs.performance.DA0017
ms.assetid: 01011eec-5930-43b3-980d-2cb01e2ca7f6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 60dfbba96a7b52ff271e1633528cf0934e347b6e
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749849"
---
# <a name="da0017-high-rates-of-paging-active-memory-to-disk"></a>DA0017: Yüksek oranda diske etkin bellek sayfalaması gerçekleşiyor.
|||  
|-|-|  
|Kural Kimliği|DA0017|  
|Kategori|Bellek ve disk belleği|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Yüksek oranda diske etkin bellek Sayfalaması oluşmalıdır. Uygulamanızı bellek bağlı olabilir.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma Çalıştır toplanan sistem performans verileri için ve diskten etkin bellek Sayfalaması bir yüksek oranda çalıştırmak profil boyunca oluştuğunu gösterir. Disk belleği oranları bu düzeyde normalde uygulama performansı ve yanıt hızını etkiler. Bellek ayırma algoritmaları düzeltilmesi tarafından azaltmayı deneyin. Uygulamanızın bellek gereksinimleri göz önünde bulundurun gerekebilir.  
  
## <a name="rule-description"></a>Kural açıklaması  
  
> [!NOTE]
>  Etkin bellek disk belleği düzeylerini önemli ölçüde ulaştığında bilgilendirme kuralın ateşlenir. Disk belleği son derece yüksek bir düzeyde meydana geldiğinde, uyarı kuralı [DA0014: aşırı yüksek hızda diske etkin bellek Sayfalaması](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md) yerine ateşlenir.  
  
 Aşırı disk belleği diske fiziksel bellek yetersizliği tarafından neden olabilir. Disk belleği dosyasının bulunduğu fiziksel disk kullanımını sayfalandırma işlemleri baskındır varsa, bunlar aynı diske diğer uygulama odaklı disk işlemleri yavaşlatabilir.  
  
 Sayfaları genellikle diskten okunan veya diske toplu sayfalandırma işlemleri içinde yazılmış. Çıkarılan Sayfa/sn genellikle çok sayısıdır sayfa Yazma/sn, örneğin sayısından büyük. Çıkarılan Sayfa/sn sistem dosya önbelleğinden değiştirilen veri sayfaları da içerdiği için. Bununla birlikte, her zaman için disk belleği doğrudan sorumlu olan işlemi belirlemek kolay değildir veya neden.  
  
## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl  
 Gitmek için hata listesi penceresini iletisinde çift [işaretleri](../profiling/marks-view.md) görünümü. Bul **Bellek\Sayfa/sn** sütun. Olup olmadığını program yürütme belirli aşamaları g/ç etkinliği disk belleği diğerlerinden daha ağır olduğu belirler.  
  
 Bir yük testi senaryosunda bir ASP.NET uygulaması için profil verileri toplama, ek fiziksel bellek (veya RAM) ile yapılandırılmış bir makinede yük testi tekrar çalıştırmayı deneyin.  
  
 Bellek ayırma algoritmaları düzeltilmesi ve bellek kullanımı yoğun API'leri String.Concat ve String.Substring gibi önleme azaltmayı deneyin.