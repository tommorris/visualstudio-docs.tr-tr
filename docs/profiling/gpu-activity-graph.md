---
title: "GPU Etkinlik Grafiği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ed2b2d86300106f432e1202c9061676ed3aacc0b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="gpu-activity-graph"></a>GPU Etkinlik Grafiği
Eşzamanlılık görselleştiricisi GPU etkinliği grafikte DirectX etkinlik düzeyi sistemde zaman içinde kullanılan DirectX altyapısı sayısı ölçülen görüntüler.  Grafik, hangi belirli motorları kullanılan göstermez.  Altyapının herhangi bir GPU iş işliyorsa kullanımda olarak kabul edilir.  
  
## <a name="gpu-activity-graph-colors"></a>GPU Etkinlik Grafiği renkleri  
 Yeşil DirectX motorları tüketimi geçerli işlem tarafından gösterir.  
  
 Açık gri DirectX motorları tüketimi sistem üzerinde başka işlemler tarafından gösterir. Diğer işlemler tarafından tüketilen DirectX altyapısını azaltmak için sistem üzerinde çalışan diğer işlemlerin sayısını azaltın.  
  
 Beyaz sistem kullanılmayan DirectX motorlarına kullanılabilirliğini gösterir. Daha fazla bunları yararlanma fırsatı bulabilirsiniz bu motorları işleminiz için kullanılabilir. Bazı motorları yalnızca belirli tür görevleri için kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanım Görünümü](../profiling/utilization-view.md)