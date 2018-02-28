---
title: "setUTCDate yöntemi (tarih) (JavaScript) | Microsoft Docs"
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
- setUTCDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- dates, setting
- UTC dates, setting
- setUTCDate method
ms.assetid: e6c3b876-70fe-4103-b197-6c84c078ce10
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5631a36c8b1c4f1ee50dcadb39f0f21ae5aa28e3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="setutcdate-method-date-javascript"></a>setUTCDate Yöntemi (Tarih) (JavaScript)
Ayın sayısal günü ayarlar `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setUTCDate(numDate)   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 *numDate*  
 Gerekli. Ayın gününü eşit sayısal değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel saat kullanarak ayın günü ayarlamak için kullanın `setDate` yöntemi.  
  
 Varsa değerini *numDate* depolanan aydaki gün sayısından daha büyük **tarih** nesne veya negatif bir sayı tarihi eşit bir tarih olarak ayarlamak *numDate* eksi saklı aydaki gün sayısı. Örneğin, saklı tarih 5 Ocak 1996 ise ve **setUTCDate(32)** çağrılır, 1 Şubat 1996 tarih yapılan değişiklikler. Negatif sayılar benzer davranışlara sahiptir.  
  
 **SetUTCFullYear** yöntemi, yıl, ay ve ayın günü ayarlamak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setUTCDate` yöntemi.  
  
```JavaScript  
function SetUTCDateDemo(newdayofmonth){  
   var d = new Date();           // Create Date object.  
   d.setUTCDate(newdayofmonth);  // Set UTC day of month.  
   var s = "Current setting is ";  
   s += d.toUTCString();   
   return(s);                    // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getDate yöntemi (tarih)](../../javascript/reference/getdate-method-date-javascript.md)   
 [getUTCDate yöntemi (tarih)](../../javascript/reference/getutcdate-method-date-javascript.md)   
 [setDate yöntemi (tarih)](../../javascript/reference/setdate-method-date-javascript.md)