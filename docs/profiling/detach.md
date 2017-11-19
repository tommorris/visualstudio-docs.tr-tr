---
title: Detach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9d1b52c-7f28-467d-b1e0-512afc4e46c9
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97d48bdcfe663fe5434622775add890166663276
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="detach"></a>Ayır
VSPerfCmd.exe **ayırma** seçeneği keser profil oluşturucu belirtilen işlemler veya tüm işlemlerin hiçbiri belirtilmemiş olması durumunda. Profil oluşturma örnekleme yöntemini kullanarak başlatılmış olması gerekir.  
  
 Profil başlatıldı biriyle **başlatma** veya **Attach** seçenekleri bağlantısı kesilmiş olan **ayırma**. Profil Oluşturucu sonraki kullanarak reattched olabilir **Attach** komutları.  
  
 **Detach** profil oluşturma veri dosyası kapatmaz. Kullanım **kapatma** seçeneği profil oluşturma ve veri dosyasını kapatın.  
  
> [!NOTE]
>  Varsa **Başlat** seçeneği ile belirtilen **Crosssession** seçeneğini yapılan her çağrı **VSPerfCmd /Attach** veya **VSPerfCmd /Detach** gerekir Ayrıca belirtin **Crosssession**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Detach[:PIDs|ProcessNames]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `PIDs|ProcessNames`  
 `PID`-Bir veya daha fazla işlemlerin sayısal sistem tanımlayıcı.  
  
 `ProcessNames`-işlemin adı. Adlandırılmış işlem birden çok örneğini çalıştırıyorsanız, sonuçlar tahmin edilemez.  
  
 Birden çok işlem virgülle ayırın.  
  
 Hiçbir işlem belirtilmediği takdirde, profil oluşturucu tüm profili işleminden ayrılır.  
  
## <a name="valid-options"></a>Geçerli seçenekleri  
 Aşağıdaki **VSPerfCmd** seçenekleri ile birleştirilebilir **Attach** tek bir komut satırı seçeneği.  
  
 **Crosssession**  
 Oturumlarında oturum dışında profil oluşturma uygulamaları etkinleştirir. Gerekli olursa **Başlat** seçeneği ile belirtilen **Crosssession** seçeneği.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, **ayırma** komutu askıya profil oluşturma ve **kapatma** komutu Profil Oluşturucu veri dosyası kapatır.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
;REM Excercise the application  
VSPerfCmd.exe /Detach  
VSPerfCmd.exe /Shutdown  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)