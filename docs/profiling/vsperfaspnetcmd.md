---
title: VSPerfASPNetCmd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
ms.assetid: f9e9f895-57bb-41e8-8bd1-cdaa738ec220
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c6e4420b0466857177cad356de7bb4a737968f3
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="vsperfaspnetcmd"></a>VSPerfASPNetCmd
**VSPerfASPNetCmd.exe** komut satırı aracı sağlar, ASP.Net Web siteleri profiline gerektirmeden ortam değişkenlerini ayarlama veya bilgisayarınızı yeniden başlatın. Kullanım **VSPerfASPNetCmd.exe** yerine [VSPerfCmd](../profiling/vsperfcmd.md) zaman ASP.NET Web siteleri profil ve tarafından sağlanan ek işlevsellik gerekmez **VSPerfCmd**. Hakkında daha fazla bilgi için **VSPerfASPNetCmd**, bkz: [VSPerfASPNETCmd ile hızlı web sitesi profili oluşturma](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md). **VSPerfASPNetCmd** bir ASP.NET Web sitesi profilini bağımsız profil oluşturucu kullanırken kullanmak için tercih edilen komut satırı aracıdır.  
  
## <a name="syntax"></a>Sözdizimi  
 **vsperfaspnetcmd** [/*seçenekleri*] *Web sitesi*  
  
## <a name="options"></a>Seçenekler  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**/ Örnek** veya   **/s**|Örnekleme yöntemini kullanarak profilleri Web sitesi. **/ Örnek** varsayılan yöntemdir. / Örnek birlikte kullanılamaz **/izleme**.|  
|**/ İzleme** veya **/t**|İzleme metodunu kullanarak profilleri Web sitesi. / İzleme ile kullanılamaz **/örnek**.|  
|**/ Bellek**[**:**`Type`] veya **/m**[**:**{**bir**&#124;**l**}]|Bellek ayırma profilleri ve isteğe bağlı olarak nesne yaşam süresi (çöp toplama) profilleri. **/ Bellek** örnekleme veya izleme yöntemi ile kullanılabilir.<br /><br /> *Tür* şunlardan biri olabilir:<br /><br /> -   **ayırma** (veya **bir**) bellek ayırma yalnızca verileri toplar.<br />-   **Ömür** (veya **l**) bellek ayırma ve nesne yaşam verisi toplar.<br /><br /> Varsayılan `Type` olan **ayırma**.|  
|**/ İpucu** veya **/i**|Ayrıntılı ASP.NET istek ve ADO.NET arama bilgilerini profil oluşturma verileri ekler. **/ İpucu** ile birlikte kullanılabilir ve örnekleme veya izleme metodunu kullanılabilir **/Memory** seçeneği.|  
|**Çıkış:** `File` veya   **/o:**`File`|Profil oluşturma verileri (.vsp) dosya yolu ve dosya adını belirtir.|  
|**/ NoWait** veya **/n**|Böylece komut istemi penceresinde ek komutlar kullanılabilir komut hemen komut istemi döndürür. Yazmanız gerekir **VSPerfASPNETCmd shutdown** profil oluşturma devre dışı bırakmak için ayrı bir komut satırında.|  
|**/ Paket sembolleri**[: {**üzerinde**&#124;**kapalı**} veya **/p**[: {**üzerinde**&#124;**Kapalı**}|Simgeler (işlev ve parametresi adları, vb.), veri (.vsp) dosyası profil katıştırır.|  
|**/ Kapat:** `Website`veya   **/d:**`Website`|Profil oluşturma devre dışı bırakır. Kullandıktan sonra komut satırındaki tek seçenek olarak kullanın **/nowait** seçeneği, başla veya profil oluşturucu beklenmedik şekilde sona erer. Özgün kullandığınız aynı URL'yi belirtin **VSPerfASPNETCmd** komutu.|  
|`Website`|Profili için Web sitesi URL'si.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Profil oluşturma VSPerfASPNETCmd ile hızlı web sitesi](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)   
 [Profil ASP.NET web uygulamaları](../profiling/command-line-profiling-of-aspnet-web-applications.md)
