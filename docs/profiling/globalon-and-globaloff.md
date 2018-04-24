---
title: GlobalOn ve GlobalOff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 24b0ed68-d19e-473e-9af3-252c11d82bcf
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3009130acbbde431c9751df848eaef252c0bdd04
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="globalon-and-globaloff"></a>GlobalOn ve GlobalOff
VSPerfCmd.exe **GlobalOff** ve **GlobalOn** seçenekleri duraklatıp tüm işlemleri ve iş parçacıklarını için bir komut satırı profil oluşturma oturumu profil oluşturma.  
  
 Belirleyebileceğiniz **GlobalOn** ve **GlobalOff** VSPerfCmd.exe komut satırı veya tek seçenekler de içeren komut satırları içerebilir gibi **Başlat**, **Başlatma**, veya **Attach** seçenekleri.  
  
 **GlobalOn** ve **GlobalOff** ile birleştirilebilir **ProcessOn**, **ProcessOff**, **ThreadOn**ve  **ThreadOff** seçenekleri.  
  
 **GlobalOn** ve **GlobalOff** seçenekleri etkileşimde **ProcessOn** ve **ProcessOff** denetlemek için veri toplama seçeneklerini bir işlemi, belirtilen ile **ThreadOn** ve **ThreadOff** , belirtilen bir iş parçacığı için veri toplama denetleyen seçenekler.  
  
 **GlobalOff** ve **GlobalOn** seçenekleri de Profil Oluşturucu'nın API işlevleri tarafından yönetilebilir genel Başlat/Durdur sayısı etkiler.  
  
-   **GlobalOff** hemen genel Başlat/Durdur sayısı 0 olarak ayarlar ve bu nedenle profil duraklatır.  
  
-   **GlobalOn** hemen genel Başlat/Durdur sayısı 1'e ayarlar ve bu nedenle sürdürür profil oluşturma.  
  
 Daha fazla bilgi için bkz: [profil oluşturma araçları API'leri](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /{GlobalOff|GlobalOn}  
  
VSPerfCmd.exe /Start:Method /{GlobalOff|GlobalOn} [Options]  
  
VSPerfCmd.exe {Launch:AppName|Attach:PID} /{GlobalOff|GlobalOn}[Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="valid-options"></a>Geçerli seçenekleri  
 **GlobalOn** ve **GlobalOff** aşağıdaki seçenekleri de içeren komut satırları belirtilebilir.  
  
 **Başlat:** `Method`  
 Komut satırı Profil Oluşturucu oturumu başlatır ve belirtilen profil oluşturma yöntemini ayarlar.  
  
 **Başlat:** `AppName`  
 Belirtilen uygulamayı başlatır ve profil oluşturma örnekleme yöntemi ile başlar.  
  
 **Ekle:** `PID`  
 Belirtilen işlem profil başlar.  
  
 {**ProcessOff**&#124;**ProcessOn**}**:**`PID`  
 Durdurur veya belirtilen işlem için profil oluşturma başlatır.  
  
 {**ThreadOff**&#124;**ThreadOn**}**:**`TID`  
 Durdurur veya (yalnızca izleme metodunu) belirtilen işlem için profil oluşturma başlatır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, **GlobalOff** ve **GlobalOn** seçenekleri, uygulama başlatma ve kapatma profil oluşturma verilerini toplayan önlemek için kullanılır.  
  
```  
; Initialize the profiler with profiling stopped.  
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp /GlobalOff  
; Start an instrumented application and wait for it to warm up.  
; Start profiling.  
VSPerfCmd.exe /GlobalOn  
; Exercise the application functionality that you want to profile.  
; Stop profiling.  
VSPerfCmd.exe /GlobalOff  
; Shut down the target application.  
; Close the profiler.  
VSPerfCmd /Shutdown  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)