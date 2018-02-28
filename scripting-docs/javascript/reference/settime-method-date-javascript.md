---
title: "setTime yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- setTime
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- SetTime method
- time method
ms.assetid: 86584748-7219-495b-bf56-e27f5782778c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e66b1fbf5d668330eb727e8bfc50ee9d11a28be3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="settime-method-date-javascript"></a>setTime Yöntemi (Tarih) (JavaScript)
Tarih ve saat değeri ayarlar `Date` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setTime(milliseconds)   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 *milisaniye*  
 Gerekli. 1 Ocak 1970 GMT gece bu yana geçen milisaniye sayısını temsil eden bir sayısal değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa *milisaniye* olan negatif bu 1970'ten önceki bir tarihi gösterir. Kullanılabilir tarihleri yaklaşık 285,616 yıl 1970'ten her iki tarafında aralığıdır.  
  
 Tarih ve saati ile ayarlama `setTime` yöntemdir saat dilimini bağımsız.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setTime` yöntemi.  
  
```JavaScript  
function SetTimeTest(newtime){  
   var d, s;                  //Declare variables.  
   d = new Date();            //Create Date object.  
   d.setTime(newtime);        //Set time.  
   s = "Current setting is ";  
   s += d.toUTCString();  
   return(s);                 //Return new setting.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getTime yöntemi (tarih)](../../javascript/reference/gettime-method-date-javascript.md)