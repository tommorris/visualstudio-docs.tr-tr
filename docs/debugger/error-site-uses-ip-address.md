---
title: 'Hata: Site IP adresi kullanan | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e6073fd88221e307b46a90173526876f2e2186d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-site-uses-ip-address"></a>Hata: Site IP Adresi Kullanıyor
Hata ayıklayıcı bir IP adresi kullanarak bir Web uygulaması için otomatik olarak eklemek çalıştığında bu hata oluşur. Değiştirirseniz bu gerçekleşir **Web sitesi tanımlaması** için **belirli bir IP adresi kullanmak** IIS'de.  
  
 İçin otomatik-çalışmaya ekleme, proje yalnızca makine adı yerine belirli bir IP adresi ile oluşturmanız gerekir. Aksi takdirde hata ayıklayıcı makine adı için IIS hata ayıklama fiil göndermek bir başarısız olmasına neden localhost değiştirilir.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Kullanım el ile eklemek yerine (hata ayıklama menüsünden **ekleme işlemi için**).  
  
     —veya—  
  
2.  Değişiklik **IIS Web sitesi tanımlaması** ayarı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web uygulamalarında hata ayıklama: Hatalar ve sorun giderme](../debugger/debugging-web-applications-errors-and-troubleshooting.md)