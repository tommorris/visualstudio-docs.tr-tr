---
title: VSPerfASPNetCmd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
ms.assetid: f9e9f895-57bb-41e8-8bd1-cdaa738ec220
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 424bc775e335c093dfbd89dfd0488a545bed7563
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="vsperfaspnetcmd"></a>VSPerfASPNetCmd
**VSPerfASPNetCmd.exe** komut satırı aracı sağlar, ASP.Net Web siteleri profiline gerektirmeden ortam değişkenlerini ayarlama veya bilgisayarınızı yeniden başlatın. Kullanım **VSPerfASPNetCmd.exe** yerine [VSPerfCmd](../profiling/vsperfcmd.md) zaman ASP.NET Web siteleri profil ve tarafından sağlanan ek işlevsellik gerekmez **VSPerfCmd**. Hakkında daha fazla bilgi için **VSPerfASPNetCmd**, bkz: [VSPerfASPNETCmd ile Hızlı Web sitesi profil](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md). **VSPerfASPNetCmd** bir ASP.NET Web sitesi profilini bağımsız profil oluşturucu kullanırken kullanmak için tercih edilen komut satırı aracıdır.  
  
## <a name="syntax"></a>Sözdizimi  
 **vsperfaspnetcmd** [/*seçenekleri*] *Web sitesi*  
  
## <a name="options"></a>Seçenekler  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**/ Örnek** veya   **/s**|Örnekleme yöntemini kullanarak profilleri Web sitesi. **/ Örnek** varsayılan yöntemdir. / Örnek birlikte kullanılamaz **/izleme**.|  
|**/ İzleme** veya **/t**|İzleme metodunu kullanarak profilleri Web sitesi. / İzleme ile kullanılamaz **/örnek**.|  
|**/ Bellek**[**:**`Type`] veya **/m**[**:**{**bir**&#124; **m**}]|Bellek ayırma profilleri ve isteğe bağlı olarak nesne yaşam süresi (çöp toplama) profilleri. **/ Bellek** örnekleme veya izleme yöntemi ile kullanılabilir.<br /><br /> *Tür* şunlardan biri olabilir:<br /><br /> -   **ayırma** (veya **bir**) bellek ayırma yalnızca verileri toplar.<br />-   **Ömür** (veya **l**) bellek ayırma ve nesne yaşam verisi toplar.<br /><br /> Varsayılan `Type` olan **ayırma**.|  
|**/ İpucu** veya **/i**|Ayrıntılı ASP.NET istek ve ADO.NET arama bilgilerini profil oluşturma verileri ekler. **/ İpucu** ile birlikte kullanılabilir ve örnekleme veya izleme metodunu kullanılabilir **/Memory** seçeneği.|  
|**Çıkış:** `File` veya   **/o:**`File`|Profil oluşturma verileri (.vsp) dosya yolu ve dosya adını belirtir.|  
|**/ NoWait** veya**/n**|Böylece komut istemi penceresinde ek komutlar kullanılabilir komut hemen komut istemi döndürür. Yazmanız gerekir **VSPerfASPNETCmd shutdown** profil oluşturma devre dışı bırakmak için ayrı bir komut satırında.|  
|**/ Paket sembolleri**[: {**üzerinde**&#124; **Kapalı**} veya **/p**[: {**üzerinde**&#124; **devre dışı**}|Simgeler (işlev ve parametresi adları, vb.), veri (.vsp) dosyası profil katıştırır.|  
|**/ Kapat:** `Website`veya   **/d:**`Website`|Profil oluşturma devre dışı bırakır. Kullandıktan sonra komut satırındaki tek seçenek olarak kullanın **/nowait** seçeneği, başla veya profil oluşturucu beklenmedik şekilde sona erer. Özgün kullandığınız aynı URL'yi belirtin **VSPerfASPNETCmd** komutu.|  
|`Website`|Profili için Web sitesi URL'si.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil oluşturma VSPerfASPNETCmd ile Hızlı Web sitesi](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)
