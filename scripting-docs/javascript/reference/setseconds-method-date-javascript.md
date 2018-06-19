---
title: setSeconds yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- setSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- setSeconds method
- seconds method
ms.assetid: 986ffa54-1db6-4af2-ab8b-8353f64f0b57
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b8d545307f6aac3506310c868a2860a6159a106
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791561"
---
# <a name="setseconds-method-date-javascript"></a>setSeconds Yöntemi (Tarih) (JavaScript)
Saniye değerini ayarlar `Date` yerel saat kullanarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj  
.setSeconds(  
numSeconds[, numMilli])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 *numSeconds*  
 Gerekli. Bir sayısal değer saniye değerine eşit.  
  
 `numMilli`  
 İsteğe bağlı. Bir sayısal değer milisaniye değerine eşit.  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm **ayarlamak** isteğe bağlı bağımsız değişken almama yöntemleri kullanın ilgili döndürülen değer **almak** isteğe bağlı bir bağımsız değişken belirtmezseniz, yöntem. Örneğin, varsa `numMilli` bağımsız değişken belirtilmezse, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] döndürülen değeri kullanır **getMilliseconds** yöntemi.  
  
 Evrensel Eşgüdümlü saate (UTC) kullanarak değeri saniye ayarlamak için kullanın `setUTCSeconds` yöntemi.  
  
 Bağımsız değişken değeri kendi aralığından daha büyük ya negatif bir sayı ise, diğer depolanan değerleri uygun şekilde değiştirilmiştir. Saklı tarih ise, örneğin, "5 Oca 1996 00:00:00" ve **setSeconds(150)** olduğu adlı Tarihi değiştirilir "5 Oca 1996 00:02:30."  
  
 `setHours` Yöntemi, saat, dakika, saniye ve milisaniye olarak ayarlamak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setSeconds` yöntemi.  
  
```JavaScript  
function SetSecondsDemo(nsec){  
   var d = new Date();         //Create Date object.  
   d.setSeconds(nsec);         //Set seconds.  
   var s = "Current setting is ";  
   s += d.toLocaleString();  
   return(s);                  //Return new setting.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getSeconds yöntemi (tarih)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [getUTCSeconds yöntemi (tarih)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setUTCSeconds yöntemi (tarih)](../../javascript/reference/setutcseconds-method-date-javascript.md)