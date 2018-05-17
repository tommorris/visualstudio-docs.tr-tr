---
title: Otomatik işaret | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 922f6f40389277bed7da7b960fae341d7afe70da
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2018
---
# <a name="automark"></a>AutoMark
**Otomatik işaret** seçeneği, Windows yazılım performans sayacı olaylarını toplama arasındaki milisaniye sayısını belirtir. Windows performans sayaçlarını belirtilir **WinCounter** seçeneği.  
  
 Yalnızca bir **otomatik işaret** seçeneği komut satırında belirtilebilir. Unutmayın **WinCounter** tarafından belirtilen örnekleme aralığı **otomatik işaret** ana örnekleme aralığı bağımsızdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Milliseconds`  
 Windows performansı sayaç olaylarını koleksiyonları arasındaki milisaniye sayısını belirtir.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **WinCounter:** `Path`  
 Windows performans sayacı toplamak için belirtir. İzleme yöntemi kullanırken, birden çok Windows sayaçları belirtilebilir. Örnekleme yöntemi kullanırken, yalnızca bir yazılım sayaç belirtilebilir. **WinCounter** içeren bir komut satırı seçeneği belirtilen **Başlat** seçeneği.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, iki Windows performans sayaçları için bir örnekleme aralığı 1000 milisaniye olarak ayarlanır.  
  
```cmd  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)