---
title: "toLocaleString yöntemi (nesne) (JavaScript) | Microsoft Docs"
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
- toLocaleString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLocaleString method
ms.assetid: 0901afcb-126b-4ed7-bd6a-2301d50e2326
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f88e1c702cd8a7d702630ae90ef840c4af88f30
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="tolocalestring-method-object-javascript"></a>toLocaleString Yöntemi (Nesne) (JavaScript)
Bir tarih döndürür geçerli yerel kullanarak bir dizeye dönüştürülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.toLocaleString()   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `dateObj` herhangi `Date` nesnesi.  
  
 `toLocaleString` Yöntemi döndürür bir `String` geçerli yerel uzun varsayılan biçimde yazılmış tarihi içeren nesne.  
  
-   1601 1999 M.S. arasındaki tarihleri, tarih kullanıcının Denetim Masası bölgesel ayarları göre biçimlendirilir.  
  
-   Bu aralık, varsayılan biçimi dışında tarihler için **toString** yöntemi kullanılır.  
  
 Örneğin, Amerika Birleşik Devletleri'nde `toLocaleString` döndürür "01/05/96 00:00:00" 5 Ocak için. Avrupa'da, döndürdüğü "01/05/96 00:00:00" aynı tarih için Avrupa kuralı ay önceki gün koyar.  
  
> [!NOTE]
>  `toLocaleString`yalnızca bir kullanıcıya sonuçları görüntülemek için kullanılması gereken; döndürülen sonuç makineye özel olarak, hiçbir zaman temel olarak bir komut dosyası içinde hesaplama için kullanılmalıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `toLocaleString` yöntemi.  
  
```JavaScript  
function toLocaleStrDemo(){     
   var d, s;                      //Declare variables.  
   d = new Date();                //Create Date object.  
   s = "Current setting is ";  
   s += d.toLocaleString();       //Convert to current locale.  
   return(s);                     //Return converted date  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [dizi nesnesi](../../javascript/reference/array-object-javascript.md)&#124; [Tarih nesne](../../javascript/reference/date-object-javascript.md)&#124; [Sayı nesne](../../javascript/reference/number-object-javascript.md)&#124; [Nesne nesnesi](../../javascript/reference/object-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleDateString yöntemi (tarih)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)