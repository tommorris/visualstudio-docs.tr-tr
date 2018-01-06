---
title: "İşaretçiler raporu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.report.markers
ms.assetid: 829ce099-172e-4c7e-bbd0-578b110c59bd
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e38aa2f9081c1d362d1125838bcfc2e39bb7f277
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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