---
title: "Uzak bilgisayarla iletişim kurmaya çalışırken bir DCOM hata oluştu. Erişim reddedildi. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.remote.dcom_access_denied
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e0d64aef8fd571032959eb8c3ea2e622a8233620
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Uzak bilgisayarla iletişim kurmaya çalışırken bir DCOM hata oluştu. Erişim reddedildi.
Uzaktan hata ayıklama, aşağıdaki durumlarda yerel ve uzak bilgisayarlar arasında iletişim kurmak için DCOM kullanır:  
  
-   Hata ayıklayıcı kümesine **yerel uyumluluk modu** veya **uyumluluk modu yönetilen** iade **Araçlar > Seçenekler > hata ayıklama** sayfası  
  
-   Hata ayıklama yönetilen C++ (C + +/ CLI) kodu.  
  
-   Visual Studio 2013'te zaman **yerel Düzenle ve devam et etkinleştirmek** iade **Araçlar > Seçenekler > hata ayıklama** sayfası  
  
-   Bazı üçüncü taraf senaryoları hata ayıklama  
  
 Bu hata Visual Studio işlemini kendi kimlik doğrulaması yapamaz (veya sağlanan kimlik bilgileri yetersiz olarak kabul) oluşur DCOM üzerinden uzaktan hata ayıklayıcı işlem. Bir veya daha fazla aşağıdaki geçici çözümlerden sorunu çözebilecek:  
  
-   Kapatma **yerel uyumluluk modu** ve **uyumluluk modu yönetilen**.  
  
-   Visual Studio 2013'te kapatmak **yerel Düzenle ve devam et etkinleştirmek**.  
  
-   Her iki bilgisayarı yeniden başlatın.  
  
-   Uzaktan hata ayıklama kimlik bilgilerini girme gerektiriyorsa, kimlik bilgilerini kaydetme seçeneğini denetleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)