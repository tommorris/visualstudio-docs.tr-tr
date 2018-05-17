---
title: CrossSession | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d0f9ef3577f1285f428415de6b5b452d2a4cd7b6
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2018
---
# <a name="crosssession"></a>CrossSession
VSPerfCmd.exe **CrossSession** seçeneğini herhangi bir konsol oturumundan verileri toplamak profil oluşturucu etkinleştirir. **CrossSession** seçeneği kullanılan, ile **Başlat** seçeneği.  
  
 Kısaltması kullanabilirsiniz **CS** yerine **CrossSession**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe /Start:Method /CrossSession [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="valid-options"></a>Geçerli seçenekleri  
 Başka bir oturumda profil oluşturmayı etkinleştirmek için **CrossSession** seçeneği belirtilen, ile **Başlat** seçeneği. **CrossSession** birinde de belirtilmelidir sonraki **VSPerfCmd Attach** ve **ayırma** komutları.  
  
 **Başlat:** `Method`  
 **Başlat** seçeneği belirtilen profil oluşturma yöntemi için profil oluşturucu başlatır.  
  
 **Ekle:** *PID*[**, *** PID*]  
 Belirtilen işlemler profil başlar.  
  
 **Detach**[**: *** PID*[,*PID*]]  
 Profil oluşturma belirtilen işlemleri durdurur.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, **CrossSession** seçeneği, başka bir konsol oturumunda başlatılmasından bir uygulama eklemek için kullanılır.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession  
VSPerfCmd.exe /Attach:12345 /CS  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)