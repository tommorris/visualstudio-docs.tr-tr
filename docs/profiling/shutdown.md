---
title: Kapatma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f2e5411a4d5b88340105f71248ca2e5c2410ff12
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="shutdown"></a>Kapat
**Kapatma** seçeneği bekler bitiş veya ayırmak için işlem şu anda herhangi bir profili ve ardından profil oluşturucu kapatır ve profil oluşturma veri dosyası kapatır. **Kapatma** seçeneği profil çalıştırmak, son komut olması gerekir.  
  
 Bir zaman aşımı parametresi belirtilmezse, **kapatma** seçeneği sonsuza kadar bekler. Zaman aşımı parametresi belirtilirse, seçeneği belirtilen sayıda saniye geçtikten sonra Profil Oluşturucu kapatma veya veri dosyası kapatmadan döndürür.  
  
 **Kapatma** seçeneği, komut satırında belirtilen tek seçenek olmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Timeout`  
 -   (İsteğe bağlı) Belirtilmişse, seçeneği belirtilen sayıda saniye geçtikten sonra Profil Oluşturucu kapatma veya profil oluşturma veri dosyası kapatmadan döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)