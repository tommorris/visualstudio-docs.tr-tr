---
title: İşaretçiler raporu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.markers
ms.assetid: 829ce099-172e-4c7e-bbd0-578b110c59bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3b46cb18e1972d22010ce356f1d9208f391f6d79
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31580414"
---
# <a name="markers-report"></a>İşaretçiler Raporu
İşaretçiler raporu görüntülenen zaman çerçevesi içinde işaretlerinin listeler.  Yatay kaydırma veya yakınlaştırma veya yolları, gizleme görünmesini veya kayboluyor işaretçileri neden olabilir. Rapor her işaret ilgili bu bilgiler içerir:  
  
-   Ne zaman onu, izlemeyi Başlat göre başladığı zaman.  
  
-   Süresi. Anlık gösterdiğinden süresi bayrakları ve iletileri için sıfır olur.  
  
-   Bu üretilen iş parçacığı kimliği.  
  
-   Bu oluşturulan olay izleme için Windows (ETW) sağlayıcısı.  
  
-   İşaretçi seri içinden yazıldı.  
  
-   Ait olduğu olay kategorisi.  
  
-   Kendi önem düzeyi.  
  
-   (Aralık, bayrak veya ileti) türü.  
  
-   Neyin temsil ettiğini bir üst düzey açıklaması  
  
 Seçin **verme** düğmesi işaretçiler raporu bir CSV dosyası olarak kaydedin. Diğer uygulamalar veya Araçlar CSV dosyasındaki veri kullanabilirsiniz.  
  
> [!NOTE]
>  İşaretçiler raporu 1.000 işaretleyicileri görüntüleyebilirsiniz. Tüm işaretlerin görmek için bir CSV dosyasına tam raporu dışarı aktarın.