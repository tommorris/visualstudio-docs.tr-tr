---
title: "Kaynak Ayrıntıları görünümü - Çekişme verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.resourcedetails
helpviewer_keywords: Resource Details view
ms.assetid: a4ecfe1c-abbc-4fb3-9ab2-34de50486901
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eaf87be0e921d0e86818c29c078d8b214591418d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="resource-details-view---contention-data"></a>Kaynak Ayrıntıları görünümü - çakışma verileri
Kaynak Ayrıntıları görünümü zaman çizelgesi grafik çekişmeleri tarafından seçilen bir kaynak kaynaklanan engelleme olayların sayısını gösterir. Başka bir iş parçacığı kaynağa erişim kilitlediği için yürütme askıya almak için bir iş parçacığı zorlandığında bir engelleme olayı oluşur.  
  
 Bu görünüm yatay bir çubuk olarak her bir iş parçacığı yürütme zaman çizelgesi temsil eder ve her engelleme olay iş parçacığı zaman çizelgesi dikey çubuk olarak temsil eder. Gerekli olduğunda olayları tek tek görüntülemek için zaman çizelgesi bir bölümünü büyütebilirsiniz. Olaya neden işlevleri yürütme yolunu (çağrı yığını) görüntülemek için olay Çubuğu'nu tıklatın. İşlevler görünür **çağrı yığını** penceresi. Bir işlev için kaynak kodunu kullanılabilir olduğunda, arabirim için kaynak dosyasında düzenlemek için işlev adı tıklatabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-magnify-a-timeline-segment"></a>Zaman Çizelgesi segmenti büyütmek için  
  
-   Fare işaretçisi bir zaman çizelgesi üzerinde sürükleyin.  
  
     Fare düğmesini bıraktığınızda, görünüm için seçilen zaman diliminin büyütür. Daha fazla segment büyütmek için bu işlemi yineleyebilirsiniz. Zaman kaydırma çubuğundaki kaydırma kutusunun görünümü'nde görüntülenen zaman diliminin göreli boyutu temsil eder.  
  
#### <a name="to-zoom-out-on-a-timeline"></a>Bir zaman çizelgesi üzerinde uzaklaştırmak için  
  
-   Aşağıdaki adımlardan birini uygulayın:  
  
    -   Tıklatın **Uzaklaştır** önceki yakınlaştırma düzeyini dönün.  
  
    -   Tıklatın **yakınlaştırma sıfırlama** tüm zaman çizelgesi görünümde göstermek için.  
  
#### <a name="to-view-the-call-stack-of-an-event"></a>Bir olay çağrı yığınını görüntülemek için  
  
-   Zaman Çizelgesi grafiğinde olay Çubuğu'nu tıklatın.  
  
#### <a name="to-view-or-edit-the-source-code-of-a-function-in-the-call-stack"></a>Görüntülemek veya kaynak kodu çağrı yığınında işlevinin düzenlemek için  
  
-   İçinde **çağrı yığını** penceresinde işlevi adına tıklayın.  
  
 İşlev kaynak kodu, geçerli projenin bir parçası olması gerekir.  
  
#### <a name="to-view-the-call-tree-of-contention-events-for-the-resource"></a>Çekişme olayları kaynak çağrı ağacının görüntülemek için  
  
-   Zaman Çizelgesi grafiği tıklatın **toplam**.  
  
     İçin kaynak çekişmeleri görünümü görüntülenir. Daha fazla bilgi için bkz: [kaynak çekişmeleri görünümü](../profiling/resource-contentions-view-contention-data.md)  
  
#### <a name="to-view-all-the-contention-events-of-a-thread"></a>İş parçacığı tüm Çekişme olayları görüntülemek için  
  
-   Zaman Çizelgesi grafiğinde adı veya kimliği iş parçacığının'ı tıklatın.  
  
     Seçilen iş parçacığı için iş parçacığı Ayrıntıları görünümü görüntülenir. Daha fazla bilgi için bkz: [iş parçacığı Ayrıntıları görünümü](../profiling/thread-details-view-contention-data.md).