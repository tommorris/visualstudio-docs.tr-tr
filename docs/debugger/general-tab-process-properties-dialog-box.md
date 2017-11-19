---
title: "Genel sekmesi, işlem özellikleri iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Process properties for Windows NT
ms.assetid: 86f4d61d-a594-4aac-8960-c5279b4a10fd
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9548b35d893fa08458c6254776c8949cc83c510
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="general-tab-process-properties-dialog-box"></a>Genel Sekmesi, İşlem Özellikleri İletişim Kutusu
Kullanım **genel** sekmesi belirli bir işlemle ilgili daha fazla bilgi edinin. Görüntülenecek [işlem özellikleri iletişim kutusu](../debugger/process-properties-dialog-box.md), odağı taşımak bir [işlemler görünümü](../debugger/processes-view.md) penceresi. Ağaçta herhangi bir işlem düğümü seçin ve ardından **özellikleri** gelen **Görünüm** menüsü.  
  
 Aşağıdaki ayarlar kullanılabilir **genel** sekmesi:  
  
|Giriş|Açıklama|  
|-----------|-----------------|  
|**Modül adı**|Modül adı.|  
|**İşlem kimliği**|Bu işlemin benzersiz Kimliğidir. İşlem Kimliği numaraları yeniden kullanılır, bu nedenle bunlar yalnızca işlem süresi için bir işlemi tanımlar. Bir program çalıştırıldığında işlem nesne türü oluşturulur. Bir işlemin tüm iş parçacıklarının aynı adres alanını paylaşır ve aynı verilere erişimi.|  
|**Temel öncelik**|Bu işlem geçerli temel önceliği. Bir işlem içinde iş parçacığı oluşturma ve kendi temel önceliği işlemin temel önceliğine göre daha düşük.|  
|**İş parçacıkları**|Bu işlemde etkin olan iş parçacıklarının sayısı.|  
|**CPU süresi**|Bu işlem ve parçacıklarını harcanan toplam CPU zaman. Kullanıcı süresi ve ayrıcalıklı zaman eşittir.|  
|**Kullanıcı Zamanı**|Bu işlemin iş parçacıklarının boş olmayan iş parçacıklarında kullanıcı modunda kod çalıştırırken harcadığı toplu geçen süre. Pencere Yöneticisi ve grafik altyapısı gibi alt sistemleri gibi uygulamalar kullanıcı modunda çalışır.|  
|**Ayrıcalıklı Zaman**|Geçen toplam süre, boş olmayan iş parçacıklarında ayrıcalıklı modda bu işlemin çalıştığı. Hizmet katmanı, Executive yordamları ve çekirdek ayrıcalıklı modda çalışır. Grafik bağdaştırıcıları ve yazıcılar dışında çoğu cihazların cihaz sürücüleri de ayrıcalıklı modda yürütün. Uygulamanız için Windows yapar bazı iş ayrıcalıklı zaman yanı sıra diğer alt sistem işlemlerinde görünebilir.|  
|**Geçen süre**|Bu işlemin çalıştığı toplam geçen süre.|