---
title: "GPU etkinliği (Bu işlem) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2b395d47e6b338559b6f0bb22c8aef88ba183cd1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="gpu-activity-this-process"></a>GPU Etkinliği (Bu İşlem)
**GPU etkinliği (Bu işlem)** kesimleri eşzamanlılık görselleştiricisi iş parçacıkları görünümünde zaman GPU işlem istekleri geçerli işlem adına kez temsil eder. Bu istekler için GPU doğrudan bellek erişimi (DMA) paketleri gönderilir. Bir segment uzunluğu GPU geçerli işlem adına DMA paket işliyordu süresini temsil eder.  
  
 Üzerinde rapor GPU etkinlik segment seçtiğinizde **geçerli** sekmesini işlenmiş DMA paket hakkındaki bilgileri görüntüler. Bu bilgiler, DirectX altyapısı, paketi gönderilen işlem ve paket işlemek için gereken süre ile ilişkili donanım sırasındaki paket beklenen süreyi içerir. Geçerli işlem dışında bir işlem fiziksel olarak GPU DMA paketi göndermemiş olabilir. Başka bir işlem GPU iş geçerli işlem adına gönderildiğinde eşzamanlılık görselleştiricisi algılayabilir.