---
title: Eşzamanlılık görselleştiricisi | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.performance.viewnavigation
- vs.cv.overview
- vs.cv.performance.gettingstarted
- vs.cv.gettingstarted
helpviewer_keywords:
- Concurrency Visualizer, Concurrency Visualizer
ms.assetid: ae5879a0-1e1a-455a-ba72-148e57f59289
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4636481c931d5035483843424f77383976a67c60
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="concurrency-visualizer"></a>Eşzamanlılık Görselleştiricisi
> [!NOTE]
>  Eşzamanlılık görselleştiricisi, Visual Studio için isteğe bağlı bir uzantıdır. Eşzamanlılık görselleştiricisi ve eşzamanlılık görselleştiricisi koleksiyonu araçları aşağıdaki bağlantılardan birini indirin:  
>   
>  -   Karşıdan [Visual Studio 2017 eşzamanlılık görselleştiricisi](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.ConcurrencyVisualizer2017#overview) uzantısı.  
>  -   Karşıdan [Visual Studio 2015 için eşzamanlılık görselleştiricisi](https://visualstudiogallery.msdn.microsoft.com/a6c24ce9-beec-4545-9261-293061436ee9) uzantısı.  
> -   Karşıdan [eşzamanlılık görselleştiricisi toplama araçları Visual Studio 2015 için](http://www.microsoft.com/en-in/download/details.aspx?id=49103).  
>   
>      [Eşzamanlılık görselleştiricisi komut satırı yardımcı programı (CVCollectionCmd)](../profiling/concurrency-visualizer-command-line-utility-cvcollectioncmd.md) Visual Studio 2015 için eşzamanlılık görselleştiricisi görüntüleyebilirsiniz komut satırından izlemeleri topladığınız sağlar. Aracı Visual Studio yüklü olmayan bilgisayarlarda kullanılabilir.  
  
 Eşzamanlılık görselleştiricisi birden çok iş parçacıklı uygulamanızı nasıl gerçekleştireceğini görmek için kullanabilirsiniz. Eşzamanlılık görselleştiricisi görünümlerde programınızı parçacıklarında ve bir bütün olarak sistem arasındaki zamana bağlı ilişkileri gösteren grafik, tablo ve metinsel veriler sağlar. Eşzamanlılık görselleştiricisi performans sorunları, CPU yetersiz kullanım, iş parçacığı Çekişme, çapraz çekirdek iş parçacığı geçiş, eşitleme gecikmeler, DirectX etkinlik, çakışan g/ç alanlarının ve diğer bilgileri bulmak için kullanabilirsiniz. Görünümleri yığınları ve kaynak kodu çağırmak için grafik çıktısını bağlayarak üzerinde davranamaz veriler sağlar.  

> [!NOTE]
>  Eşzamanlılık görselleştiricisi Web projeleri desteklemiyor.  
  
 Eşzamanlılık görselleştiricisi dayanan [Windows için olay izleme](http://go.microsoft.com/fwlink/?LinkId=234579) işlevselliği.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Kullanım Görünümü](../profiling/utilization-view.md)|Görüntüleme ve tüm işlemciler arasında sistem etkinliğini çözümleme açıklar.|  
|[İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)|İş parçacığı programınızdaki arasındaki etkileşimler analiz edilmesi anlatılmaktadır.|  
|[Çekirdekler Görünümü](../profiling/cores-view.md)|Çekirdek arasında iş parçacığı geçiş analiz edilmesi anlatılmaktadır.|  
|[Hatalı davranan çok iş parçacıklı uygulamalar için ortak desenler](../profiling/common-patterns-for-poorly-behaved-multithreaded-applications.md)|Birçok ortak desenleri açıklar ve eşzamanlılık görselleştiricisi görüntülenme gösterir.|  
|[Visual Studio Web günlüğündeki paralel geliştirme](http://go.microsoft.com/fwlink/?LinkId=235385)|İpuçları ve en iyi uygulamalar için eşzamanlılık görselleştiricisi sağlar.|  
|[Performans Raporu Görünümleri](../profiling/performance-report-views.md)|Visual Studio profil oluşturma araçları görünümlerini ve raporlar için başvuru bilgileri sağlar.|  
|[Eşzamanlılık Görselleştiricisi SDK](../profiling/concurrency-visualizer-sdk.md)|Eşzamanlılık görselleştiricisi ek bilgileri görüntülemek için kaynak kodu işaretlemesini açıklar.|  
|[Eşzamanlılık Görselleştiricisi Komut Satırı Yardımcı Programı (CVCollectionCmd)](../profiling/concurrency-visualizer-command-line-utility-cvcollectioncmd.md)|Eşzamanlılık görselleştiricisi komut satırı yardımcı programını (CVCollectionCmd.exe) toplamak ve izlemelerini Visual Studio sahip olmayan makinelere işlemek için nasıl kullanılacağını açıklar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Özellik turu profil oluşturma](../profiling/profiling-feature-tour.md)
