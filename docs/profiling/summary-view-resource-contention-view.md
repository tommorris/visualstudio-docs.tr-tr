---
title: Özet görünümü - kaynak çakışması görünümü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 6da57b83-7b42-4d7c-9aea-8e0a830faf6b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b74d2f83a184a69b4dba957e8e3195e679a140d9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="summary-view---resource-contention-view"></a>Özet görünümü - kaynak çakışması görünümü
Özet görünümü, bir kaynağa erişim için beklenen karşın, bir iş parçacığı veya işlem askıya alındı, uygulamanızda olaylar hakkında bilgi görüntüler.  
  
 Bildirim bağlantıları ve rapor listeler açıklaması dahil olmak üzere daha fazla bilgi için bkz: [özeti görünümü](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Zaman Çizelgesi grafiği  
 Özet görünümü zaman çizelgesi grafiğinde Çekişme olayları profil oluştu zamanla profili uygulamasının sayısını gösterir. Seçilen zaman aralığı görünümüne filtrelemek için zaman çizelgesi grafik kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Özet zaman çizelgesi filtre rapor görünümleri](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="most-contended-resources"></a>En Contended kaynakları  
 **Çoğu Contended kaynakları** en Çekişme olayları nedeniyle uygulama kaynakları listeler. Çakışmaları görüntülemek için bir kaynak adı tıklatabilirsiniz. Kaynak çekişmeleri ayrıntılı bir zaman çizelgesi çekişmeleri görünümü iş parçacığı tarafından sağlar.  
  
 **Çoğu Contended kaynakları** her kaynak için aşağıdaki veriler içerir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|Kaynağın adı.|  
|**Çekişmeleri %**|Bu kaynak üzerinde çekişmeleri olan profil oluşturma veri tüm Çekişme olayları yüzdesi.|  
  
## <a name="most-contended-thread"></a>En Contended iş parçacığı  
 **Çoğu Contended iş parçacığı** Çekişme olayları'en büyük sayı olan uygulama parçacıklarında listeler. Kaynak çekişmeleri ayrıntılı bir zaman çizelgesi iş parçacığı tarafından sağlar çekişmeleri görünümü görüntülemek için iş parçacığı adı tıklatabilirsiniz.  
  
 **Çoğu Contended iş parçacığı** her iş parçacığı için aşağıdaki veriler içerir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**ID**|İş parçacığı tanımlayıcısı.|  
|**Ad**|İş parçacığı sahibi olan işlemin adı.|  
|**Çekişmeleri %**|Bu kaynak üzerinde çekişmeleri olan profil oluşturma veri tüm Çekişme olayları yüzdesi.|