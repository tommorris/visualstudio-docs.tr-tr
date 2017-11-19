---
title: "Span işaretçileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.markers.span
ms.assetid: 736b7765-9c71-44d7-85e5-79787d13d91c
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74919ddaa31bc7857a7bb9c30264830757f336b0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Eşzamanlılık görselleştiricisi SDK](../profiling/concurrency-visualizer-sdk.md)