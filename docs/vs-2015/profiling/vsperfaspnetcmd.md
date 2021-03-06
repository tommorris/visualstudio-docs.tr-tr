---
title: VSPerfASPNetCmd | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profiling tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
ms.assetid: f9e9f895-57bb-41e8-8bd1-cdaa738ec220
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a074edba64f9742f9761754279be35f5c621be2b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632145"
---
# <a name="vsperfaspnetcmd"></a>VSPerfASPNetCmd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [VSPerfASPNetCmd](https://docs.microsoft.com/visualstudio/profiling/vsperfaspnetcmd).  
  
**VSPerfASPNetCmd.exe** komut satırı aracı sayesinde ASP.Net Web sitesini profiline gerektirmeden ortam değişkenlerini ayarlama veya bilgisayarınızı yeniden başlatın. Kullanım **VSPerfASPNetCmd.exe** yerine [VSPerfCmd](../profiling/vsperfcmd.md) ne zaman, ASP.NET Web sitesini profil ve tarafından sağlanan ek işlevsellik gerekmeyen **VSPerCmd**. Hakkında daha fazla bilgi için **VSPerfASPNetCmd**, bkz: [VSPerfASPNETCmd ile Hızlı Web sitesi profil](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md). **VSPerfASPNetCmd** bağımsız profil oluşturucuyu bir ASP.NET Web sitesinin profilini çıkarmak için kullanırken kullanmak için tercih edilen komut satırı aracıdır.  
  
## <a name="syntax"></a>Sözdizimi  
 **vsperfaspnetcmd** [/*seçenekleri*] *Web sitesi*  
  
## <a name="options"></a>Seçenekler  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**/ Örnek** veya **/s**|Örnekleme metodu kullanılarak profilleri Web sitesi. **/ Örnek** için varsayılan yöntemdir. / Örnek ile birlikte kullanılamaz **/Trace**.|  
|**/ İzleme** veya **/t**|Araçlar yöntemini kullanarak profilleri Web sitesi. / İzleme ile birlikte kullanılamaz **/Sample**.|  
|**/ Bellek**[**:**`Type`] veya **/m**[**:**{**bir**&#124;**l**}]|Bellek ayırma profilini oluşturur ve isteğe bağlı olarak, nesne kullanım ömrü (atık toplama) profilleri. **/ Bellek** örnekleme veya araç haline getirme yöntemi ile kullanılabilir.<br /><br /> *Tür* aşağıdakilerden biri olabilir:<br /><br /> -   **ayırma** (veya **bir**) yalnızca bellek ayırma verileri toplar.<br />-   **yaşam süresi** (veya **l**) bellek ayırma ve nesne yaşam süresi verisi toplar.<br /><br /> Varsayılan `Type` olduğu **ayırma**.|  
|**/ İpucu** veya **/i**|Profil oluşturma verileri ayrıntılı ASP.NET isteğinin ve ADO.NET çağrı bilgilerini ekler. **/ İpucu** örnekleme veya araç haline getirme yöntemi ile kullanılabilir ve ile kullanılabilir **/Memory** seçeneği.|  
|**Çıkış:** `File` veya   **/o:**`File`|Profil oluşturma veri (.vsp) dosyasının yolu ve dosya adını belirtir.|  
|**/ NoWait** veya **/n**|Ek komutlar komut istemi penceresinde kullanılabilir böylece komut hemen sor döndürür. Yazmanız gerekir **VSPerfASPNETCmd/shutdown** profil oluşturma devre dışı bırakmak için ayrı bir komut satırında.|  
|**/ PackSymbols**[: {**üzerinde**&#124;**kapalı**} veya **/p**[: {**üzerinde**&#124;**Kapalı**}|Semboller (işlev ve parametre adları, vb.), profil oluşturma veri (.vsp) dosyası gömer.|  
|**/ Shutdown:** `Website`veya   **/d:**`Website`|Profil oluşturma kapatır. Kullandıktan sonra bir komut satırında tek seçenek olarak kullanın **/nowait** profil oluşturma, başlatmak için seçeneği veya profil oluşturucuyu beklenmedik şekilde sona erer. Özgün kullandığınız aynı URL'yi belirtin **VSPerfASPNETCmd** komutu.|  
|`Website`|Profili oluşturulacak Web sitesi URL'si.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil oluşturma VSPerfASPNETCmd ile Hızlı Web sitesi](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)



