---
title: Eşzamanlılık görselleştiricisi işaretleyicileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.markersui
ms.assetid: c4692d17-6cd2-4ad1-8590-d7275c771c70
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f59167b356f4a04b4b37e699fbe49f1ea82943e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692307"
---
# <a name="concurrency-visualizer-markers"></a>Eşzamanlılık görselleştiricisi işaretleyicileri
Eşzamanlılık görselleştiricisi içinde işaretlerinin bir uygulama olayları temsil eden simgelerdir.  Genellikle, bu olayların aşamaları veya bir uygulamadaki oluşum belirlemek için uygulama oluşturur.  Olayları, uygulama veya kitaplıkları ve uygulamanın kullandığı çalışma zamanları tarafından oluşturulabilir.  
  
## <a name="kinds-of-markers"></a>İşaretçileri türleri  
 Eşzamanlılık görselleştiricisi işaretleyicileri üç tür uygulama olayları temsil etmek için kullanır.: bayrakları, iletileri ve yayılır.  
  
1.  Kullanım bir *bayrağı* uygulamanızı zamanda ilginç bir noktanın belirtmek için.  Örneğin, bir değişken değerini belirli bir eşiğe ulaştı veya bir özel durum oluştu temsil edecek bayrak kullanabilirsiniz.  
  
2.  A *ileti* de işaretleri zaman, ancak noktasında günlük stili izleme için kullanabilirsiniz.  Örneğin, ne; böylece, izleme ve eşzamanlılık görselleştiricisi görüntülemek bir ileti çağrısında şimdi kayabilir bir günlük dosyasına yazılan. Eşzamanlılık görselleştiricisi, bu verileri bir CSV dosyasına dışarı aktarmak için de kullanabilirsiniz.  
  
3.  A *span* bir, uygulamanızda kendi aşamaları Örneğin, bir zaman aralığı temsil eder.  
  
## <a name="marker-linkage-to-threads"></a>İş parçacıklarını işaret bağlantı  
 İşaretçileri oluşturur her iş parçacığı ayrı zaman çizelgesi kanal vardır.  İşaretçi olayları oluşturmaktan sorumlu iş parçacığı kimliği işaret kanal açıklama yanında gösterilir.  İşaretçi kanal sol tarafta gösterilen kimliği geçerli işlemdeki başka bir iş parçacığı kimliği eşleşir.  
  
## <a name="marker-importance"></a>İşaretçi önem derecesi  
 İşaretçileri dört önem düzeyinden birine sahip olabilir: Düşük, normal, yüksek ve kritik.  Önem düzeyi temelinde işaretçileri kaynakları filtreleyebilirsiniz.  Örneğin, yalnızca normal veya kritik önemi olan belirli bir kaynaktan işaretçileri görmek istiyorsanız, filtrede yapılandırabilirsiniz [Gelişmiş ayarları](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) iletişim kutusu. Araç ipucu ve buna bir işaret önemini görüntülenen [işaretçiler raporu](../profiling/markers-report.md).  
  
## <a name="marker-category"></a>İşaretçi kategorisi  
 Bir işaretçi kategori aynı kaynaktan geldiği işaret olaylar grubu gösterir.  Eşzamanlılık görselleştiricisi renk bayrakları ve yayılma farklı kategorileri ayırmak için kullanır. Eşzamanlılık görselleştiricisi kategorileri, belirli bir olay Sağlayıcısı'ndan işaret olayları filtrelemek için kullanmak için yapılandırabilirsiniz.  Kullanım [Gelişmiş ayarları](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) filtre yapılandırmak için iletişim kutusu.  
  
## <a name="known-sources-of-markers"></a>İşaretçileri bilinen kaynakları  
 Sağlayıcı için bazı kısıtlamalar aynılarını sürece tüm ETW sağlayıcı işaretleyicileri oluşturabilir. Eşzamanlılık görselleştiricisi işaretçileri için ek olay kaynaklarına dinleyecek şekilde yapılandırabilirsiniz. Varsayılan olarak, bu olay kaynaklarını dinler:  
  
-   [Eşzamanlılık Görselleştiricisi SDK](../profiling/concurrency-visualizer-sdk.md)  
  
-   [Görev Paralel Kitaplığı (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl)  
  
-   [Veri akışı](/dotnet/standard/parallel-programming/dataflow-task-parallel-library)  
  
-   [Paralel LINQ (PLINQ)](/dotnet/standard/parallel-programming/parallel-linq-plinq)  
  
-   [Eşzamanlılık Çalışma Zamanı](/cpp/parallel/concrt/concurrency-runtime)  
  
-   [Senaryo işaret desteği](http://msdn.microsoft.com/en-us/e3b55bc2-b451-4214-ae00-0c7f5a5baec8)  
  
-   [C++ AMP (C++ Accelerated Massive Parallelism)](/cpp/parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism)  
  
 İşaretçileri sekmesindeki kullanabilir [Gelişmiş ayarları](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) çeşitli kaynaklardan işaretçileri eşzamanlılık görselleştiricisi ve, görüntülenen denetlemek için iletişim kutusunu işaretlerin önem ve kategorisine göre filtre uygulayabilirsiniz.  
  
## <a name="markers-from-eventsource"></a>EventSource işaretçilerini  
 Eşzamanlılık görselleştiricisi EventSource olaylarını da görüntüleyebilirsiniz.  Daha fazla bilgi için bkz: [görselleştirmek EventSource olaylarını işaretleyici olarak](../profiling/visualizing-eventsource-events-as-markers.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bayrak işaretleyicileri](../profiling/flag-markers.md)   
 [İleti işaretçileri](../profiling/message-markers.md)   
 [Kapsam işaretleyicileri](../profiling/span-markers.md)   
 [EventSource olaylarını işaretleyici olarak Görselleştirme](../profiling/visualizing-eventsource-events-as-markers.md)