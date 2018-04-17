---
title: İşaretçiler raporu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.markers
ms.assetid: 829ce099-172e-4c7e-bbd0-578b110c59bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e0347107f2f6f50a9c35f59577ea3c13a6e887a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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