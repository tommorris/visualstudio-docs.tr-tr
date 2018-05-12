---
title: GC (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08c9de6d307b54829e2f0783cf0ff272f399de68
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="gc-vsperfcmd"></a>GC (VSPerfCmd)
**GC** seçenek, .NET Framework bellek ayırma ve nesne yaşam verisi koleksiyonunu etkinleştirir. **GC** seçeneği, yalnızca örnekleme profili oluşturma yöntemi ve yalnızca birlikte kullanılabilir **başlatma** seçeneği.  
  
 Kullanırken **GC** seçeneği, VSPerfClrEnv **/sampleon** komutu gerekli değildir.  
  
 Hiçbir parametre belirtilmezse veya **ayırma** parametresi belirtilirse, yalnızca .NET Framework bellek ayırma verileri toplanır. Varsa **ömrü** parametresi belirtilirse, .NET Framework bellek ayırma ve .NET Framework nesne yaşam verisi toplanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 **Ayırma**  
 Varsayılan. .NET Framework bellek ayırma verileri toplar.  
  
 **Ömür**  
 Hem .NET Framework bellek ayırma verileri hem de .NET Framework nesne yaşam verisi toplar.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **GC** seçeneği yalnızca kullanılabilir ile **başlatma** seçeneği.  
  
 **Başlat:** `AppName`  
 Belirtilen uygulamayı başlatır ve profil oluşturma örnekleme yöntemi ile başlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir uygulama başlatır ve .NET Framework bellek ayırma verileri toplar.  
  
```cmd  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)