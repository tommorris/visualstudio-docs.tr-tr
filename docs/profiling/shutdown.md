---
title: Kapatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c835894d18ca1aea33f26f234a4df914114089c
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="shutdown"></a>Kapat
**Kapatma** seçeneği bekler bitiş veya ayırmak için işlem şu anda herhangi bir profili ve ardından profil oluşturucu devre dışı bırakır ve profil oluşturma veri dosyası kapatır. **Kapatma** seçeneği profil çalıştırmak, son komut olması gerekir.  
  
 Bir zaman aşımı parametresi belirtilmezse, **kapatma** süresiz olarak seçeneği bekler. Zaman aşımı parametresi belirtilirse, seçenek devre dışı profil oluşturucu kapatma veya veri dosyası kapatmadan belirtilen sayıda saniye geçtikten sonra döndürür.  
  
 **Kapatma** seçeneği, komut satırında belirtilen tek seçenek olmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Timeout`  
 -   (İsteğe bağlı) Belirtilmişse, seçenek devre dışı profil oluşturucu kapatma veya profil oluşturma veri dosyası kapatmadan belirtilen sayıda saniye geçtikten sonra döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)