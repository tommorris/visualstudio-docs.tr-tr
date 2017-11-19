---
title: "İşlevler görünümü - örnekleme veri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sampling profiling method,Functions View
- Functions view
ms.assetid: 029d5ebb-e551-46b0-b64e-2c553d9dbb8e
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6bafb60abd13713ec8f942de62bf6c82aead379a
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="functions-view---sampling-data"></a>İşlevler görünümü - örnekleme verileri
Örnekleme profili yöntemi için işlevleri rapor görünümü Çalıştır profili oluşturma sırasında örneklenen işlevleri listeler.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|İşlevi içeren modülü adı.|  
|**Modül yolu**|İşlevi içeren modülü yolu.|  
|**Kaynak dosya**|Bu işlev için tanım içeriyor kaynak dosya.|  
|**İşlev adı**|İşlev tam adı.|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**İşlev adresi**|İşlev adresi.|  
|**Kapsayıcı örnekleri**|Bu işlev yürütülürken toplanan örnek toplam sayısını; diğer bir deyişle, bu işlev çağrı yığınındaki olduğu zaman, toplanan örnek sayısı. Bu işlev tarafından çağrılan işlevler yürütülürken toplanan örnek sayısını içerir.|  
|**Kapsayıcı örnekleri %**|Profil çalıştıran tüm örneklerini yüzdesi bu işlevin kapsayıcı örnekleri yoktu.|  
|**Özel örnekleri**|Bu işlev gövdesi kodda yürütülürken toplanan örnek toplam sayısını; diğer bir deyişle, bu işlev üst kısmında çağrı yığını zaman oluştu. Bu işlev tarafından çağrılan işlevler toplanan örnekleri dahil edilmez.|  
|**Özel örnekleri %**|Profil çalıştıran tüm örneklerini yüzdesi bu işlev özel örnekleri yoktu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md)   
 [İşlevler görünümü - izleme](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [İşlevler görünümü - örnekleme](../profiling/functions-view-dotnet-memory-sampling-data.md)   
 [İşlevler görünümü](../profiling/functions-view-instrumentation-data.md)