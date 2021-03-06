---
title: PF | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdc0a094-a986-4629-bd1c-dd5fdca323dc
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9ba9558683311d77742b89a4ae4841ed5b7d8511
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634346"
---
# <a name="pf"></a>PF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [PF](https://docs.microsoft.com/visualstudio/profiling/pf).  
  
VSPerfCmd.exe **PF** seçeneği ayarlar örneklenir profil oluşturma olay sayfa hataları ve bir örnekleme aralığı 10 varsayılan sayfa hata sayısı isteğe bağlı olarak değişir.  
  
> [!NOTE]
>  PF, 64 bit sistemlerde kullanılamaz.  
  
 **Not PF** 64 bit bilgisayarlarda desteklenmez. **PF** de içeren bir komut satırında yalnızca kullanılabilir **başlatma** veya **iliştirme** seçeneği.  
  
 Varsayılan olarak, örnekleme olay durdurulmamış işlemci saat döngülerini için ayarlanır ve örnekleme aralığı 10,000,000 için ayarlanır. **Zamanlayıcı**, **PF**, **Sys**, ve **sayacı** seçenekleri örnekleme olay ve örnekleme aralığı ayarlamanızı sağlar. **GC** seçeneği her ayırma ve atık toplama etkinlikte .NET bellek verileri toplar. Bir komut satırında bu seçenekleri yalnızca biri belirtilebilir.  
  
 Örnekleme olay ve örnekleme aralığı yalnızca ilk komut içeren satırı ayarlanabilir bir **başlatma** veya **iliştirme** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe {/Launch:AppName|/Attach:PID} /PF[:Events] [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Events`  
 Bir örnekleme aralığı içinde sayfa hatası olaylarının sayısını belirten bir tamsayı değeri. Varsa `Events` belirtilmezse, aralığı 10'a ayarlayın.  
  
## <a name="required-options"></a>Gerekli seçenekleri  
 **PF** yalnızca aşağıdaki seçeneklerden birini içeren bir komut satırında belirtilebilir.  
  
 **Başlat:** `AppName`  
 Profil Oluşturucu ve AppName tarafından belirtilen uygulamayı başlatır.  
  
 **Ekleme:** `PID`  
 AppName tarafından belirtilen işlem için profil oluşturucuyu ekler.  
  
## <a name="invalid-options"></a>Geçersiz Seçenekler  
 Aşağıdaki seçenekler aynı komut satırında belirtilemez **PF**.  
  
 **Zamanlayıcı**[**:**`Cycles`]  
 Kümeleri işlemci saat için örnekleme olay geçiş yapar ve isteğe bağlı olarak örnekleme aralığı ayarlar `Cycles`. Varsayılan Zamanlayıcı 10,000,000 aralığıdır.  
  
 **Sys**[**:**`Events`]  
 Örnekleme olayını, işletim sisteminin çekirdeğine (syscalls) profili oluşturulan uygulamayla çağrıları ayarlar ve isteğe bağlı olarak örnekleme aralığı ayarlar `Events`. Varsayılan Sys aralığı 10'dur.  
  
 **Sayaç:** `Name`[`,Reload`[`,FriendlyName`]]  
 Bir CPU performans sayaç tarafından belirtilen örnekleme olayını ayarlar `Name` ve örnekleme aralığı ayarlar `Reload`.  
  
 **GC**[**:**{**ayırma**&#124;**ömrü**}]  
 .NET bellek verileri toplar. Varsayılan olarak (**ayırma**), her bir bellek ayırma etkinlikte toplanan veriler. Zaman **ömrü** parametresi belirtildiğinde, veriler ayrıca her çöp toplama olayını toplanır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, profil oluşturma örnek olay sayfa hataları ve 20 sayfa hataları örnekleme aralığı ayarlayın gösterilmektedir.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /PF:20  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



