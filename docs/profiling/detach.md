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
ms.workload: multiple
ms.openlocfilehash: 02ff1bd3e3db51a444d371e2e803f77ef1429676
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="detach"></a>Ayır
VSPerfCmd.exe **ayırma** seçeneği keser profil oluşturucu belirtilen işlemler veya tüm işlemlerin hiçbiri belirtilmezse. Profil oluşturma örnekleme yöntemini kullanarak başlatılmış olması gerekir.  
  
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