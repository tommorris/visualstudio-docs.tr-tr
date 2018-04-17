---
title: 'Nasıl yapılır: satır düzeyi örnekleme verileri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, line-level sampling
ms.assetid: 44803aad-dd39-4c2e-9209-d35185d44983
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 582a17e0a373bde99f17a077c17313ea5b7dfe56
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-collect-line-level-sampling-data"></a>Nasıl yapılır: Satır Düzeyi Örnekleme Verileri Toplama
Satır düzeyi örnekleme yüksek özel örnekleri olan bir işlev gibi bir işlemci yoğunluğu işlevinin kodda işlemci, süreyi en çok harcama sahip olduğu belirlemek için profil oluşturucu özelliğidir.  
  
## <a name="overview"></a>Genel Bakış  
 Satır düzeyi örnekleme için profil oluşturucu programı çağrı yığını belirlenen aralıklarla anlatılmaktadır ve bu sonuçları toplar. Bu sonuçları örnekleri durumdayken işlemci yürütülmekte olan hangi yönergeleri gösterir. Özel örnekleri hakkında toplanan verileri ardından satırları kod ve yönerge işaretçisi (IP) belirlemek için analiz edilir.  
  
 Satır düzeyi örnekleme yönetilen yanı sıra yerel kod için çalışır. Satırlar görünümü ve modüller görünümü bu verileri görüntülemek performans raporları içerir.  
  
 Karakter begin/bitiş bilgileri yerel kod için kullanılabilir değil. Çok satırlı deyimleri için satırın başında bilgileri yerel kod için; mevcut değil yalnızca satır sonu bilgisi yok.  
  
### <a name="available-data"></a>Kullanılabilir veri  
 Kullanılabilir satır düzeyi örnekleme verileri aşağıdaki bilgileri içerir:  
  
-   İşlev adı.  
  
-   İşlev adresi.  
  
-   Satırın başında - örneklenen kodu satır sayısı.  
  
-   Satır sonu - kaynak satır numarasını bitiş. Bu genellikle tek bir program deyimde birden çok kaynak kodu satır yayıldığında dışında "Satırın başında" veri aynıdır.  
  
-   Karakter başlamalı - birleşik örnek başlangıç sütunu. Bu genellikle tek bir satıra birden fazla program deyimleri içerdiğinde dışında 0'dır.  
  
-   Karakter son - birleşik örnek sütununun bitiş.  
  
-   IP - birleşik örnek (yalnızca IP görünümü) burada alındığı adresi.  
  
 İçinde **modülleri** görüntülemek için bir işlev satır düzeyi istatistikleri varsa, altında her işlevi istatistikleri yerleştirilir. Ayrıca, her satırın altında iç içe geçmiş IP düzeyi istatistikleri sunulur.  
  
### <a name="turn-off-line-level-sampling-for-managed-code"></a>Yönetilen kod için satır düzeyi örnekleme devre dışı bırakma  
 Varsayılan olarak, satır düzeyi örnekleme açıktır. Aşağıdakilerden birini yaparak yönetilen kod için satır düzeyi verilerin toplanmasını kapatabilirsiniz:  
  
-   Profil oluşturma önce yazın **VSPerfCLREnv /samplelineoff**. Bu uygulamalar ve hizmetler etkiler.  
  
     — veya —  
  
-   Bir uygulama başlatılırken yazın **VSPerfCmd /lineoff \<başka bir bağımsız değişken >**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Araçları verilerini performansını analiz etme](../profiling/analyzing-performance-tools-data.md)