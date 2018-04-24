---
title: 'DA0014: aşırı yüksek hızda diske etkin bellek Sayfalaması | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAMemoryBound
- vs.performance.DA0014
- vs.performance.14
- vs.performance.rules.DA0014
ms.assetid: a7fa3749-9191-437a-9331-9d917181e62f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1fe54cec0e42161dceb9879264548d5926a0e7c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="da0014-extremely-high-rates-of-paging-active-memory-to-disk"></a>DA0014: Aşırı yüksek oranda diske etkin bellek sayfalaması gerçekleşiyor.
|||  
|-|-|  
|Kural Kimliği|DA0014|  
|Kategori|Bellek ve disk belleği|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Bir son derece yüksek oranda diske etkin bellek Sayfalaması oluşmalıdır. Uygulamanızı bellek bağlı olabilir.|  
|Kural türü|Uyarı|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 25 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma Çalıştır toplanan sistem performans verileri için ve diskten etkin bellek Sayfalaması bir son derece yüksek oranda çalıştırmak profil boyunca oluştuğunu gösterir. Bu düzeyde oranları genellikle disk belleği, uygulama performansı ve yanıt hızını etkiler. Bellek ayırma algoritmaları düzeltilmesi tarafından azaltmayı deneyin. Uygulamanızın bellek gereksinimleri göz önünde bulundurun gerekebilir. Daha fazla belleğe sahip bir bilgisayarda yeniden profil çalışıyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Aşırı disk belleği diske fiziksel bellek yetersizliği tarafından neden olabilir. Disk belleği dosyasının bulunduğu fiziksel disk kullanımını sayfalandırma işlemleri baskındır varsa, bunlar aynı diske diğer uygulama odaklı disk işlemleri yavaşlatabilir.  
  
 Sık sık sayfaları diskten okunan veya diske toplu disk belleği işlemlerinde yazılan. Çıkarılan Sayfa/sn örneğin sık çok sayısından daha büyük sayfa Yazma/sn, sayısıdır. Çıkarılan Sayfa/sn sistem dosya önbelleğinden değiştirilen veri sayfaları da içerdiği için. Bununla birlikte, her zaman için disk belleği doğrudan sorumlu olan işlemi belirlemek kolay değildir veya neden.  
  
> [!NOTE]
>  Bu kural active bellek disk belleği düzeylerini oranı çok yüksek ulaştığında tetikler. Disk belleği düzeyini önemli, ancak değil aşırı olduğunda, bilgilendirici kural [DA0017: yüksek hızda diske etkin bellek Sayfalaması](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md) yerine ateşlenir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Gitmek için hata listesi penceresini iletisinde çift [işaretleri](../profiling/marks-view.md) görünümü. Bul **Bellek\Sayfa/sn** sütun. Olup olmadığını program yürütme belirli aşamaları g/ç etkinliği disk belleği diğerlerinden daha ağır olduğu belirler.  
  
 Bir yük testi senaryosunda bir ASP.NET uygulaması için profil verileri toplama, ek fiziksel bellek (veya RAM) ile yapılandırılmış bir makinede yük testi tekrar çalıştırmayı deneyin.  
  
 Bellek ayırma algoritmaları düzeltilmesi ve bellek kullanımı yoğun API'leri String.Concat ve String.Substring gibi önleme azaltmayı deneyin.