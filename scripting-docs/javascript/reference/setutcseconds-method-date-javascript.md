---
title: setUTCSeconds yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- setUTCSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- setUTCSeconds method
- UTC times, setting
- seconds method
ms.assetid: e035e282-b39d-4d1d-8771-c17542fd6493
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f3df010cd84332d8957f1c08c41c4543dec36e4a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791672"
---
# <a name="setutcseconds-method-date-javascript"></a>setUTCSeconds Yöntemi (Tarih) (JavaScript)
Saniye değerini ayarlar `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setUTCSeconds(numSeconds[, numMilli])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 *numSeconds*  
 Gerekli. Bir sayısal değer saniye değerine eşit.  
  
 `numMilli`  
 İsteğe bağlı. Bir sayısal değer milisaniye değerine eşit.  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm **ayarlamak** isteğe bağlı bağımsız değişken almama yöntemleri kullanın ilgili döndürülen değer **almak** isteğe bağlı bir bağımsız değişken belirtmezseniz, yöntem. Örneğin, varsa `numMilli` bağımsız değişken belirtilmezse, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] döndürülen değeri kullanır `getUTCMilliseconds` yöntemi.  
  
 Yerel saat kullanarak değeri saniye ayarlamak için kullanın `setSeconds` yöntemi.  
  
 Bağımsız değişken değeri kendi aralığından daha büyük ya negatif bir sayı ise, diğer depolanan değerleri uygun şekilde değiştirilmiştir. Örneğin saklı tarih "5 Oca 1996 00:00:00.00" ise ve **setSeconds(150)** olduğu adlı Tarihi değiştirilir "5 Oca 1996 00:02:30.00."  
  
 **SetUTCHours** yöntemi, saat, dakika, saniye ve milisaniye olarak ayarlamak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setUTCSeconds` yöntemi.  
  
```JavaScript  
function SetUTCSecondsDemo(nsec){  
// Create Date object.  
    var d = new Date();       
// Set UTC seconds.  
    d.setUTCSeconds(nsec);    
    var s = "Current setting is ";  
    s += d.toUTCString();  
// Return new setting.  
    return(s);                
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getSeconds yöntemi (tarih)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [getUTCSeconds yöntemi (tarih)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setSeconds yöntemi (tarih)](../../javascript/reference/setseconds-method-date-javascript.md)