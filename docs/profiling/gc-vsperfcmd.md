---
title: GC (VSPerfCmd) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6a57cb824ca6c2ec4b2f52a070ae407690f83d69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="gc-vsperfcmd"></a>GC (VSPerfCmd)
**GC** seçenek, .NET Framework bellek ayırma ve nesne yaşam verisi koleksiyonunu etkinleştirir. **GC** seçeneği, yalnızca örnekleme profili oluşturma yöntemi ve yalnızca birlikte kullanılabilir **başlatma** seçeneği.  
  
 Kullanırken **GC** seçeneği, VSPerfClrEnv **/sampleon** komutu gerekli değildir.  
  
 Hiçbir parametre belirtilmezse veya **ayırma** parametresi belirtilirse, yalnızca .NET Framework bellek ayırma verileri toplanır. Varsa **ömrü** parametresi belirtilirse, .NET Framework bellek ayırma ve .NET Framework nesne yaşam verisi toplanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 **Ayırma**  
 Varsayılan. .NET Framework bellek ayırma verileri toplar.  
  
 **Ömür**  
 Hem .NET Framework bellek ayırma verileri hem de .NET Framework nesne yaşam verisi toplar.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **GC** seçeneği yalnızca kullanılabilir ile **başlatma** seçeneği.  
  
 **Başlatma:**`AppName`  
 Belirtilen uygulamayı başlatır ve profil oluşturma örnekleme yöntemi ile başlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir uygulama başlatır ve .NET Framework bellek ayırma verileri toplar.  
  
```  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)