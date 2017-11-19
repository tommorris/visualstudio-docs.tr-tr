---
title: "Kaynak çakışması veri değerlerini anlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
ms.assetid: 071c0f0f-1eba-4dc8-ae87-0810e4086dd0
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b4e128fa9a557569eb737a2b0a70ce60687d0830
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="understanding-resource-contention-data-values"></a>Kaynak Çakışması Veri Değerlerini Anlama
Kaynak çakışması profil rakip iş parçacığı bir uygulamada bir paylaşılan kaynağa erişim için beklenecek zorlanır ayrıntılı çağrı yığını bilgileri her zaman toplar.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 Kaynak çakışması raporları çekişmeleri ve modüller, İşlevler, kaynak kod satırlarını ve bekleme gerçekleştiği yönergeleri için bir kaynak için bekleyen harcanan toplam süreyi toplam sayısını görüntüler.  
  
-   Kapsayıcı değerleri toplam sayısını bir işlev tarafından kaynak çekişmeleri beklenecek zorunlu çekişmeleri ve işlevi beklenen toplam süreyi görüntüler.  İşlevin adı veriliyordu alt işlevleri neden çekişmeleri dahil değerleri dahil edilir.  
  
-   Özel değerler yalnızca beklenecek bir işlev zorlanan ve işlev gövdesine kodu tarafından neden çekişmeleri sayısını görüntüler. Alt işlevleri tarafından neden çekişmeleri dahil edilmez. Özel zaman işlevi için yalnızca işlev gövdesi deyimlerinde neden bekleme süresini de içerir.  
  
 Kaynak çakışması rapor görünümlerini de zaman içinde tek tek Çekişme olayları Göster zaman çizelgesi grafikleri içerir ve belirli olay oluşturulan çağrı yığınları gösterir. Daha fazla bilgi için aşağıdaki konulardan birine bakın:  
  
-   [İş parçacığı Ayrıntıları görünümü](../profiling/thread-details-view-contention-data.md)  
  
-   [Kaynak Ayrıntıları görünümü](../profiling/resource-details-view-contention-data.md)  
  
 Eşzamanlılık profili oluşturma ikinci modu hakkında daha fazla bilgi için bkz: [eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md).