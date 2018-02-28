---
title: "setFullYear yöntemi (tarih) (JavaScript) | Microsoft Docs"
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
- setFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Year method
- setFullYear method
- dates, setting
ms.assetid: 635e4f5a-0210-4c01-8152-b0da4146f6ff
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e5e20a8486d1aefeab9b244c5f1e9d1b1e60c3f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="setfullyear-method-date-javascript"></a>setFullYear Yöntemi (Tarih) (JavaScript)
Yılın ayarlar `Date` yerel saat kullanarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setFullYear(numYear[, numMonth[, numDate]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numYear`  
 Gerekli. Yıl için sayısal bir değer.  
  
 `numMonth`  
 İsteğe bağlı. (0, 11 Ocak Aralık için için) ay için sıfır tabanlı bir sayısal değer. Belirtilmelidir `numDate` belirtilir.  
  
 `numDate`  
 İsteğe bağlı. Ayın günü için eşit sayısal değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm **ayarlamak** isteğe bağlı bağımsız değişken almama yöntemleri kullanın ilgili döndürülen değer **almak** isteğe bağlı bağımsız değişkeni belirtmezseniz, yöntem. Örneğin, varsa `numMonth` bağımsız değişken isteğe bağlıdır, ancak belirtilmedi, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] döndürülen değeri kullanır **getMonth** yöntemi.  
  
 Ayrıca, bir bağımsız değişkenin değeri kendi Takvim aralığından daha büyük ya da negatif ise tarihi ileriye veya geriye doğru uygun şekilde yapar.  
  
 Evrensel Eşgüdümlü saate (UTC) kullanarak yılı ayarlamak için kullanın `setUTCFullYear` yöntemi.  
  
 Tarih nesnesi desteklenen yıl yaklaşık 285,616 yıl önce ve 1970'ten sonra aralığıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setFullYear` yöntemi:  
  
```JavaScript  
var date1 = new Date("1/1/2001");  
date1.setFullYear(2007);  
  
var date2 = new Date("1/1/2001");  
date2.setFullYear(2008, 10, 3);   
  
document.write (date1.toLocaleString());  
document.write ("<br />");  
document.write (date2.toLocaleString());  
  
// Output:  
// Monday, January 01, 2007 12:00:00 AM  
// Monday, November 03, 2008 12:00:00 AM  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getFullYear yöntemi (tarih)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear yöntemi (tarih)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setUTCFullYear yöntemi (tarih)](../../javascript/reference/setutcfullyear-method-date-javascript.md)