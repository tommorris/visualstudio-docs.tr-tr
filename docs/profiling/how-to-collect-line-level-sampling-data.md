---
title: 'Nasıl yapılır: satır düzeyi örnekleme verileri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, line-level sampling
ms.assetid: 44803aad-dd39-4c2e-9209-d35185d44983
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a10c8db7a9706c406cb192f9418c1fd8d04e888a
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765706"
---
# <a name="how-to-collect-line-level-sampling-data"></a>Nasıl yapılır: satır düzeyi örnekleme verileri toplama
Satır düzeyi örnekleme yüksek özel örnekleri olan bir işlev gibi bir işlemci yoğunluğu işlevinin kodda işlemci, süreyi en çok harcama sahip olduğu belirlemek için profil oluşturucu özelliğidir.  
  
## <a name="overview"></a>Genel Bakış  
 Satır düzeyi örnekleme için profil oluşturucu programı çağrı yığını belirlenen aralıklarla anlatılmaktadır ve bu sonuçları toplar. Bu sonuçları örnekleri durumdayken işlemci yürütülmekte olan hangi yönergeleri gösterir. Özel örnekleri hakkında toplanan verileri ardından satırları kod ve yönerge işaretçisi (IP) belirlemek için analiz edilir.  
  
 Satır düzeyi örnekleme yönetilen yanı sıra yerel kod için çalışır. Satırlar görünümü ve modüller görünümü bu verileri görüntülemek performans raporları içerir.  
  
 Karakter begin/bitiş bilgileri yerel kod için kullanılabilir değil. Çok satırlı deyimleri için satırın başında bilgileri yerel kod için; mevcut değil yalnızca satır sonu bilgisi yok.  
  
### <a name="available-data"></a>Kullanılabilir veri  
 Kullanılabilir satır düzeyi örnekleme verileri aşağıdaki bilgileri içerir:  
  
-   İşlev adı.  
  
-   İşlev adresi.  
  
-   Satırları başlayın - örneklenen kodu satır sayısı.  
  
-   Satır sonu - kaynak satır numarasını bitiş. Bu genellikle tek bir program deyimde birden çok kaynak kodu satır yayıldığında dışında "Satırın başında" veri aynıdır.  
  
-   Karakter başlayın - birleşik örnek başlangıç sütunu. Bu genellikle tek bir satıra birden fazla program deyimleri içerdiğinde dışında 0'dır.  
  
-   Karakter son - birleşik örnek sütununun bitiş.  
  
-   IP - birleşik örnek (yalnızca IP görünümü) burada alındığı adresi.  
  
 İçinde **modülleri** görüntülemek için bir işlev satır düzeyi istatistikleri varsa, altında her işlevi istatistikleri yerleştirilir. Ayrıca, her satırın altında iç içe geçmiş IP düzeyi istatistikleri sunulur.  
  
### <a name="turn-off-line-level-sampling-for-managed-code"></a>Yönetilen kod için satır düzeyi örnekleme devre dışı bırakma  
 Varsayılan olarak, satır düzeyi örnekleme açıktır. Yönetilen kod için satır düzeyi veri koleksiyonu aşağıdaki komutlardan birini kullanarak devre dışı bırakabilirsiniz:  
  
-   Profil oluşturma önce yazın **VSPerfCLREnv /samplelineoff**. Bu uygulamalar ve hizmetler etkiler.  
  
     — veya —  
  
-   Bir uygulama başlatılırken yazın **VSPerfCmd /lineoff \<başka bir bağımsız değişken >**.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Performans araçları verilerini analiz etme](../profiling/analyzing-performance-tools-data.md)