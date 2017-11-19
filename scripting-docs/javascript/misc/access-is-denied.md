---
title: "Erişim reddedildi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 8a512060-d744-47af-a83e-4ba42ea2c5b2
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 9c097cd09712d19acf5a0e4999b5c7a47469f958
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="access-is-denied"></a>Erişim reddedildi
Bir komut dosyası konak geçerli sayfanın dışında bir kaynaktan alınan verilere erişmeye çalıştı. Internet Explorer ve diğer tarayıcılarda ardından aynı kaynak İlkesi komut yalnızca aynı düzeni, ana bilgisayar ve bağlantı noktası geçerli sayfanın URL'sini kaynaklardan veri erişim sağlar.  
  
 Örneğin, geçerli sayfa https://employees.mycompany.com ise, aşağıdaki URL'lerden veri erişilemiyor:  
  
-   http://Data.contoso.com, çünkü HTTPS yerine HTTP kullanıyor.  
  
-   https://somedatasource.com, farklı bir etki alanı olduğundan.  
  
-   https://Employees.MyCompany.com:8888, çünkü farklı bir bağlantı noktasını kullanır.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Çağrılacak çalıştığınız API JSONP veya güvenli bir şekilde çıkış noktaları arası betik yazmaya izin ver iki yaklaşım olan CORS destekleyip desteklemediğini araştırın.  
  
-   REST API'sini çağırmak çalışıyorsanız, sunucu tarafı kodunuzu bu çağrıyı yeniden düzenlemeniz ve ardından istemci tarafı komut dosyalarınız için yeni bir REST uç noktasını kullanıma sunar.  
  
     Ek bilgi için aynı kaynak İlkesi, JSONP ve CORS ile ilgili çevrimiçi belgeleri arayın.