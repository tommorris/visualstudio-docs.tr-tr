---
title: Otomatik işaret zamanının | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e01dac3f1012c76ebe6095b5b5a244226fe4843
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632154"
---
# <a name="automark"></a>AutoMark
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [AutoMark](https://docs.microsoft.com/visualstudio/profiling/automark).  
  
**AutoMark** seçeneği, Windows yazılım performansı sayaç olaylarını koleksiyonunu arasındaki milisaniye sayısını belirtir. Windows performans sayaçları belirtilir **WinCounter** seçeneği.  
  
 Yalnızca bir **AutoMark** seçeneği, komut satırında belirtilebilir. Unutmayın **WinCounter** örnekleme aralığı tarafından belirtilen **AutoMark** ana örnekleme aralığı bağımsızdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Milliseconds`  
 Windows performansı sayaç olaylarını koleksiyonları arasında geçen milisaniye sayısını belirtir.  
  
## <a name="required-options"></a>Gerekli seçenekleri  
 **WinCounter:** `Path`  
 Toplanacak Windows performans sayacı belirtir. Araçlar yöntemini kullanırken, birden çok Windows sayaçları belirtilebilir. Örnekleme yöntemini kullanırken, yalnızca bir yazılım sayacı belirtilebilir. **WinCounter** içeren bir komut satırı seçeneği belirtilen **Başlat** seçeneği.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, iki Windows performans sayaçları için 1000 milisaniye cinsinden örnekleme aralığı ayarlanır.  
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



