---
title: İşlem görünümü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.process
helpviewer_keywords:
- performance tools reports, process view
- Process view
- performance tools, process view
- Profiling Tools,process view
- Profiling Tools,process report
ms.assetid: 6d4e2a5d-9f17-4ece-a6f1-75836e1fc382
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 86e8a11f55edd2f7a04498b81ec6b8713876f718
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="process-view"></a>İşlem Görünümü
İşlem görünümü işlemleri ve profil oluşturma çalışması sırasında yürütüldü iş parçacıklarını için profil oluşturma verilerini görüntüler.  
  
 İşlemler adına göre listelenmiştir. İş parçacığı oluşturuldukları işlem alt düğümleri olarak listelenir. İş parçacığı, iş parçacığı çalışmaya işlev veya etiketi tarafından adlandırıldığı **[ntdll.dll]** simge varsa.  
  
 Sütun eklemek veya kaldırmak için görünümü sağ tıklayın ve ardından **Sütun Ekle/Kaldır**. Ayrıca, bir sütun adı tıklayarak verileri sıralayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md).  
  
 İşlem görünümü sütunlarını ve .NET bellek verileri içeren veri örnekleme ve izleme yöntemleri kullanılarak oluşturulan veri için aynıdır. Sütun değerleri aşağıdaki tabloda açıklanmaktadır.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Benzersiz kimliği**|İş parçacığı ve işlem için benzersiz bir profil oluşturucu tarafından oluşturulan bir tanımlayıcı.|  
|**ID**|İş parçacığı ve işlem sistem tarafından oluşturulan tanıtıcısı.|  
|**Ad**|İş parçacığı ve işlem adı.|  
|**Başlangıç zamanı**|Milisaniye veya işlemci döngülerinin sayısı işlemin veya iş parçacığı başına profil oluşturma başından.|  
|**Bitiş saati**|Milisaniye veya işlemci döngülerinin sayısı işlemin veya iş parçacığı sonuna profil oluşturma başından.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Örnekleme yöntemi veri görünümleri](../profiling/profiler-sampling-method-data-views.md)   
 [İzleme yöntemi veri görünümleri](../profiling/instrumentation-method-data-views.md)   
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)