---
title: "Kullanım Görünümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.cpuutilization
helpviewer_keywords: Concurrency Visualizer, CPU Utilization View
ms.assetid: b4f7ceab-3653-4069-bb74-c309aec62866
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ee1168865d5827f4536b39b8b0822f1e1d67635e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="utilization-view"></a>Kullanım Görünümü
**Kullanım görünümü** CPU, GPU ve geçerli işlem tarafından kullanılan diğer sistem kaynaklarını hakkındaki bilgileri görüntüler. Çözümlenen işlemi, boşta işlemi, sistem işlem ve zaman içinde sistem üzerinde çalışan diğer işlemler tarafından ortalama Çekirdek kullanımını gösterir. Hangi belirli çekirdek herhangi bir anda etkin göstermez. Örneğin, iki çekirdek her belirli bir süre için yüzde 50 kapasiteyle çalıştırıyorsanız, bu görünüm kullanılan bir mantıksal çekirdek gösterir. Profil oluşturma süresi kısa bir süre parçalara bölerek oluşturulan görüntüleyin. Her segment için grafiğin üzerinde mantıksal çekirdekler bu zaman aralığı boyunca yürütülen işlem iş parçacıklarının ortalama sayısı çizer.  
  
 ![CPU Kullanımı görünümü](../profiling/media/vsts_ppacpuutil.png "VSTS_PPAcpuUtil")  
  
 Zamanında (x ekseni) ve hedef süreci, boşta işlemi ve sistem işlemi tarafından kullanılan ortalama mantıksal çekirdekler grafiğini gösterir. (Boşta çekirdekleri boşta işlemi gösterilmektedir. Sistem iş adına diğer işlemler gerçekleştirebilir Windows işleminde işlemidir.) Sistem hesabı için kalan tüm çekirdek kullanımını üzerinde çalışan kalan işlemler.  
  
 Y ekseni üzerindeki mantıksal çekirdek sayısı gösterilir. Windows eşzamanlı çoklu iş parçacığı destek donanımda mantıksal çekirdekler (örneğin, Hyper-Threading) değerlendirir. Bu nedenle, çekirdek başına iki donanım iş parçacığı destek dört çekirdekli bir işlemciye sahip bir sistem sekiz mantıksal-çekirdek sistem olarak görünür. Bu durum, çekirdekler görünümü için de geçerlidir. Daha fazla bilgi için bkz: [çekirdekler görünümü](../profiling/cores-view.md).  
  
 GPU Etkinlik Grafiği, zaman içinde kullanılan DirectX motorları sayısını gösterir.  DMA paket işleme altyapının kullanılıyor.  Grafiğin belirli DirectX altyapısı (örneğin, 3B motor, Video altyapısı ve diğerleriyle) göstermez.  
  
## <a name="purpose"></a>Amaç  
 Eşzamanlılık görselleştiricisi kullandığınızda kullanım görünümü performans araştırmalar için başlangıç noktası olarak öneririz. Zaman içinde bir uygulamada eşzamanlılık derecesini genel bir bakış sağladığından, hızlı bir şekilde performans ayarlama gerektiren alanları tanımlamak veya paralelleştirme kullanabilirsiniz.  
  
 Performans ayarlama düşünüyorsanız beklentilerinizi karşılamıyor davranışını tanımlamak çalışıyor olabilir. Ayrıca mantıksal CPU çekirdekleri düşük kullanımını sahip bölgeler nedenini ve varlığı için arıyor olabilir. Ayrıca CPU ve GPU'ya arasında kullanım desenlerini görmek.  
  
 Bir uygulama parallelizing düşünüyorsanız, her iki CPU bağımlı alanları yürütme veya burada CPU kullanmıyorsanız alanları için büyük olasılıkla öğrenmek isterler.  
  
 CPU bağımlı alanları yeşil. Grafik uygulama seri ise göstermesi bir çekirdek gösterir.  
  
 Burada CPU kullanmıyorsanız gri alanlarıdır. Bu uygulama boşta olduğu noktaları veya diğer CPU bağımlı iş ile çakışan tarafından paralellik olanaklarını sağlayan gerçekleştirme engelleme g/ç gösterebilir.  
  
 İlgi davranışını bulduğunuzda, o bölge üzerinde seçerek yakınlaştırabilirsiniz. Yakınlaştırma, sonra iş parçacıkları görünümü ya da daha ayrıntılı bir analiz çekirdekler görünümü geçiş yapabilirsiniz.  
  
 C++ AMP veya DirectX kullanarak GPU kullanıyorsanız, GPU altyapısı kullanın veya GPU beklenmedik bir şekilde boşta olduğu alanlarına sayısı tanımlamak için ilginizi çekebilir.  
  
## <a name="zooming"></a>Yakınlaştırma  
 CPU kullanım grafiği veya GPU Etkinlik Grafiği yakınlaştırmak için bir bölüm seçin veya grafiği yukarıda yakınlaştırma kaydırıcı aracını kullanın. Diğer görünümlere geçiş yaparken yakınlaştırma ayarını devam ettirir. Yeniden uzaklaştırmak için yakınlaştırma kaydırıcı aracını kullanın. Ayrıca, Ctrl + kaydırma kullanarak yakınlaştırabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md)   
 [Çekirdekler Görünümü](../profiling/cores-view.md)