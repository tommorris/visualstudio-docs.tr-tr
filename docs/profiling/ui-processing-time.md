---
title: UI işleme zamanı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.uiprocessing
helpviewer_keywords:
- Concurrency Visualizer, UI Processing Time
ms.assetid: 0ddb05a3-8c6b-448b-8488-2751c1e5abcc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1d1e587fa7e089ee3c137ffa836a99d31dd62f8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ui-processing-time"></a>UI İşleme Zamanı
Bu kesimler çizelgesinde UI işleme sınıflandırılır kez engelleme ile ilişkilendirilir. Bu bir iş parçacığı Windows iletileri Pompalama veya diğer kullanıcı arabirimi (UI) iş gerçekleştirme anlamına gelir. Bu süre boyunca, bir iş parçacığı UI işleme eşzamanlılık görselleştiricisi sayım bir API'sindeki engellendi. API'leri gibi `GetMessage()` ve `MsgWaitForMultipleObjects()` bu gruba ayrılır.  
  
 Önceden tanımlanmış hiçbir engelleme API tanımlanırsa, çağrı yığınları ve gecikme temel nedenlerini belirlemek için profil raporları gözden geçirin.  
  
 UI işleme kategori GUI uygulamalarının yanıtlama hızını anlamak için önemlidir ve UI yanıtlama hızı üzerinde bağımlı olan uygulamalar tercih edilir. Örneğin, kullanıcı Arabirimi iş parçacığı bir uygulamada UI işleme % 100 zamanında erişir, büyük olasılıkla çok esnek olur. Ancak, kullanıcı Arabirimi iş parçacığı diğer kategorilerdeki önemli ölçüde zaman harcayan, kök nedeni arayın ve o iş parçacığı UI olmayan kategorilerindeki azaltma seçenekleri göz önünde bulundurun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)