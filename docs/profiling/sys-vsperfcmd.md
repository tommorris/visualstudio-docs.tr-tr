---
title: Sys (VSPerfCmd) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c733e9ce91ede2e8944616c5db1a727349854b1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sys-vsperfcmd"></a>Sys (VSPerfCmd)
VSPerfCmd.exe **Sys** seçeneği sistem çağrısı olayları (işletim sistemi profili uygulamasından işlev çağrıları) örnekleme profil olay ayarlar ve isteğe bağlı olarak değişiklik sistem bir örnekleme ek çağrı sayısı Varsayılan olarak 10 Aralık.  
  
 **Sys** de içeren bir komut satırında yalnızca kullanılabilir **başlatma** veya **Attach** seçeneği.  
  
 Varsayılan olarak, profil oluşturucu örnekleme olay işlemci saat döngüsü için ayarlanır ve örnekleme aralığı 10,000,000 için ayarlanır. **Zamanlayıcı**, **PF**, **Sys**, ve **sayaç** seçenekleri örnekleme olay ve örnekleme aralığı ayarlamanıza olanak sağlar. **GC** seçeneği her ayırma ve atık toplama olay .NET bellek verileri toplar. Bir komut satırında bu seçenekler yalnızca biri belirtilebilir.  
  
 Örnekleme olay ve örnekleme aralığı yalnızca ilk komut içeren satırı ayarlanabilir bir **başlatma** veya bir **Attach** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Events`  
 Sistem sayısını belirten bir tamsayı değeri bir örnekleme aralığı içinde olayları çağırın. Varsa `Events` belirtilmezse, aralığı 10 olarak ayarlandı.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **Sys** aşağıdaki seçeneklerden birini gerektirir.  
  
 **Başlatma:**`AppName`  
 Profil Oluşturucu ve tarafından belirtilen uygulamayı başlatır `AppName`.  
  
 **Ekle:**`PID`  
 Profil Oluşturucu tarafından belirtilen işlem ekler `PID`.  
  
## <a name="invalid-options"></a>Geçersiz seçenekleri  
 Aşağıdaki seçenekler aynı komut satırında belirtilemez **Sys**.  
  
 **PF**[**:**`Events`]  
 Sayfa hataları için örnekleme olay ayarlar ve isteğe bağlı olarak örnekleme aralığı ayarlar `Events`. Varsayılan PF aralığı 10'dur.  
  
 **Zamanlayıcı**[**:**`Cycles`]  
 Ayarlar işlemci saatinin örnekleme olaya geçiş yapar ve isteğe bağlı olarak örnekleme aralığı ayarlar `Cycles`. Varsayılan süreölçerini 10,000,000 ' dir.  
  
 **Sayaç:** `Name`[`,Reload`[`,FriendlyName`]]  
 Sayaç tarafından belirtilen CPU performans örnekleme olay ayarlar `Name` ve örnekleme aralığı ayarlar `Reload`.  
  
 **GC**[**:**{**ayırma**&#124; **Ömür**}]  
 .NET bellek verileri toplar. Varsayılan olarak (**ayırma**), her bellek ayırma etkinlikte toplanan veriler. Zaman **ömrü** parametresi belirtilmişse, veri her atık toplama etkinlikte de toplanır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte profil oluşturucu örnekleme olay sistem çağrıları yapma ve örnek başına 20 çağrı örnekleme aralığı ayarlamak nasıl gösterilir.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)