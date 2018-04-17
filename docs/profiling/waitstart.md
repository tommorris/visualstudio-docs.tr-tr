---
title: WaitStart | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5f3f91177a372b3508257150e9d3e44c44f525bc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="waitstart"></a>WaitStart
WaitStart seçeneği yalnızca profil oluşturucu başlatıldı başlatıldığında ya da belirtilen sayıda saniye geçtikten sonra dönmek VSPerfCmd.exe başlatma alt komutunun neden olur. Varsayılan olarak, başlangıç komut hemen döndürür. Başlangıç alt komut profil oluşturucu başlatılırken olmadan döndürürse, bir hata döndürülür. Saniye sayısını belirtilmezse, başlatma komutunun sonsuza kadar bekler.  
  
 Bu profil oluşturucu başlatıldı güvence altına almaya toplu iş dosyalarında WaitStart seçeneği kullanışlıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Seconds`  
 Başlangıç alt komutun dönmeden önce beklenecek saniye sayısı.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 WaitStart seçeneği yalnızca başlangıç alt komutu ile kullanılabilir.  
  
 **Çıktı:** `filename`  
 Çıktı dosyası adını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Bu toplu iş dosyası örneği başlatma komutunun başlatmak profil oluşturucu 5 saniye bekler.  
  
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