---
title: "Zamanlayıcı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1971868e-89fa-4452-8ee7-76e4daf31b66
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c259b4a66a6f26443b684a005adb2899e2d77ca
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="timer"></a>Zamanlayıcı
VSPerfCmd.exe **Zamanlayıcı** seçeneği işlemci saat döngüsü örneklenen ve isteğe bağlı olarak bir örnekleme aralığı içinde döngüsü sayısını 10,000,000 varsayılandan değişiklikleri profil olayını ayarlar. 1GH (bir gigahertz) işlemci üzerinde 10,000,000 saat döngüleri saniyede yaklaşık 100 örnek olur. Minimum belirtilebilir döngüleri 50.000 sayısıdır.  
  
 **Zamanlayıcı** yalnızca örnekleme profili oluşturma yöntemi kullandığınızda ve bu da içeren bir komut satırında kullanılabilir kullanılabilir **başlatma** veya **Attach** seçeneği.  
  
 Varsayılan olarak, profil oluşturucu örnekleme olay işlemci saat döngüsü için ayarlanır ve örnekleme aralığı 10,000,000 için ayarlanır. **Zamanlayıcı**, **PF**, **Sys**, ve **sayaç** seçenekleri örnekleme olay ve örnekleme aralığı ayarlamanıza olanak sağlar. **GC** seçeneği her ayırma ve atık toplama olay .NET bellek verileri toplar. Bir komut satırında bu seçenekler yalnızca biri belirtilebilir.  
  
 Örnekleme olay ve örnekleme aralığı yalnızca ilk komut içeren satırı ayarlanabilir bir **başlatma** veya bir **Attach** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe {/Launch:AppName|/Attach:PID} /Timer[:Cycles] [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Cycles`  
 Bir örnekleme aralığı içinde işlemci saat döngüsü sayısını belirten bir tamsayı değeri. Varsa `Cycles` belirtilmezse, aralığı 10,000,000 için ayarlanır. Virgül olmadan değeri belirtin.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **Zamanlayıcı** yalnızca aşağıdaki seçeneklerden birini içeren bir komut satırında belirtilebilir.  
  
 **Başlatma:**`AppName`  
 Profil Oluşturucu ve tarafından belirtilen uygulamayı başlatır `AppName`.  
  
 **Ekle:**`PID`  
 İşlem kimliği tarafından belirtilen işlem için profil oluşturucu ekler (`PID`).  
  
## <a name="invalid-options"></a>Geçersiz seçenekleri  
 Aşağıdaki seçenekler aynı komut satırında belirtilemez **Zamanlayıcı**.  
  
 **PF**[**:**`Events`]  
 Sayfa hataları için örnekleme olay ayarlar ve isteğe bağlı olarak örnekleme aralığı ayarlar `Events`. Varsayılan PF aralığı 10'dur.  
  
 **Sys**[**:**`Events`]  
 Ayarlar işletim sistemi örnekleme olayı çağırır ve isteğe bağlı olarak örnekleme aralığı ayarlar `Events`. Varsayılan Sys aralığı 10'dur.  
  
 **Sayaç**[**:**`Name,Reload,FriendlyName`]  
 Sayaç tarafından belirtilen CPU performans örnekleme olay ayarlar `Name` ve örnekleme aralığı ayarlar `Reload`.  
  
 **GC**[**:**{**ayırma**&#124; **Ömür**}]  
 .NET bellek verileri toplar. Varsayılan olarak (**ayırma**), her bellek ayırma etkinlikte toplanan veriler. Zaman **ömrü** parametresi belirtilmişse, veri her atık toplama etkinlikte de toplanır.  
  
## <a name="example"></a>Örnek  
 Bu örnek, profil oluşturucu örnekleme aralığı 1.000.000 işlemci döngülerinin ayarlanacağı gösterilmiştir.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Timer:1000000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)