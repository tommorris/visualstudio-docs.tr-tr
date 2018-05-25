---
title: Performans sorunlarını giderme araçları sorunları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 0b61cdf7-75b7-4abd-aff2-7bd997717626
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2e78013c97bf7f2cf3bcd60f642f51e9da01b25d
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="troubleshoot-performance-tools-issues"></a>Performans Araçları sorunlarını giderme
Profil oluşturma araçları kullandığınızda aşağıdaki sorunlardan biriyle karşılaşabilirsiniz:  
  
-   [Profil oluşturma araçları tarafından hiçbir veri toplanmadı](#NoDataCollected)  
  
-   [Performans görünümleri ve raporlar için işlev adlarını sayıları görüntüleme](#NoSymbols)  
  
## <a name="no-data-is-collected-by-the-profiling-tools"></a>Profil oluşturma araçları tarafından hiçbir veri toplanmadı  
 Profil oluşturma verileri bir uygulama profili sonra (. *Vsp*) dosyası oluşturulmadı ve çıktı penceresinde veya komut penceresinde aşağıdaki uyarıyı alırsınız:  
  
 PRF0025: Hiçbir veri toplanmıştır.  
  
 Bu sorun birkaç sorunlarından kaynaklanabilir:  
  
-   Örnekleme veya .NET bellek yöntemi kullanarak profili bir işlem uygulama çalışma gerçekleştirir işlem hale bir alt işlem başlatır. Örneğin, bazı uygulamalar, bir Windows uygulaması veya bir komut satırı uygulaması olarak başlatılmış olup olmadığını belirlemek için komut satırını okur. Bir Windows uygulaması istediyseniz özgün işlem bir Windows uygulaması olarak yapılandırılmış yeni bir işlem başlatır ve özgün işlem çıkar. Profil oluşturma araçları otomatik olarak alt işlemleri için veri toplamak için hiçbir veri toplanmadı.  
  
     Bu durumda profil oluşturma verileri toplamak için Profil Oluşturucu ile uygulama başlangıç yerine alt işlem profil oluşturucu ekleme. Daha fazla bilgi için bkz: [nasıl yapılır: ekleme ve çalışan işlemleri için performans araçları ayırma](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md) ve [Ekle (VSPerfCmd)](../profiling/attach.md)  
  
## <a name="performance-views-and-reports-display-numbers-for-function-names"></a>Performans görünümleri ve raporlar için işlev adlarını sayıları görüntüleme  
 Bir uygulama profili sonra raporları ve görünümlerde işlev adları yerine numaralarını bakın.  
  
 Bulunacak erişememe profil oluşturma araçları Çözümleme altyapısı tarafından bu soruna neden *.pdb* eşlemeleri kod bilgileri, bu tür işlev adları ve satır numaralarını derlenmiş dosya için kaynak sembol bilgileri içeren dosyalar. Varsayılan olarak, derleyici oluşturur *.pdb* dosya uygulama dosyası yapılandırıldığında. Bir yerel dizinin başvuru *.pdb* dosya derlenmiş uygulama içinde depolanır. Çözümleme altyapısı başvurulan dizinini arar *.pdb* dosya ve ardından dosyasında şu anda uygulama dosyasını içeren. Varsa *.pdb* dosyası bulunamadı, Çözümleme altyapısı işlevi uzaklıkları yerine işlev adlarını kullanır.  
  
 İki yoldan biriyle sorunu düzeltebilir:  
  
-   Bulun. *pdb* dosyaları ve uygulama dosyalarını aynı dizine koyun.  
  
-   Sembol bilgilerini profil oluşturma verileri katıştırma (. *Vsp*) dosyası. Daha fazla bilgi için bkz: [sembol bilgileri performans ile veri dosyalarını Kaydet](../profiling/saving-symbol-information-with-performance-data-files.md).  
  
> [!NOTE]
>  Çözümleme altyapısı gerektirir. *pdb* derlenmiş uygulama dosyası ile aynı sürüme bir dosyadır. A *.pdb* önceki veya sonraki bir yapı uygulama dosyasının dosyasından çalışmaz.