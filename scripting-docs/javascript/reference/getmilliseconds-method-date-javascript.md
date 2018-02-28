---
title: "getMilliseconds yöntemi (tarih) (JavaScript) | Microsoft Docs"
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
- getMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- getMilliseconds method
ms.assetid: 1b512146-1e8a-44a4-89da-6cc5338d15cb
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33e5fc54dffbe06e47f0978e6cef94b1f650c90f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getmilliseconds-method-date-javascript"></a>getMilliseconds Metodu (Tarih) (JavaScript)
Yerel saat kullanarak, bir tarihin milisaniye alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getMilliseconds()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir tarih milisaniye olarak döndürür. Değeri 0-999 aralığında değişebilir. Milisaniye belirtmeden oluşturulan bir tarih değilse, döndürülen değer 0'dır.  
  
## <a name="remarks"></a>Açıklamalar  
 Evrensel Eşgüdümlü saate (UTC) milisaniye sayısını almak üzere kullanmak `getUTCMilliseconds` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir **getMilliseconds** yöntemi.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getMilliseconds());  
document.write("<br/>");  
  
date.setMilliseconds(5);  
document.write(date.getMilliseconds());  
// Output:   
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getUTCMilliseconds yöntemi (tarih)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setMilliseconds yöntemi (tarih)](../../javascript/reference/setmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds yöntemi (tarih)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)