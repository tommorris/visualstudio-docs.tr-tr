---
title: 'Nasıl yapılır: satır düzeyi örnekleme verileri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance tools, line-level sampling
ms.assetid: 44803aad-dd39-4c2e-9209-d35185d44983
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bd57893476ba7654a37fc44d1681adc3264f92b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693233"
---
# <a name="how-to-collect-line-level-sampling-data"></a>Nasıl yapılır: Satır Düzeyi Örnekleme Verileri Toplama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: satır düzeyi örnekleme verileri toplama](https://docs.microsoft.com/visualstudio/profiling/how-to-collect-line-level-sampling-data).  
  
Satır düzeyi örnekleme nerede yüksek dışlamalı örnekleri olan bir işlev gibi yoğun işlemci işlevinin kodundaki işlemci zamanının çoğunu harcama belirlemek için profil oluşturucu özelliğidir.  
  
## <a name="overview"></a>Genel Bakış  
 Satır düzeyi örnekleme profil oluşturucu programı çağrı yığınını belirlenen aralıklarla size yol gösterir ve bu sonuçları toplar. Bu sonuçları örnekleri durumdayken işlemci çağırılma yürütüldüğü hangi yönergeleri gösterir. Dışlamalı örnekler hakkında toplanan verileri satırlık bir kod ve yönerge işaretçisi (IP) belirlemek için analiz edilir.  
  
 Satır düzeyi örnekleme yönetilen hem de yerel kod için çalışır. Satırlar görünümü ve modüller görünümü bu verileri görüntüleyen performans raporları içerir.  
  
 Karakter başlamak son bilgileri yerel kod için kullanılabilir değil. Çok satırlı ifadeleri için satırın başında bilgi yerel kod için; mevcut değil yalnızca satır sonu bilgileri kullanılabilir.  
  
### <a name="available-data"></a>Kullanılabilir veri  
 Kullanılabilir satır düzeyi örnekleme verileri aşağıdaki bilgileri içerir:  
  
-   İşlev adı.  
  
-   İşlev adresi.  
  
-   Satırın başında – örnek kod satır sayısı.  
  
-   Satır sonu – kaynak satırı numarasını bitiş. Bu genellikle "Satırın başında" verileri tek bir program ifadesi birden çok kaynak kod satırlarına yayıldığında dışında aynıdır.  
  
-   Karakter başlamalı – toplama örneği başlangıç sütunu. Bu genellikle tek bir satır birden fazla program deyimleri içerdiğinde dışında 0'dır.  
  
-   Karakter sonu – toplam örnek sütunun bitiş.  
  
-   IP – (yalnızca IP görünümü) toplam örnek nereden alındığı adresi.  
  
 İçinde **modülleri** görüntülemek için bir işlevi satır düzeyi istatistikleri varsa, her işlevin altında istatistikleri yerleştirilir. Ayrıca, her satırı altında iç içe geçmiş IP düzeyi İstatistikler gösterilir.  
  
### <a name="turn-off-line-level-sampling-for-managed-code"></a>Yönetilen kod için satır düzeyi örnekleme devre dışı bırakma  
 Varsayılan olarak, satır düzeyi örnekleme etkinleştirilir. Aşağıdakilerden birini yaparak yönetilen kod için satır düzeyinde veri toplamayı kapatabilirsiniz:  
  
-   Profil oluşturmadan önce yazın **VSPerfCLREnv /samplelineoff**. Bu işlem, uygulamaları ve hizmetleri hem de etkiler.  
  
     — veya —  
  
-   Bir uygulama başlatma sırasında yazın **VSPerfCmd/lineoff \<diğer bağımsız değişkenleri >**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Veri Araçları performansını analiz etme](../profiling/analyzing-performance-tools-data.md)



