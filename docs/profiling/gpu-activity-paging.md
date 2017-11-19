---
title: "GPU etkinliği (disk belleği) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuactivity
- vs.cv.threads.timeline.gpupaging
ms.assetid: 95284ac5-3492-4f7b-a79f-7d2840a07679
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 960ea3a50a5c937b93b81c56e3b775d3fde49bd8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="gpu-activity-paging"></a>GPU Etkinliği (Disk Belleği)
**GPU etkinliği (disk belleği)** iş parçacığı sekmesinde kesimleri zaman GPU işleme disk belleği istekleri kez temsil eder.  Bir segment uzunluğu GPU doğrudan bellek erişimi (DMA) disk belleği paket işliyordu süreyi temsil eder. Genellikle, disk belleği paketleri CPU ve GPU'ya arasında bellek aktarımı ile ilişkilendirilmiş.  
  
 Seçtiğinizde, bir GPU disk belleği segment, rapor üzerinde **geçerli** sekmesini işlenmiş DMA paket hakkındaki bilgileri görüntüler. Bu, beklenen süre miktarını DirectX altyapısı, DMA paket gönderilen işlem ve paket işlemek için gerekli olan zamanı ile ilişkili donanım sıranın içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanım Görünümü](../profiling/utilization-view.md)