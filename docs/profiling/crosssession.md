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
ms.openlocfilehash: c0dc63350b3acf89b1b226e5ebae45fdf8868fb3
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750096"
---
# <a name="crosssession"></a>CrossSession
*VSPerfCmd.exe* **CrossSession** seçeneğini herhangi bir konsol oturumundan verileri toplamak profil oluşturucu etkinleştirir. **CrossSession** seçeneği kullanılan, ile **Başlat** seçeneği.  
  
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamalar profili](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profil ASP.NET web uygulamaları](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil Hizmetleri](../profiling/command-line-profiling-of-services.md)