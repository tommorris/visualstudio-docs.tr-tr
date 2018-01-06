---
title: "Performans sorunlarını giderme araçları sorunları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b61cdf7-75b7-4abd-aff2-7bd997717626
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 748f642e4bd150c8ec5819057b4ee3f7768893f0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-performance-tools-issues"></a>Sorunları araçları performans sorunlarını giderme
Profil oluşturma araçları kullandığınızda aşağıdaki sorunlardan biriyle karşılaşabilirsiniz:  
  
-   [Profil oluşturma araçları tarafından hiçbir veri toplanmadı](#NoDataCollected)  
  
-   [Performans görünümleri ve raporlar için işlev adlarını sayıları görüntüleme](#NoSymbols)  
  
##  <a name="NoDataCollected"></a>Profil oluşturma araçları tarafından hiçbir veri toplanmadı  
 Bir uygulama profili sonra bir profil oluşturma verileri (.vsp) dosyası oluşturulmadı ve çıktı penceresinde veya komut penceresinde aşağıdaki uyarıyı alırsınız:  
  
 PRF0025: Hiçbir veri toplanmıştır.  
  
 Bu sorun birkaç sorunlarından kaynaklanabilir:  
  
-   Örnekleme veya .NET bellek yöntemi kullanarak profili bir işlem uygulama çalışma gerçekleştirir işlem hale bir alt işlem başlatır. Örneğin, bazı uygulamalar, bir Windows uygulaması veya bir komut satırı uygulaması olarak başlatılmış olup olmadığını belirlemek için komut satırını okur. Bir Windows uygulaması istediyseniz özgün işlem bir Windows uygulaması olarak yapılandırılmış yeni bir işlem başlatır ve özgün işlem çıkar. Profil oluşturma araçları otomatik olarak alt işlemleri için veri toplamak için hiçbir veri toplanmadı.  
  
     Bu durumda profil oluşturma verileri toplamak için Profil Oluşturucu ile uygulama başlangıç yerine alt işlem profil oluşturucu ekleme. Daha fazla bilgi için bkz: [nasıl yapılır: ekleme ve ayırma performans araçları çalışan işlemler için](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md) ve [Ekle (VSPerfCmd)](../profiling/attach.md)  
  
##  <a name="NoSymbols"></a>Performans görünümleri ve raporlar için işlev adlarını sayıları görüntüleme  
 Bir uygulama profili sonra raporları ve görünümlerde işlev adları yerine numaralarını bakın.  
  
 Bu sorun, kaynak kodu bilgilerini, bu tür işlev adları ve satır numaralarını derlenmiş dosyaya eşler sembol bilgilerini içeren .pdb dosyaları bulmak erişememe profil oluşturma araçları Çözümleme altyapısı kaynaklanır. Uygulama dosyasını yapılandırıldığında varsayılan olarak, derleyici .pdb dosyasını oluşturur. .Pdb dosyasının yerel dizin başvuru derlenmiş uygulama içinde depolanır. Çözümleme altyapısı .pdb dosyasını başvurulan dizinde bulunan ve ardından şu anda uygulama dosyasını içeren dosyayı arar. .Pdb dosyasını bulunmazsa, Çözümleme altyapısı işlevi uzaklıkları yerine işlev adlarını kullanır.  
  
 İki yoldan biriyle sorunu düzeltebilir:  
  
-   .Pdb dosyaları bulmak ve uygulama dosyalarını aynı dizine koyun.  
  
-   Sembol bilgilerini profil oluşturma veri (.vsp) dosyasına ekleme. Daha fazla bilgi için bkz: [performans veri dosyalarıyla kaydetme sembol bilgileri](../profiling/saving-symbol-information-with-performance-data-files.md).  
  
> [!NOTE]
>  Çözümleme altyapısı .pdb dosyasını derlenmiş uygulama dosyası ile aynı sürüme olmasını gerektirir. Önceki veya sonraki bir yapı uygulama dosyasının .pdb dosyasından çalışmaz.