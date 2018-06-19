---
title: setUTCHours yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- setUTCHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- UTC times, setting
- setUTCHours method
ms.assetid: 257e36fd-fb06-4a4d-8634-d66a020a1511
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fe83735028f86d38ef270beac6c44dfa4caae7f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791834"
---
# <a name="setutchours-method-date-javascript"></a>setUTCHours Yöntemi (Tarih) (JavaScript)
Saat değeri ayarlar `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setUTCHours(numHours[, numMin[, numSec[, numMilli]]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numHours`  
 Gerekli. Bir sayısal değer saat değerine eşit.  
  
 `numMin`  
 İsteğe bağlı. Bir sayısal değer dakika değerine eşit. Her iki sağlanmalıdır `numSec` veya `numMilli` kullanılır.  
  
 `numSec`  
 İsteğe bağlı. Bir sayısal değer saniye değerine eşit. Sağlanması gereken `numMilli` bağımsız değişkeninin değeri kullanılır.  
  
 `numMilli`  
 İsteğe bağlı. Bir sayısal değer milisaniye değerine eşit.  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm **ayarlamak** isteğe bağlı bağımsız değişken almama yöntemleri kullanın ilgili döndürülen değer **almak** isteğe bağlı bir bağımsız değişken belirtmezseniz, yöntem. Örneğin, varsa `numMin` bağımsız değişken belirtilmezse, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] döndürülen değeri kullanır `getUTCMinutes` yöntemi.  
  
 Yerel saat kullanarak saat değeri ayarlamak için kullanın `setHours` yöntemi.  
  
 Bağımsız değişken değeri, kendi aralığından daha büyük ya negatif bir sayı ise diğer depolanan değerleri uygun şekilde değiştirilmiştir. Örneğin saklı tarih "5 Oca 1996 00:00:00.00" ise ve **setUTCHours(30)** olduğu adlı Tarihi değiştirilir "6 Oca 1996 06:00:00.00."  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setUTCHours` yöntemi.  
  
```JavaScript  
function SetUTCHoursDemo(nhr, nmin, nsec){     
   var d, s;                        // Declare variables.  
   d = new Date();                  // Create Date object.  
   d.setUTCHours(nhr, nmin, nsec);  // Set UTC hours, minutes, seconds.  
   s = "Current setting is " + d.toUTCString()   
   return(s);                       // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getHours yöntemi (tarih)](../../javascript/reference/gethours-method-date-javascript.md)   
 [getUTCHours yöntemi (tarih)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setHours yöntemi (tarih)](../../javascript/reference/sethours-method-date-javascript.md)