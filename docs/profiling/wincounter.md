---
title: WinCounter | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 723b7a0eb4d01795853c3cf0144bfd17d3609891
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="wincounter"></a>WinCounter
**WinCounter** seçeneği, Windows veya uygulama performans sayacı Çalıştır profili sırasında belirlenen aralıklarla toplanacak belirtir. Windows ve uygulama performans sayaçları, profil oluşturma veri dosyası işaretleri olarak listelenir. Ayrı seçeneklerinde toplamak için birden çok performans sayaçları belirtebilirsiniz.  
  
 Varsayılan olarak, sayaçları toplanır her 500 milisaniye. Kullanım **otomatik işaret** seçeneği farklı toplama aralığı belirtin.  
  
 Yalnızca bir **otomatik işaret** seçenek kullanılır. Birden çok **otomatik işaret** seçenekleri belirtilirse, son kullanılır.  
  
 **WinCounter** seçeneği yalnızca kullanılabilir ile **Başlat** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Path`  
 Windows performans sayacı PDH sayaç yolu biçiminde.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **WinCounter** seçeneği yalnızca kullanılabilir ile **Başlat** seçeneği.  
  
 **Başlangıç:**`Method`  
 **Başlat** seçeneği belirtilen profil oluşturma yöntemi için profil oluşturucu başlatır.  
  
## <a name="exclusive-options"></a>Dışlayan seçenekleri  
 **Otomatik işaret** seçeneği yalnızca kullanılabilir ile **WinCounter** seçeneği.  
  
 **Otomatik işaret:**`Milliseconds`  
 Windows performansı sayaç verileri toplama arasındaki milisaniye sayısını belirtir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki Windows performans sayaçlarını 1000 süresi (milisaniye) bir zaman aralığında toplanacak belirtilir.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)