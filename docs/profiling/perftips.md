---
title: PerfTips | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 509d2d4f-48a5-4cdf-acad-6f7b75421303
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 53366b300c94166116c0dc03b108991fc80af013
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255138"
---
# <a name="perftips"></a>PerfTips
Visual Studio hata ayıklayıcısı *PerfTips* ve hata ayıklayıcısı ile tümleşik **tanılama araçları** izleme ve hata ayıklarken, uygulamanızın performansını analiz yardımcı olur.  
  
 Hata ayıklayıcı tümleşik tanılama araçları, geliştirirken, performans sorunlarının farkında olmadan harika bir yolu olsa da, hata ayıklayıcı uygulamanızı performans üzerinde önemli bir etkisi olabilir. Daha doğru performans verilerini toplamak için hata ayıklayıcı dışında çok performans araştırmalar ek bir parçası olarak çalıştırmak Visual Studio tanılama araçlarını kullanmayı düşünün. Bkz: [Profil Araçları ile veya olmadan hata ayıklayıcı çalıştırmak](../profiling/running-profiling-tools-with-or-without-the-debugger.md).  
  
## <a name="perftips"></a>PerfTips  
 Hata ayıklayıcı kesme noktası ya da sürüm işlemi yürütme sona erdiğinde, geçen süre sonu ve önceki kesme noktası arasında Düzenleyicisi penceresinde bir ipucu olarak görüntülenir. Daha fazla bilgi için bkz: [PerfTips: performans bilgileri bir bakışta Visual Studio ile hata ayıklama sırasında](http://blogs.msdn.com/b/visualstudioalm/archive/2014/08/18/perftips-performance-information-at-a-glance-while-debugging-with-visual-studio.aspx).  
  
 ![PerfTip](../profiling/media/dbgdiag_perf_perftip.png "DBGDIAG_PERF_PerfTip")  
  
## <a name="diagnostics-tools-window"></a>Tanılama araçları penceresindeki  
 Kesme noktaları ve ilişkili zamanlama verileri kaydedilir **tanılama araçları** penceresi.  
  
 Aşağıdaki grafik gösterir **tanılama araçları** Visual Studio 2015 güncelleştirme 1 penceresinde:  
  
 ![DiagnosticTools&#45;Update1](../profiling/media/diagnostictools-update1.png "DiagnosticTools Update1")  
  
-   **Kesme olayları** zaman çizelgesi hata ayıklama oturumunda isabet kesme noktaları işaretleyin. Tıklatma seçmek için bir olay **hata ayıklayıcı** ayrıntıları listesi.  
  
-   **CPU kullanımı** grafik gösterir değişikliği CPU kullanımı tüm işlemci çekirdeği arasında hata ayıklama oturumunda.  
  
-   **Olayları** listesi **hata ayıklayıcı** Ayrıntılar bölmesinde her kesme olayı için öğeleri içerir.  
  
-   **Süresi** sütunu sonu olayın olay ve önceki kesme noktası arasında geçen süreyi görüntüler.  
  
## <a name="turn-perftips-on-or-off"></a>PerfTips Aç veya kapat.  
 Etkinleştirmek veya PerfTips devre dışı bırakmak için:  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **seçenekleri**.  
  
2.  Denetleyin veya temizleyin **Göster hata ayıklama sırasında PerfTip geçen**.  
  
## <a name="turn-the-diagnostic-tools-window-on-or-off"></a>Tanılama araçları penceresini aç veya kapat.  
 Etkinleştirmek veya tanılama araçları penceresini devre dışı bırakmak için:  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **seçenekleri**.  
  
2.  Denetleyin veya temizleyin **tanılama araçlarını hata ayıklama etkinleştirme**.

## <a name="see-also"></a>Ayrıca bkz.
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Profil oluşturma özelliği turu](../profiling/profiling-feature-tour.md)
