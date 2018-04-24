---
title: CPU kullanım grafiği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph
helpviewer_keywords:
- CPU Utilization GraphConcurrency Visualizer, CPU Utilization Graph
ms.assetid: 5332fd38-622d-47a3-874f-8c2fd7a30f95
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cfbce376425d4e98d493aa3478e9cf00ac837a17
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="cpu-utilization-graph"></a>CPU Kullanım Grafiği
CPU kullanım grafiği, zaman içinde bir uygulamada kullanımı düzeyini gösterir. İzleme süresi x ekseni ve y ekseni sistem üzerindeki mantıksal çekirdek sayısı temsil eder. Grafiği, belirli bir zamanda hangi belirli çekirdek etkindir göstermez. Örneğin, iki çekirdek her belirli bir süre için yüzde 50 kapasiteyle çalıştırıyorsanız, bu görünüm kullanılan bir mantıksal çekirdek gösterir.  
  
## <a name="cpu-utilization-graph-colors"></a>CPU kullanım grafiği renkleri  
  
-   Yeşil mantıksal çekirdekler kullanımını, sistemdeki geçerli işlem tarafından gösterir.  
  
-   Açık gri sistem üzerinde başka işlemler tarafından mantıksal çekirdekler kullanımını gösterir. Yüksek CPU grafikte açık gri yüzdesi sistem yoğun başka işlemler tarafından yüklenen ve işleminizi onlar tarafından biterse olası olduğunu gösterir. Diğer işlemler tarafından mantıksal çekirdekler kullanımını azaltmak için sistemde çalışan bunları sayısını azaltın.  
  
-   Koyu gri sistem işlem tarafından mantıksal çekirdekler kullanımını gösterir. Bu doğrudan denetleyemezsiniz ancak işleminiz için mantıksal çekirdekler kullanılabilirliğini etkileyebileceğinden oluştuğunu bilmek yararlıdır.  
  
-   Beyaz sistemdeki kullanılmayan mantıksal çekirdekler kullanılabilirliğini gösterir. Paralellik daha fazla fırsatı bulabilirsiniz bu çekirdek işleminiz için kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanım Görünümü](../profiling/utilization-view.md)   
 [Ortalama CPU Kullanımı](../profiling/average-cpu-utilization.md)