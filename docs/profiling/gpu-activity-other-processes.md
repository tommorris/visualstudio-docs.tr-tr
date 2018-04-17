---
title: GPU etkinliği (diğer işlemler) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: edbe8a49ed65fbd51a53cf9e197154489d4ca271
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="gpu-activity-other-processes"></a>GPU Etkinliği (Diğer İşlemler)
**GPU etkinliği (diğer işlemler)** eşzamanlılık görselleştiricisi iş parçacıkları görünümü segmentlerinde ne zaman GPU işlem istekleri sistemdeki diğer işlemleri adına kez temsil eder. Bu istekler GPU doğrudan bellek erişimi (DMA) paketleri gönderilir.  Bir segment uzunluğu paket GPU tarafından işlenen süreyi temsil eder.  
  
 Seçtiğinizde, bu tür bir segment, rapor üzerinde **geçerli** sekmesini işlenmiş paket hakkındaki bilgileri görüntüler.  Bu bilgiler, DirectX altyapısı, paketi gönderilen işlem ve paket işlemek için gereken süre ile ilişkili donanım sırasındaki paket beklenen süre miktarını içerir.