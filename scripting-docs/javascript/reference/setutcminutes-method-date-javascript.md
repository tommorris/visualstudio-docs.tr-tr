---
title: setUTCMinutes yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- setUTCMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- dates, UTC
- UTC times, setting
- setUTCMinutes method
ms.assetid: 2415e788-6d28-46dd-a103-0931a1fd1446
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37df1bcefa358f2c9076a3da877bd642d19178b0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791777"
---
# <a name="setutcminutes-method-date-javascript"></a>setUTCMinutes Yöntemi (Tarih) (JavaScript)
Dakika değeri ayarlar `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setUTCMinutes(numMinutes[, numSeconds[, numMilli]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numMinutes`  
 Gerekli. Bir sayısal değer dakika değerine eşit. Şu bağımsız değişkenleri herhangi birini kullanıldığında sağlanmalıdır.  
  
 *numSeconds*  
 İsteğe bağlı. Bir sayısal değer saniye değerine eşit. Sağlanması gereken `numMilli` kullanılır.  
  
 `numMilli`  
 İsteğe bağlı. Bir sayısal değer milisaniye değerine eşit.  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm **ayarlamak** isteğe bağlı bağımsız değişken almama yöntemleri kullanın ilgili döndürülen değer **almak** isteğe bağlı bir bağımsız değişken belirtmezseniz, yöntem. Örneğin, varsa *numSeconds* bağımsız değişken belirtilmezse, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] döndürülen değeri kullanır `getUTCSeconds` yöntemi.  
  
 Yerel saat kullanarak dakika değerini değiştirmek için `setMinutes` yöntemi.  
  
 Bağımsız değişken değeri, kendi aralığından daha büyük ya negatif bir sayı ise diğer depolanan değerleri uygun şekilde değiştirilmiştir. Örneğin saklı tarih "5 Oca 1996 00:00:00.00" ise ve **setUTCMinutes(70)** olduğu adlı Tarihi değiştirilir "5 Oca 1996 01:10:00.00."  
  
 **SetUTCHours** yöntemi, saat, dakika, saniye ve milisaniye olarak ayarlamak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setUTCMinutes` yöntemi:  
  
```JavaScript  
function SetUTCMinutesDemo(nmin, nsec){  
   var d, s;                    // Declare variables.  
   d = new Date();              // Create Date object.  
   d.setUTCMinutes(nmin,nsec);  // Set UTC minutes.  
   s = "Current setting is " + d.toUTCString()   
   return(s);                   // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getMinutes yöntemi (tarih)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [getUTCMinutes yöntemi (tarih)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setMinutes yöntemi (tarih)](../../javascript/reference/setminutes-method-date-javascript.md)