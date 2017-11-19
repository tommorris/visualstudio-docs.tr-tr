---
title: "GPU etkinliği (diğer işlemler) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b32ee2967ccc4a7cf1f02935a58cfff5c9e8a33
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="gpu-activity-other-processes"></a>GPU Etkinliği (Diğer İşlemler)
**GPU etkinliği (diğer işlemler)** eşzamanlılık görselleştiricisi iş parçacıkları görünümü segmentlerinde ne zaman GPU işlem istekleri sistemdeki diğer işlemleri adına kez temsil eder. Bu istekler GPU doğrudan bellek erişimi (DMA) paketleri gönderilir.  Bir segment uzunluğu paket GPU tarafından işlenen süreyi temsil eder.  
  
 Seçtiğinizde, bu tür bir segment, rapor üzerinde **geçerli** sekmesini işlenmiş paket hakkındaki bilgileri görüntüler.  Bu bilgiler, DirectX altyapısı, paketi gönderilen işlem ve paket işlemek için gereken süre ile ilişkili donanım sırasındaki paket beklenen süre miktarını içerir.