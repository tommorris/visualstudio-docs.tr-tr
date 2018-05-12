---
title: ThreadOn ve ThreadOff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 5cd5a695-0a14-484a-8952-ed47e13d8e92
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a55bcfd09a99d9808bc378e680c33594007661e1
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="threadon-and-threadoff"></a>ThreadOn ve ThreadOff
VSPerfCmd.exe **ThreadOff** ve **ThreadOn** subcommands izleme yöntemini kullanan komut satırı profil oturumlarında kullanılabilir yalnızca. **ThreadOff** ve **ThreadOn** belirtilen iş parçacığı için profil oluşturmayı durdur. **ThreadOff** iş parçacığı profil durdurur ve **ThreadOn** iş parçacığı profil başlatır.  
  
 Çoğu durumda, belirttiğiniz **ThreadOn** veya **ThreadOff** yalnızca seçeneği bir VSPerfCmd.exe olarak komut satırı, ancak bunlar da birleştirilebilir ile **GlobalOn**, **GlobalOff**, **ProcessOn**, ve **ProcessOff** subcommands.  
  
 **ThreadOn** ve **ThreadOff** subcommands etkileşimde **GlobalOn** ve **GlobalOff** veri denetimi komutları komut satırı profil oluşturma oturumu tüm işlemler için koleksiyonda ve **ProcessOn** ve **ProcessOff** belirtilen işlem için veri toplama denetim komutları.  
  
 **ThreadOff** ve **ThreadOn** subcommands profil oluşturucu API işlevleri tarafından yönetilebilir Başlat/Durdur iş parçacığı sayısı da etkiler.  
  
-   **ThreadOff** hemen Başlat/Durdur iş parçacığı sayısı 0 olarak ayarlar ve bu nedenle profil duraklatır.  
  
-   **ThreadOn** hemen Başlat/Durdur iş parçacığı sayısı 1'e ayarlar ve bu nedenle sürdürür profil oluşturma.  
  
 Daha fazla bilgi için bkz: [profil oluşturma araçları API'leri](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe /{ThreadOff|ThreadOn}:TID [Options]  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TID`  
 İş parçacığı başlatmak veya durdurmak için tamsayı tanımlayıcısı.  
  
## <a name="valid-options"></a>Geçerli seçenekleri  
 **ThreadOn** ve **ThreadOff** de aşağıdaki komutları içeren komut satırları belirtilebilir.  
  
 **Başlat:** `Method`  
 Komut satırı profil oluşturma oturumu başlatır ve belirtilen profil oluşturma yöntemini ayarlar.  
  
 **GlobalOff**&#124;**GlobalOn**  
 Durdurur veya bir komut satırı profil oluşturma oturumu tüm işlemler için profil başlatır.  
  
 {**ProcessOff**&#124;**ProcessOn**}**:**`TID`  
 Durdurur veya belirtilen işlem için profil oluşturma başlatır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, **ThreadOff** alt, böylece yalnızca uygulama başlangıç veriler toplanır profil oluşturma veri toplamayı durdurmak için kullanılır.  
  
```cmd  
; Initialize the profiler.  
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp   
; Start the instrumented application.  
; Stop profiling the thread after startup.  
VSPerfCmd.exe /ThreadOff:12345  
; Shut down the target application.  
; Close the profiler.  
VSPerfCmd /Shutdown  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)