---
title: "Date.Now işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- now method
ms.assetid: 41beda89-1a40-4fb1-88b0-38c090af739b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41a098c55b8ced3c630d3724615835301b6f00c8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="datenow-function-javascript"></a>Date.now İşlevi (JavaScript)
Geçerli tarih ve saati alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
Date.now()  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Gece yarısından, 1 Ocak 1970 ve geçerli tarih ve saat arasındaki milisaniye sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 [GetTime yöntemi](../../javascript/reference/gettime-method-date-javascript.md) arasındaki milisaniye sayısını döndürür 1 Ocak 1970 ve belirtilen tarih.  
  
 Geçen süre hesaplamak ve tarihleri karşılaştırmak hakkında daha fazla bilgi için bkz: [hesaplama tarihler ve saatler (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `now` yöntemi.  
  
```JavaScript  
var start = Date.now();  
var response = prompt("What is your name?", "");  
var end = Date.now();  
var elapsed = (end - start) / 1000;  
document.write("You took " + elapsed + " seconds" + " to type: " + response);  
  
// Output:  
// You took <seconds> seconds to type: <name>  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Yüklü sürümlerinde Internet Explorer 9'den önceki desteklenmiyor. Ancak, şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları, Internet Explorer 10 standartları. Ayrıca desteklenen [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getTime yöntemi (tarih)](../../javascript/reference/gettime-method-date-javascript.md)   
 [Tarih nesnesi](../../javascript/reference/date-object-javascript.md)   
 [Tarihler ve saatleri hesaplama (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)   
 [JavaScript yöntemleri](../../javascript/reference/javascript-methods.md)