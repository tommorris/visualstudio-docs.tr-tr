---
title: Waıtstart | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e1e452fb46af37778a94dee271adf47a1255e1b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690661"
---
# <a name="waitstart"></a>WaitStart
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Waıtstart](https://docs.microsoft.com/visualstudio/profiling/waitstart).  
  
Waıtstart seçeneği yalnızca profil oluşturucu başlatıldı veya belirtilen sayıda saniye geçtikten döndürmek VSPerfCmd.exe başlangıç alt komut neden olur. Varsayılan olarak, başlangıç komut hemen döndürür. Başlangıç alt komutu, profil oluşturucu başlatma olmadan döndürürse, hata döndürülür. Saniye sayısı belirtilmezse, Start komutunu süresiz olarak bekler.  
  
 Bu profil oluşturucu başlatıldı sağlamak üzere toplu iş dosyalarında Waıtstart seçeneği kullanışlıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Seconds`  
 Başlangıç alt komuttan dönmeden önce beklenecek saniye sayısı.  
  
## <a name="required-options"></a>Gerekli seçenekleri  
 Waıtstart seçeneği yalnızca başlangıç alt komut ile kullanılabilir.  
  
 **Çıkış:** `filename`  
 Çıkış dosyası adını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Bu toplu dosya örnekte Start komutunu profil oluşturucuyu başlatmak 5 saniye bekler.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```



