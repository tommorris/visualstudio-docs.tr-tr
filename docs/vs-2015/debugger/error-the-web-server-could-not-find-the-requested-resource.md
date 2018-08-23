---
title: 'Hata: Web sunucusu istenen kaynağı bulamadı. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 1ceeaf30-918c-42bb-ace1-96944530fef3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc41673da6157306cd0e4e66070717d5745d6218
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633077"
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>Hata: Web Sunucusu İstenilen Kaynağı Bulamadı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: Web sunucusu istenen kaynağı bulamadı](https://docs.microsoft.com/visualstudio/debugger/error-the-web-server-could-not-find-the-requested-resource).  
  
Güvenlik konuları nedeniyle IIS genel bir hata döndürdü.  
  
 Olası bir nedeni sunucunun güvenlik yapılandırmasıdır. IIS 6.0 ve önceki sürümleri URLScan bilinen bir eklenti program şüpheli ve hatalı isteklerini filtrelemek için kullanılır. IIS 7.0 yerleşik istek filtreleme, aynı amaçla vardır. Her iki durumda da aşırı kısıtlayıcı istek filtrelemeyi Visual Studio sunucu hata ayıklamasından engelleyebilirsiniz.  
  
 Bu hata birçok olası nedenleri vardır. Birkaç yaygın nedenlerinden dosya sisteminde IIS yüklemesi veya yapılandırma, web sitesi yapılandırması veya izinleri ile ilgili bir sorun içerir. Bir tarayıcı ile kaynağa erişmek deneyebilirsiniz. IIS nasıl yapılandırdığına bağlı olarak sunucuda yerel bir tarayıcı kullanın veya ayrıntılı hata iletisini almak için IIS hata günlüğünü inceleyin gerekebilir.  
  
 IIS sorun giderme hakkında daha fazla bilgi için bkz. [IIS Yönetim ve Yönetim](http://go.microsoft.com/fwlink/?LinkId=255872).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UrlScan güvenlik aracı](http://www.microsoft.com/technet/security/tools/urlscan.mspx)   
 [Hata: Web sunucusu kilitli ve DEBUG fiilini engelliyor](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)



