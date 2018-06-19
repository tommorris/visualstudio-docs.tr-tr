---
title: Date.UTC işlevi (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- UTC
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- UTC function [JavaScript]
- UTC dates, returning
- Date.UTC function [JavaScript]
ms.assetid: c0d67ce1-a47e-4dfd-bbf4-21619c406a0f
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a6a7c5622b74699e3d718ceb65e96638bdb6c3c5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790415"
---
# <a name="dateutc-function-javascript"></a>Date.UTC İşlevi (JavaScript)
Gece yarısından, 1 Ocak 1970'ten arasındaki milisaniye sayısını döndürür (veya GMT) Evrensel Eşgüdümlü saate (UTC) ve belirtilen tarih.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Date.UTC(year, month, day[, hours[, minutes[, seconds[,ms]]]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `year`  
 Gerekli. Tam yıl ataması arası century tarih doğruluğu için gereklidir. Varsa `year` 0 ile 99 arasında ardından kullanılan `year` 1900 varsayılır + `year`.  
  
 `month`  
 Gerekli. 0 ve 11 (Ocak-Aralık) arasında bir tamsayı olarak ay.  
  
 `day`  
 Gerekli. 1 ile 31 arasında bir tamsayı olarak tarih.  
  
 `hours`  
 İsteğe bağlı. Sağlanması gereken `minutes` sağlanır. Saati belirten bir tamsayı 0 ile 23 (11 pm gece yarısı).  
  
 `minutes`  
 İsteğe bağlı. Sağlanması gereken `seconds` sağlanır. Dakika cinsinden belirten bir tamsayı 0 ile 59.  
  
 `seconds`  
 İsteğe bağlı. Sağlanması gereken `milliseconds` sağlanır. Saniye belirten bir tamsayı 0 ile 59.  
  
 `ms`  
 İsteğe bağlı. Milisaniye olarak belirten bir tamsayı 0 ila 999 arasında.  
  
## <a name="remarks"></a>Açıklamalar  
 `Date.UTC` İşlevi gece, 1 Ocak 1970'ten UTC sağlanan tarih arasındaki milisaniye sayısını döndürür. Bu dönüş değeri kullanılabilir `setTime` yöntemi ve `Date` nesne Oluşturucusu. Bağımsız değişken değeri, kendi aralığından daha büyük ya negatif bir sayı ise diğer depolanan değerleri uygun şekilde değiştirilmiştir. Örneğin, 150 saniye belirtirseniz [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] bu sayıyı iki dakika ile 30 saniye yeniden tanımlamaktadır.  
  
 Arasındaki farkı `Date.UTC` işlevi ve `Date` bir tarih kabul Nesne oluşturucusu olan `Date.UTC` işlevi, UTC varsayar ve `Date` Nesne oluşturucusu yerel saat varsayar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Date.UTC` işlevi.  
  
```JavaScript  
// Determine the milliseconds per day.  
 var MinMilli = 1000 * 60;  
var HrMilli = MinMilli * 60;  
var DyMilli = HrMilli * 24;  
  
var date = new Date("June 1, 1990");  
var year = date.getFullYear();  
var month = date.getMonth();  
var day = date.getDay();  
  
var newDay = new Date("January 16, 2020");  
var yeartoday = newDay.getUTCFullYear();  
var monthtoday = newDay.getUTCMonth();  
var dayofmonthtoday = newDay.getUTCDate();  
  
// Get the milliseconds since 1/1/1970 UTC.  
var t1 = Date.UTC(year, month - 1, day)  
var t2 = Date.UTC(yeartoday, monthtoday, dayofmonthtoday);  
  
// Determine the difference in days.  
var days = (t2 - t1) / DyMilli;  
  
document.write(days);  
// Output: 10848  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [setTime yöntemi (tarih)](../../javascript/reference/settime-method-date-javascript.md)