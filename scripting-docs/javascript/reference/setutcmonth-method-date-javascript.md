---
title: "setUTCMonth yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setUTCMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- setUTCMonth method
- Month method
- UTC dates, setting
ms.assetid: cdac5f64-c4fd-44cc-ba3a-9a8dd3dd3fad
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02cb69026b66e3f307a8709ab3f5b23d9518643a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="setutcmonth-method-date-javascript"></a>setUTCMonth Yöntemi (Tarih) (JavaScript)
Ay değeri ayarlar `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setUTCMonth(numMonth[, dateVal])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numMonth`  
 Gerekli. Bir sayısal değer aya eşit. Ocak değeri 0'dır ve diğer ay değerlerini art arda izleyin.  
  
 `dateVal`  
 İsteğe bağlı. Ayın gününü temsil eden bir sayısal değer. Sağlanmazsa, çağrısından değer `getUTCDate` yöntemi kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel saat kullanarak ay değeri ayarlamak için kullanın `setMonth` yöntemi.  
  
 Varsa değerini `numMonth` 11 büyük (Ocak olan ay 0) veya negatif bir sayı saklı yıl uygun şekilde artırılır veya indirildiği. Örneğin saklı tarih "5 Oca 1996 00:00:00.00" ise ve **setUTCMonth(14)** olduğu adlı Tarihi değiştirilir "5 Mar 1997 00:00:00.00."  
  
 **SetUTCFullYear** yöntemi, yıl, ay ve ayın günü ayarlamak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setUTCMonth` yöntemi.  
  
```JavaScript  
function SetUTCMonthDemo(newmonth){  
   var d, s;                       // Declare variables.  
   d = new Date();                 // Create Date object.  
   d.setUTCMonth(newmonth);        // Set UTC month.  
   s = "Current setting is ";  
   s += d.toUTCString();   
   return(s);                      // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getMonth yöntemi (tarih)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [getUTCMonth yöntemi (tarih)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setMonth yöntemi (tarih)](../../javascript/reference/setmonth-method-date-javascript.md)