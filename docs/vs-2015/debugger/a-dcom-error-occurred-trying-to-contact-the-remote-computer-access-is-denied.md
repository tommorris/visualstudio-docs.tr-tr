---
title: Uzak bilgisayara erişilmeye çalışılırken DCOM hatası oluştu. Erişim reddedildi. | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.remote.dcom_access_denied
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cabac4997480b626714c129daef0511643ae2a50
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693419"
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Uzak bilgisayara erişilmeye çalışılırken DCOM hatası oluştu. Erişim reddedildi.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bir DCOM hatası oluştu uzak bilgisayara erişilmeye çalışılıyor. Erişim reddedildi. ](https://docs.microsoft.com/visualstudio/debugger/a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied).  
  
Uzaktan hata ayıklama, aşağıdaki durumlarda yerel ve uzak bilgisayarlar arasında iletişim kurmak için DCOM kullanır:  
  
-   Hata ayıklayıcı kümesine **yerel uyumluluk modu** veya **yönetilen uyumluluk modu** iade **Araçlar / Seçenekler / hata ayıklama** sayfası  
  
-   Yönetilen C++ hata ayıklama (C + +/ CLI) kodu.  
  
-   Visual Studio 2013'te zaman **yerel Düzenle ve Devam Et'i etkinleştir** iade **Araçlar / Seçenekler / hata ayıklama** sayfası  
  
-   Bazı üçüncü taraf hata ayıklama senaryoları  
  
 Visual Studio işlemini kendi kimlik doğrulaması yapamaz (veya sağlanan kimlik bilgilerinin yeterli kabul zaman) Bu hata oluşur. DCOM üzerinden uzaktan hata ayıklayıcı işleme. Bir veya daha fazla aşağıdaki geçici çözümlerden sorunu çözebilir:  
  
-   Devre dışı **yerel uyumluluk modu** ve **yönetilen uyumluluk modu**.  
  
-   Visual Studio 2013'te kapatmak **yerel Düzenle ve Devam Et'i etkinleştir**.  
  
-   Her iki bilgisayar yeniden başlatın.  
  
-   Uzaktan hata ayıklama kimlik bilgilerinin girilmesi gerekir, kimlik bilgilerini kaydetme seçeneğini denetleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)



