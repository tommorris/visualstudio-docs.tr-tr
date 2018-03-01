---
title: "İşlem görünümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.view.process
helpviewer_keywords:
- performance tools reports, process view
- Process view
- performance tools, process view
- Profiling Tools,process view
- Profiling Tools,process report
ms.assetid: 6d4e2a5d-9f17-4ece-a6f1-75836e1fc382
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c730169988d931d3e1e57dd22f2793b1f8a16a72
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="process-view"></a>İşlem Görünümü
İşlem görünümü işlemleri ve profil oluşturma çalışması sırasında yürütüldü iş parçacıklarını için profil oluşturma verilerini görüntüler.  
  
 İşlemler adına göre listelenmiştir. İş parçacığı oluşturuldukları işlem alt düğümleri olarak listelenir. İş parçacığı, iş parçacığı çalışmaya işlev veya etiketi tarafından adlandırıldığı **[ntdll.dll]** simge varsa.  
  
 Sütun eklemek veya kaldırmak için görünümü sağ tıklayın ve ardından **Sütun Ekle/Kaldır**. Ayrıca, bir sütun adı tıklayarak verileri sıralayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md).  
  
 İşlem görünümü sütunlarını ve .NET bellek verileri içeren veri örnekleme ve izleme yöntemleri kullanılarak oluşturulan veri için aynıdır. Sütun değerleri aşağıdaki tabloda açıklanmaktadır.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Benzersiz kimliği**|İş parçacığı ve işlem için benzersiz bir profil oluşturucu tarafından oluşturulan bir tanımlayıcı.|  
|**KİMLİĞİ**|İş parçacığı ve işlem sistem tarafından oluşturulan tanıtıcısı.|  
|**Ad**|İş parçacığı ve işlem adı.|  
|**Başlangıç zamanı**|Milisaniye veya işlemci döngülerinin sayısı işlemin veya iş parçacığı başına profil oluşturma başından.|  
|**Bitiş saati**|Milisaniye veya işlemci döngülerinin sayısı işlemin veya iş parçacığı sonuna profil oluşturma başından.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)   
 [İzleme yöntemi veri görünümleri](../profiling/instrumentation-method-data-views.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)