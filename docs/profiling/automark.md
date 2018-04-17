---
title: Otomatik işaret | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf11dd16dcf9724e0913eed07ae13b285a2d382e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="automark"></a>AutoMark
**Otomatik işaret** seçeneği, Windows yazılım performans sayacı olaylarını toplama arasındaki milisaniye sayısını belirtir. Windows performans sayaçlarını belirtilir **WinCounter** seçeneği.  
  
 Yalnızca bir **otomatik işaret** seçeneği komut satırında belirtilebilir. Unutmayın **WinCounter** tarafından belirtilen örnekleme aralığı **otomatik işaret** ana örnekleme aralığı bağımsızdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)