---
title: Zamanlayıcı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 1971868e-89fa-4452-8ee7-76e4daf31b66
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cc361925d26bb6274a90d62c0b0c2085b47210c4
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34476707"
---
# <a name="timer"></a>Zamanlayıcı
VSPerfCmd.exe **Zamanlayıcı** seçeneği işlemci saat döngüsü örneklenen ve isteğe bağlı olarak bir örnekleme aralığı içinde döngüsü sayısını 10,000,000 varsayılandan değişiklikleri profil olayını ayarlar. 1GH (bir gigahertz) işlemci üzerinde 10,000,000 saat döngüleri saniyede yaklaşık 100 örnek olur. Minimum belirtilebilir döngüleri 50.000 sayısıdır.  
  
 **Zamanlayıcı** yalnızca örnekleme profili oluşturma yöntemi kullandığınızda ve bu da içeren bir komut satırında kullanılabilir kullanılabilir **başlatma** veya **Attach** seçeneği.  
  
 Varsayılan olarak, profil oluşturucu örnekleme olay işlemci saat döngüsü için ayarlanır ve örnekleme aralığı 10,000,000 için ayarlanır. **Zamanlayıcı**, **PF**, **Sys**, ve **sayaç** seçenekleri örnekleme olay ve örnekleme aralığı ayarlamanıza olanak sağlar. **GC** seçeneği her ayırma ve atık toplama olay .NET bellek verileri toplar. Bir komut satırında bu seçenekler yalnızca biri belirtilebilir.  
  
 Örnekleme olay ve örnekleme aralığı yalnızca ilk komut içeren satırı ayarlanabilir bir **başlatma** veya bir **Attach** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe {/Launch:AppName|/Attach:PID} /Timer[:Cycles] [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Cycles`  
 Bir örnekleme aralığı içinde işlemci saat döngüsü sayısını belirten bir tamsayı değeri. Varsa `Cycles` belirtilmezse, aralığı 10,000,000 için ayarlanır. Virgül olmadan değeri belirtin.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **Zamanlayıcı** yalnızca aşağıdaki seçeneklerden birini içeren bir komut satırında belirtilebilir.  
  
 **Başlat:** `AppName`  
 Profil Oluşturucu ve tarafından belirtilen uygulamayı başlatır `AppName`.  
  
 **Ekle:** `PID`  
 İşlem kimliği tarafından belirtilen işlem için profil oluşturucu ekler (`PID`).  
  
## <a name="invalid-options"></a>Geçersiz seçenekleri  
 Aşağıdaki seçenekler aynı komut satırında belirtilemez **Zamanlayıcı**.  
  
 **PF**[**:**`Events`]  
 Sayfa hataları için örnekleme olay ayarlar ve isteğe bağlı olarak örnekleme aralığı ayarlar `Events`. Varsayılan PF aralığı 10'dur.  
  
 **Sys**[**:**`Events`]  
 Ayarlar işletim sistemi örnekleme olayı çağırır ve isteğe bağlı olarak örnekleme aralığı ayarlar `Events`. Varsayılan Sys aralığı 10'dur.  
  
 **Sayaç**[**:**`Name,Reload,FriendlyName`]  
 Sayaç tarafından belirtilen CPU performans örnekleme olay ayarlar `Name` ve örnekleme aralığı ayarlar `Reload`.  
  
 **GC**[**:**{**ayırma**&#124;**ömrü**}]  
 .NET bellek verileri toplar. Varsayılan olarak (**ayırma**), her bellek ayırma etkinlikte toplanan veriler. Zaman **ömrü** parametresi belirtilmişse, veri her atık toplama etkinlikte de toplanır.  
  
## <a name="example"></a>Örnek  
 Bu örnek, profil oluşturucu örnekleme aralığı 1.000.000 işlemci döngülerinin ayarlanacağı gösterilmiştir.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Timer:1000000  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamalar profili](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profil ASP.NET web uygulamaları](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil Hizmetleri](../profiling/command-line-profiling-of-services.md)