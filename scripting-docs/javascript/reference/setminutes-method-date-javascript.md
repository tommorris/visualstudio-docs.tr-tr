---
title: "setMinutes yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- setMinutes method
ms.assetid: 34c959cd-cd29-4cee-8e04-9061cf6d42f3
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ce40cb3ebf769cdd8f668e246e272833780434d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="setminutes-method-date-javascript"></a>setMinutes Yöntemi (Tarih) (JavaScript)
Dakika değeri ayarlar **tarih** yerel saat kullanarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setMinutes(numMinutes[, numSeconds[, numMilli]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numMinutes`  
 Gerekli. Bir sayısal değer dakika değerine eşit. Şu bağımsız değişkenleri herhangi birini kullanıldığında sağlanmalıdır.  
  
 *numSeconds*  
 İsteğe bağlı. Bir sayısal değer saniye değerine eşit. Sağlanması gereken `numMilli` bağımsız değişkeninin değeri kullanılır.  
  
 `numMilli`  
 İsteğe bağlı. Bir sayısal değer milisaniye değerine eşit.  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm **ayarlamak** isteğe bağlı bağımsız değişken almama yöntemleri kullanın ilgili döndürülen değer **almak** isteğe bağlı bir bağımsız değişken belirtmezseniz, yöntem. Örneğin, varsa *numSeconds* bağımsız değişken belirtilmezse, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] döndürülen değeri kullanır `getSeconds` yöntemi.  
  
 Evrensel Eşgüdümlü saate (UTC) kullanarak dakika değerini ayarlamak için kullanın `setUTCMinutes` yöntemi.  
  
 Bağımsız değişken değeri kendi aralığından daha büyük ya negatif bir sayı ise, diğer depolanan değerleri uygun şekilde değiştirilmiştir. Saklı tarih ise, örneğin, "5 Oca 1996 00:00:00" ve **setMinutes(90)** olduğu adlı Tarihi değiştirilir "5 Oca 1996 01:30:00." Negatif sayılar benzer davranışlara sahiptir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setMinutes` yöntemi.  
  
```JavaScript  
function SetMinutesDemo(nmin, nsec){  
   var d, s;                     // Declare variables.  
   d = new Date();               // Create Date object.  
   d.setMinutes(nmin, nsec);     // Set minutes.  
   s = "Current setting is " + d.toLocaleString()   
   return(s);                    // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getMinutes yöntemi (tarih)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [getUTCMinutes yöntemi (tarih)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setUTCMinutes yöntemi (tarih)](../../javascript/reference/setutcminutes-method-date-javascript.md)