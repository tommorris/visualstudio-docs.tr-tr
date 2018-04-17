---
title: İş parçacığı Ayrıntıları görünümü - çakışma verileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.threaddetails
helpviewer_keywords:
- Thread Details view
ms.assetid: 874c3b1c-88d8-479a-bb35-1291d9aa8e67
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 241a3d9640e96cb7280321caacfedb406cd52e40
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="thread-details-view---contention-data"></a>İş parçacığı Ayrıntıları görünümü - çakışma verileri
İş parçacığı Ayrıntıları görünümü tarafından çekişmeleri kaynaklar kaynaklanan engelleme olayları Seçili iş parçacığında bir profil oluşturma çalışma zaman çizelgesi grafiğini gösterir. Başka bir iş parçacığı bir kaynağa erişim kilitlediği için yürütme askıya almak için iş parçacığı zorlandığında bir engelleme olayı oluşur.  
  
 Bu görünüm, yürütme zaman çizelgesi yatay bir çubuk olarak iş parçacığı ve iş parçacığı için yatay bir zaman çizelgesi üzerinde dikey çubuk olarak engelleme olayları temsil eder. Gerekli olduğunda olayları tek tek görüntülemek için zaman çizelgesi bir bölümünü yakınlaştırabilirsiniz. Olaya neden işlevleri yürütme yolunu görüntülemek için olay Çubuğu'nu tıklatın. İşlevler çağrı yığını penceresinde görünür. Bir işlev için kaynak kodunu kullanılabilir olduğunda, Visual Studio IDE kaynak dosyasında düzenlemek için işlev adı tıklatabilirsiniz.  
  
## <a name="navigating-the-timeline"></a>Zaman Çizelgesi gezinme  
  
#### <a name="to-zoom-in-on-a-timeline-segment"></a>Bir zaman çizelgesi segmenti yakınlaştırmak için  
  
-   Zaman çizelgesi alanını seçmek için fare işaretçisini sürükleyip bırakın.  
  
     Fareyi bıraktığınızda, görünüm için seçilen zaman diliminin büyütür. Daha ayrıntılı biçimde yakınlaştırmak için bu işlemi yineleyebilirsiniz. Zaman kaydırma çubuğundaki kaydırma kutusunun görünümünde görüntülenen zaman diliminin göreli boyutu temsil eder.  
  
#### <a name="to-zoom-out-on-a-timeline"></a>Bir zaman çizelgesi üzerinde uzaklaştırmak için  
  
-   Tıklatın **Uzaklaştır** önceki yakınlaştırma düzeyini dönün.  
  
-   Tıklatın **yakınlaştırma sıfırlama** tüm zaman çizelgesi görünümde göstermek için.  
  
#### <a name="to-view-the-call-stack-of-an-event"></a>Bir olay çağrı yığınını görüntülemek için  
  
-   Zaman Çizelgesi grafiğinde olay gösteren dikey çubuğu'nu tıklatın...  
  
#### <a name="to-view-or-edit-the-source-code-of-a-function-in-the-call-stack"></a>Görüntülemek veya kaynak kodu çağrı yığınında işlevinin düzenlemek için  
  
-   Çağrı yığını penceresinde işlevi adına tıklayın.  
  
 İşlev kaynak kodu, geçerli projenin bir parçası olması gerekir.  
  
#### <a name="to-view-the-contention-events-of-a-resource-in-all-threads-in-the-profiling-run"></a>Tüm iş parçacıklarını çalıştırmak profil bir kaynağın Çekişme olayları görüntülemek için  
  
-   Zaman Çizelgesi grafiğinde adı veya Kaynak Kimliği'ı tıklatın.  
  
     [Kaynak Ayrıntıları görünümü](../profiling/resource-details-view-contention-data.md) seçilen kaynak için görünür.  
  
#### <a name="to-view-the-thread-contention-data-in-the-processes-window"></a>İş parçacığı Çekişme verileri işlemleri penceresinde görüntülemek için  
  
-   Zaman Çizelgesi grafiği tıklatın **toplam**.  
  
     [İşlem görünümü](../profiling/process-view-contention-data.md) Seçili iş parçacığı ile görünür.