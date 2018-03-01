---
title: "İşlevler görünümü - çakışma verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Functions view
ms.assetid: 208773b0-1a54-4b7a-ad37-2b6fd4f731d4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d9dcf9ab34e5d0441f3c1ce3a47d5e148c9394d0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="functions-view---contention-data"></a>İşlevler görünümü - çakışma verileri
İşlevler raporu engellendi profil çalıştırmada profil çalıştırma sırasında yürütmesindeki işlevleri Çekişme verileri listesini görüntüleyin.  
  
 Eşzamanlılık yöntemi kullanılarak toplanan profil bir veri dosyasının işlevleri görünümünde görüntülenen değerler aşağıdaki tabloda açıklanmaktadır.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Özel engellenen süresi**|İşlev gövdesine kodu yürütme sırasında bu işlev engellendi süre miktarı. İşlevin adı veriliyordu işlevlerinde engellenen süresi dahil değildir.|  
|**Özel engellenen süresi %**|Bu işlevin özel engellenen zamanı çalıştırmak profil tüm engellenen zamanı yüzdesi.|  
|**Özel çekişmeleri**|Bu işlev, işlev gövdesine kod yürütmek engellendi sayısı. İşlevin adı veriliyordu işlevlerinde çekişmeleri dahil edilmez.|  
|**Özel çekişmeleri %**|Profil oluşturma çalıştırmada tüm çekişmeleri yüzdesi bu işlevin özel çekişmeleri yoktu.|  
|**İşlev adresi**|İşlev adresi.|  
|**İşlev adı**|İşlev tam adı.|  
|**Dahil engellenen süre**|Bu işlev veya bu işlev tarafından çağrılan işlev yürütülmesini engellendi süre.|  
|**Kapsayıcı engellenen süresi %**|Bu işlev veya modül (bunlar dahil) engellenen süresi olan çalıştırmak profil tüm engellenen zamanı yüzdesi.|  
|**Kapsayıcı çekişmeleri**|Bu işlev veya bu işlev tarafından çağrılan işlev yürütülmesini engellendi sayısı.|  
|**Kapsayıcı çekişmeleri %**|Profil çalıştıran tüm çekişmeleri yüzdesi bu işlevin veya modül (bunlar dahil) çekişmeleri yoktu.|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**Modül adı**|İşlevi içeren modülü adı.|  
|**Modül yolu**|İşlevi içeren modülü yolu.|  
|**İşlem kimliği**|İşlev yürütülmekte olan işlemin işlem kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Kaynak dosya**|Bu işlev için tanım içeriyor kaynak dosya.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md)   
 [İşlevler görünümü](../profiling/functions-view.md)   
 [İşlevler görünümü - izleme](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [İşlevler görünümü - örnekleme](../profiling/functions-view-dotnet-memory-sampling-data.md)   
 [İşlevler görünümü](../profiling/functions-view-instrumentation-data.md)   
 [İşlevler Görünümü](../profiling/functions-view-sampling-data.md)