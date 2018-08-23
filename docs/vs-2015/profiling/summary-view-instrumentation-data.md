---
title: Özet görünümü - izleme verileri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Summary view
ms.assetid: 0a3b3a1f-e22b-4ac8-b46e-71694e9b2cf1
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17534c0c7970238d4b6ef3de79c87d637743ff83
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628949"
---
# <a name="summary-view---instrumentation-data"></a>Özet Görünümü - İzleme Verileri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Özet görünümü - izleme verileri](https://docs.microsoft.com/visualstudio/profiling/summary-view-instrumentation-data).  
  
Özet görünümü, bir profil oluşturma çalışmasında en pahalı performans işlevleri hakkında bilgi görüntüler. Rapor listeler ve bildirim bağlantıları açıklamasını dahil olmak üzere daha fazla bilgi için bkz. [özeti görünümünü](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Zaman Çizelgesi grafiği  
 Özet görünümü zaman çizelgesi grafikte, profili oluşturulan uygulamanın profil oluşturma gerçekleşen zaman tarafından işlemci (CPU) kullanımı gösterir. Seçili zaman aralığı için görünüme filtre uygulamak için zaman çizelgesi Grafiği'ni kullanabilirsiniz. Daha fazla bilgi için [nasıl yapılır: Özet zaman çizelgesinden rapor görünümlerini filtreleme](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="hot-path"></a>Etkin yol  
 **Etkin yolu** en çok zaman harcanan yürütme yolunu görüntüler. İşlev için işlev ayrıntıları görüntülemek için bir işlev tıklayabilirsiniz. İçin işlev sağ işlevi için diğer görünümleri görüntülemek ve sonra listeden bir görünümü tıklatın.  
  
 **Etkin yolu** her işlevine yönelik olarak aşağıdaki verileri içerir:  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlevin adı.|  
|**Geçen kapsamlı süre yüzdesi**|İşlevi, işlev gövdesinde ve onu çağıran işlevler kodu yürütürken harcanan profil oluşturma verilerinin tüm süre yüzdesi.|  
|**Geçen dışlamalı süre yüzdesi**|Tüm profil oluşturma verilerinin işlevi, işlev gövdesinde kod çalıştırırken harcadığı süre yüzdesi. İşlev çağrılan işlevlerde geçen süre dahil değildir.|  
  
## <a name="functions-with-most-individual-work"></a>En bireysel işlerle İşlevler  
 Çoğu zaman kodu yürütürken işlevinin gövdesi ve onu çağıran işlevlerini tüketilen işlevlerin listesi.  
  
 **En bireysel işleri işlevleriyle** her işlevine yönelik olarak aşağıdaki verileri içerir:  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlevin adı.|  
|**Dışlamalı süre yüzdesi**|Tüm profil oluşturma verilerinin işlevi, işlev gövdesinde kod çalıştırırken harcadığı süre yüzdesi. İşlev çağrılan işlevlerde geçen süre dahil değildir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özet görünümü](../profiling/summary-view-sampling-data.md)   
 [Özet Görünümü](../profiling/summary-view-dotnet-memory-data.md)



