---
title: GPU etkinliği (Bu işlem) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44d676fc69142e0ab8de4f63637b81578a0e2a00
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="gpu-activity-this-process"></a>GPU Etkinliği (Bu İşlem)
**GPU etkinliği (Bu işlem)** kesimleri eşzamanlılık görselleştiricisi iş parçacıkları görünümünde zaman GPU işlem istekleri geçerli işlem adına kez temsil eder. Bu istekler için GPU doğrudan bellek erişimi (DMA) paketleri gönderilir. Bir segment uzunluğu GPU geçerli işlem adına DMA paket işliyordu süresini temsil eder.  
  
 Üzerinde rapor GPU etkinlik segment seçtiğinizde **geçerli** sekmesini işlenmiş DMA paket hakkındaki bilgileri görüntüler. Bu bilgiler, DirectX altyapısı, paketi gönderilen işlem ve paket işlemek için gereken süre ile ilişkili donanım sırasındaki paket beklenen süreyi içerir. Geçerli işlem dışında bir işlem fiziksel olarak GPU DMA paketi göndermemiş olabilir. Başka bir işlem GPU iş geçerli işlem adına gönderildiğinde eşzamanlılık görselleştiricisi algılayabilir.