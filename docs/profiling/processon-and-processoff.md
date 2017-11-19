---
title: ProcessOn ve ProcessOff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3dc6a7e-bc0f-48a6-a4ec-f386348bb296
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e187498656f1fd781d26e6b04426621bd2f3c3c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="processon-and-processoff"></a>ProcessOn ve ProcessOff
VSPerfCmd.exe **ProcessOff** ve **ProcessOn** subcommands duraklatıp belirtilen işlem için bir komut satırı profil oluşturma oturumu profil oluşturma. **ProcessOff** profil oluşturma işlemi durdurur ve **ProcessOn** profil oluşturma işlemini başlatır.  
  
 Çoğu durumda, belirttiğiniz **ProcessOn** veya **ProcessOff** yalnızca seçeneği bir VSPerfCmd.exe olarak komut satırı, ancak bunlar da birleştirilebilir ile **GlobalOn**, **GlobalOff**, **ThreadOn**, ve **ThreadOff** subcommands.  
  
 **ProcessOn** ve **ProcessOff** subcommands etkileşimde **GlobalOn** ve **GlobalOff** veri denetimi komutları komut satırı profil oluşturma oturumu tüm işlemler için koleksiyonda ve **ThreadOn** ve **ThreadOff** belirtilen bir iş parçacığı için veri toplama denetim komutları.  
  
 **ProcessOff** ve **ProcessOn** subcommands profil oluşturucu API işlevleri tarafından yönetilebilir işlem başlatma/durdurma sayısı da etkiler.  
  
-   **ProcessOff** hemen işlem başlatma/durdurma sayısı 0 olarak ayarlar ve bu nedenle profil duraklatır.  
  
-   **ProcessOn** hemen işlem başlatma/durdurma sayısı 1'e ayarlar ve bu nedenle sürdürür profil oluşturma.  
  
 Daha fazla bilgi için bkz: [profil oluşturma araçları API'leri](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /{ProcessOff|ProcessOn}:PID [Options]  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `PID`  
 Tamsayı başlatmak veya durdurmak için işlem tanıtıcısı. İşlem kimliklerini Windows Görev Yöneticisi'nin işlem sekmesinde listelenir.  
  
## <a name="required-subcommands"></a>Gerekli komutları  
 Yok.  
  
## <a name="valid-subcommands"></a>Geçerli komutları  
 **ProcessOn** ve **ProcessOff** de aşağıdaki komutları içeren komut satırları belirtilebilir.  
  
 **Başlangıç:**`Method`  
 Komut satırı profil oluşturma oturumu başlatır ve belirtilen profil oluşturma yöntemini ayarlar.  
  
 **Başlatma:**`AppName`  
 Belirtilen uygulamayı başlatır ve profil oluşturma örnekleme yöntemi ile başlar.  
  
 **Ekle:**`PID`  
 Belirtilen işlem profil başlar.  
  
 **GlobalOff**&#124; **GlobalOn**  
 Durdurur veya bir komut satırı profil oluşturma oturumu tüm işlemler için profil başlatır.  
  
 {**ThreadOff**&#124; **ThreadOn**}**:**`TID`  
 Durdurur veya belirtilen iş parçacığı (yalnızca izleme metodunu) için profil oluşturma başlatır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, **ProcessOff** alt, uygulama başlangıcından profil oluşturma verilerini toplamak için kullanılır.  
  
```  
; Initialize the profiler.  
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp   
; Start the instrumented application.  
; Stop profiling the process after startup.  
VSPerfCmd.exe /ProcessOff:12345  
; Shut down the target application.  
; Close the profiler.  
VSPerfCmd /Shutdown  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)