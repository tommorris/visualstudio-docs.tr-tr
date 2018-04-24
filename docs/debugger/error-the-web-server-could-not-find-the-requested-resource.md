---
title: 'Hata: Web sunucusu istenen kaynak bulunamadı. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 48d4a5845dd5e5f364d34544f57e1ef7bdfe6052
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>Hata: Web Sunucusu İstenilen Kaynağı Bulamadı
Güvenlik hususları nedeniyle IIS genel bir hata döndürdü.  
  
 Olası bir nedeni, sunucunun güvenlik yapılandırmasıdır. IIS 6.0 ve önceki sürümleri URLScan bilinen bir eklenti programı şüpheli ve hatalı biçimlendirilmiş istekleri filtrelemek için kullanılır. IIS 7.0 yerleşik istek filtreleme, aynı amaçla vardır. Her iki durumda da aşırı kısıtlayıcı istek filtreleme Visual Studio sunucunun hata ayıklama engelleyebilir.  
  
 Bu hata, çok sayıda olası nedenleri vardır. En yaygın nedenlerinden bazılarını dosya sisteminde IIS yüklemesi veya yapılandırması, web sitesi yapılandırması veya izinleri ile ilgili bir sorun içerir. Bir tarayıcı ile kaynak erişme deneyebilirsiniz. IIS nasıl yapılandırdığına bağlı olarak sunucuda yerel bir tarayıcı kullanın veya ayrıntılı hata iletisini almak için IIS hata günlüğünü İncele gerekebilir.  
  
 IIS sorunlarını giderme hakkında daha fazla bilgi için bkz: [IIS yönetimi ve Yönetim](http://go.microsoft.com/fwlink/?LinkId=255872).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UrlScan güvenlik aracı](http://www.microsoft.com/technet/security/tools/urlscan.mspx)   
 [Hata: Web sunucusu kilitli ve DEBUG fiilini engelliyor](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)