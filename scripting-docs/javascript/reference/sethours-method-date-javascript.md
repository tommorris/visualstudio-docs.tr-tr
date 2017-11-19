---
title: "setHours yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- hours
- setHours method
- dates, setting
ms.assetid: 460f742d-f8d2-4874-9d07-2fb969fef066
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f9757f8416953eaf756dba96b91100527606cf9c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="sethours-method-date-javascript"></a>setHours Yöntemi (Tarih) (JavaScript)
Saat değeri ayarlar `Date` yerel saat kullanarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setHours(numHours[, numMin[, numSec[, numMilli]]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numHours`  
 Gerekli. Bir sayısal değer saat değerine eşit.  
  
 `numMin`  
 İsteğe bağlı. Bir sayısal değer dakika değerine eşit. Şu bağımsız değişkenleri herhangi birini kullanıldığında sağlanmalıdır.  
  
 `numSec`  
 İsteğe bağlı. Bir sayısal değer saniye değerine eşit. Şu bağımsız değişkenle kullanıldığında sağlanmalıdır.  
  
 `numMilli`  
 İsteğe bağlı. Bir sayısal değer milisaniye değerine eşit.  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm **ayarlamak** isteğe bağlı bağımsız değişken almama yöntemleri kullanın ilgili döndürülen değer **almak** isteğe bağlı bir bağımsız değişken belirtmezseniz, yöntem. Örneğin, varsa `numMinutes` bağımsız değişken belirtilmezse, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] döndürülen değeri kullanır `getMinutes` yöntemi.  
  
 Evrensel Eşgüdümlü saate (UTC) kullanarak saat değeri ayarlamak için kullanın `setUTCHours` yöntemi.  
  
 Bağımsız değişken değeri kendi aralığından daha büyük ya negatif bir sayı ise, diğer depolanan değerleri uygun şekilde değiştirilmiştir. Saklı tarih ise, örneğin, "5 Oca 1996 00:00:00", ve **setHours(30)** olduğu adlı Tarihi değiştirilir "6 Oca 1996 06:00:00." Negatif sayılar benzer davranışlara sahiptir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setHours` yöntemi.  
  
```JavaScript  
function SetHoursDemo(nhr, nmin, nsec){  
   var d, s;                     //Declare variables.  
   d = new Date();               //Create Date object.  
   d.setHours(nhr, nmin, nsec);  //Set hours, minutes, & seconds.  
   s = "Current setting is " + d.toLocaleString()   
   return(s);                    //Return new date setting.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getHours yöntemi (tarih)](../../javascript/reference/gethours-method-date-javascript.md)   
 [getUTCHours yöntemi (tarih)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setUTCHours yöntemi (tarih)](../../javascript/reference/setutchours-method-date-javascript.md)