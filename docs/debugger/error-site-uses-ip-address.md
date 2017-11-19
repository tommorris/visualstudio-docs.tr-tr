---
title: 'Hata: Site IP adresi kullanan | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
ms.assetid: b2b8ddc8-746d-46e3-87a6-b956b1ee048d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e1ee3e2ed3d6524749757806931fbb8c4b9a36a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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