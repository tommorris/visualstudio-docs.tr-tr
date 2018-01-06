---
title: "Çağrı ağacı görünümü - Çekişme verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Call Tree view
ms.assetid: 9bd4bde2-2ca3-446c-9ccc-7421522e03ae
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c829f11efd5eddda0ea819422856cb2bcc30c2ed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="call-tree-view---contention-data"></a>Çağrı ağacı görünümü - Çekişme verileri
Çağrı ağacı görünümü profili uygulamada geçiş işlevi yürütme yollarını görüntüler. Ağaç kök uygulama veya bileşenin giriş noktasıdır. Her işlevi düğümü adlı tüm işlevleri, işlevi engellendi sayısı ve diğer iş parçacıkları veya işlemler sahip bir kaynak için contending çünkü işlev engellendi süreyi listeler.  
  
 Çağrı ağacı görünümü çağrısı ağacında üst işlevi tarafından çağrılan işlev örnekleri için değerler. Yüzde değerleri, profil çalıştırmada çekişmeleri toplam sayısı işlevi örneği değerine karşılaştırılmasıyla hesaplanır.  
  
## <a name="highlighting-the-execution-hot-path"></a>Yürütme etkin yolunuzda vurgulama  
 Çağrı ağacı görünümü genişletin ve işlem ya da çoğu çekişmeleri oluşturulan işlevi yürütme yolunu vurgulayın.  
  
-   En etkin yol görüntülemek için işlem veya işlevi sağ tıklayın ve ardından **genişletin etkin yolunuzda**.  
  
## <a name="setting-the-call-tree-root-node"></a>Çağrı ağacı kök düğümü ayarlama  
 Her profil çalıştırma işleminde bir kök düğüm olarak görünür. Çağrı ağacı görünümü başlangıç düğümünün ayarlamak için başlangıç düğümü olarak ayarlayın ve ardından istediğiniz düğümünü sağ tıklatın **ayarlamak kök**.  
  
 Kök düğüm kümesi olduğunda, Seçili düğümün alt ağacı dışında görünümünden diğer tüm girişleri kaldırın. Kök düğüm özgün düğüme geri sıfırlamak için çağrı ağaç görünümünde sağ tıklayın ve ardından **sıfırlama kök**.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Özel engellenen süresi**|Bu işlev bu yürütme yolunda örneklerini profil yürütülmesini engellendi zaman çalıştırın. İşlevin adı veriliyordu alt işlevlerin engellenen zaman zaman dahil değildir.|  
|**Özel engellenen süresi %**|Bu işlev bu yürütme yolunda için özel engellenen zamanı çalıştırmak profil tüm engellenen zamanı yüzdesi.|  
|**Özel çekişmeleri**|Bu işlev bu yürütme yolunda örneklerinde oluştu çekişmeleri sayısı. Sayı, işlev tarafından çağrılan alt işlevlerin çekişmeleri içermez.|  
|**Özel çekişmeleri %**|Özel çekişmeleri çağrısı ağacında üst işlevi tarafından adlı bu işlev örnekleri olan tüm çekişmeleri profil çalıştırmada yüzdesi.|  
|**İşlev adresi**|İşlev adresi.|  
|**İşlev adı**|İşlev tam adı.|  
|**Dahil engellenen süre**|Bu işlev bu yürütme yolunda örneklerini çalıştırmak profil yürütülmesini engellendi toplam süre. İşlev tarafından çağrılan alt işlevlerin engellenen zaman zaman içerir.|  
|**Kapsayıcı engellenen süresi %**|Profil çalıştıran tüm engellenen zamanın yüzde olarak dahil engellenen süre bu işlev bu yürütme yolunda örnekleri için oluştu.|  
|**Kapsayıcı çekişmeleri**|Bu işlev bu yürütme yolunda örneklerini engellenen çekişmeleri toplam sayısı. İşlev tarafından çağrılan alt işlevleri çekişmeleri sayısını içerir.|  
|**Kapsayıcı çekişmeleri %**|Profil çalıştıran tüm çekişmeleri yüzdesi bu işlev bu yürütme yolunda örneklerinin dahil çekişmeleri yoktu.|  
|**Düzeyi**|Çağrı ağacı işlev düzeyi. Yalnızca VSReport komut satırı raporlarda. Daha fazla bilgi için bkz [VSPerfReport](../profiling/vsperfreport.md).|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**Modül adı**|İşlevi içeren modülü adı.|  
|**Modül yolu**|İşlevi içeren modülü yolu.|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Kaynak dosya**|Bu işlev için tanım içeriyor kaynak dosya.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md)   
 [Çağrı ağacı görünümü](../profiling/call-tree-view.md)   
 [Çağrı ağacı görünümü - izleme](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [Çağrı ağacı görünümü - örnekleme](../profiling/call-tree-view-dotnet-memory-sampling-data.md)   
 [Çağrı ağacı görünümü](../profiling/call-tree-view-instrumentation-data.md)   
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-sampling-data.md)