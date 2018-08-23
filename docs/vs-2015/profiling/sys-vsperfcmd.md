---
title: Sys (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb87886e4b40643a23e661294c6fcf0a2a74332b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691142"
---
# <a name="sys-vsperfcmd"></a>Sys (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Sys (VSPerfCmd)](https://docs.microsoft.com/visualstudio/profiling/sys-vsperfcmd).  
  
VSPerfCmd.exe **Sys** seçeneği ayarlar örneklenir profil oluşturma olayı sistem çağrısı olaylarını (işletim sistemi profili oluşturulmuş uygulamadan işlev çağrıları) için ve isteğe bağlı olarak değişiklik sistemi sayısı bir örnekleme Varsayılan değer olan 10 aralığından.  
  
 **Sys** de içeren bir komut satırında yalnızca kullanılabilir **başlatma** veya **iliştirme** seçeneği.  
  
 Varsayılan olarak, profil oluşturucu örnekleme olay işlemci saat döngülerini için ayarlanır ve örnekleme aralığı 10,000,000 için ayarlanır. **Zamanlayıcı**, **PF**, **Sys**, ve **sayacı** seçenekleri örnekleme olay ve örnekleme aralığı ayarlamanızı sağlar. **GC** seçeneği her ayırma ve atık toplama etkinlikte .NET bellek verileri toplar. Bir komut satırında bu seçenekleri yalnızca biri belirtilebilir.  
  
 Örnekleme olay ve örnekleme aralığı yalnızca ilk komut içeren satırı ayarlanabilir bir **başlatma** veya **iliştirme** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Events`  
 Sistem sayısını belirten bir tamsayı değeri, bir örnekleme aralığındaki olayları arayın. Varsa `Events` belirtilmezse, aralığı 10'a ayarlayın.  
  
## <a name="required-options"></a>Gerekli seçenekleri  
 **Sys** aşağıdaki seçeneklerden birini gerektirir.  
  
 **Başlat:** `AppName`  
 Profil Oluşturucu ve tarafından belirtilen uygulamayı başlatır `AppName`.  
  
 **Ekleme:** `PID`  
 Tarafından belirtilen işlem için profil oluşturucuya iliştirir `PID`.  
  
## <a name="invalid-options"></a>Geçersiz Seçenekler  
 Aşağıdaki seçenekler aynı komut satırında belirtilemez **Sys**.  
  
 **PF**[**:**`Events`]  
 Örnekleme olay sayfa hataları için ayarlar ve isteğe bağlı olarak örnekleme aralığı ayarlar `Events`. Varsayılan PF aralığı 10'dur.  
  
 **Zamanlayıcı**[**:**`Cycles`]  
 Kümeleri işlemci saat için örnekleme olay geçiş yapar ve isteğe bağlı olarak örnekleme aralığı ayarlar `Cycles`. Varsayılan Zamanlayıcı 10,000,000 aralığıdır.  
  
 **Sayaç:** `Name`[`,Reload`[`,FriendlyName`]]  
 Bir CPU performans sayaç tarafından belirtilen örnekleme olayını ayarlar `Name` ve örnekleme aralığı ayarlar `Reload`.  
  
 **GC**[**:**{**ayırma**&#124;**ömrü**}]  
 .NET bellek verileri toplar. Varsayılan olarak (**ayırma**), her bir bellek ayırma etkinlikte toplanan veriler. Zaman **ömrü** parametresi belirtildiğinde, veriler ayrıca her çöp toplama olayını toplanır.  
  
## <a name="example"></a>Örnek  
 Bu örnek, profil oluşturucu örnekleme olay sistem çağrıları ayarlama ve örnekleme aralığı için örnek başına 20 çağrıları nasıl ayarlanacağını gösterir.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



