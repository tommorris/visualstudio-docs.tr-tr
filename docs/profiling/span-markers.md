---
title: Span işaretçileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.markers.span
ms.assetid: 736b7765-9c71-44d7-85e5-79787d13d91c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 697603cea62087163dea5115a74aae4c401b2c2c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="span-markers"></a>Kapsam İşaretleyicileri
Bir aralık işaret uygulama anlamlı bir aşamasını temsil eder. Örneğin, belirli iş öğesini işleniyor zaman aralığını temsil etmek için bir aralığı kullanabilirsiniz. Uzunluğu karşılık gelen uygulama aşaması süresini temsil eder. Bu grafik bir aralık içinde eşzamanlılık görselleştiricisi göstermektedir:  
  
 ![Eşzamanlılık görselleştiricisi bir aralık işaretçisi](../profiling/media/cvmarkerspan.png "CVMarkerSpan")  
Eşzamanlılık görselleştiricisi bir aralık işaretçisi  
  
## <a name="span-category"></a>Aralık kategorisi  
 Bir aralık işaret kategorisinin bağlı olarak beş farklı renk birinde görüntülenir. Beşten fazla kategorileri varsa renkleri yinelenir. Kategori herhangi bir tamsayı olabilir. Bu örnekte, beş olası renkleri gösterilmiştir:  
  
 ![Farklı kategorilerdeki beş yayılma](../profiling/media/cvmarkerspancategory.png "CVMarkerSpanCategory")  
İlk beş aralık kategorileri renkleri  
  
## <a name="span-aggregation-markers"></a>Toplama işaretleyicileri  
 Bazen aralık işaretçileri bunu başka yakın bunlar ayrı ayrı çekilemez eşzamanlılık görselleştiricisi içinde oluşur. Bu oluştuğunda, bir gri *aralık toplama işaret* temsil olarak temel yayılma gösterilir. Bu simgeleri birinde işaretçiyi getirdiğinizde, araç ipucu temsil edilen temel yayılma sayısını görüntüler. Yayılma görüntülemek için Yakınlaştır. Bu süreç boyunca tüm yakınlaştırmak ve bir aralık toplama işaretçi almaya devam varsa, temel alınan aralık işaretlerinde görüntüleyebilirsiniz [işaretçiler raporu](../profiling/markers-report.md). Bu örnekte, bir aralık toplama işaret gösterilmiştir:  
  
 ![Bir toplama eşzamanlılık görselleştiricisi işaretçisi span](../profiling/media/cvmarkerspanaggregate.png "CVMarkerSpanAggregate")  
Bir aralık toplama işaretçisi  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık görselleştiricisi işaretleyicileri](../profiling/concurrency-visualizer-markers.md)   
 [Eşzamanlılık Görselleştiricisi SDK](../profiling/concurrency-visualizer-sdk.md)