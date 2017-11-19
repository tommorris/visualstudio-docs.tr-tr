---
title: "getTime yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getTime
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetTime method
- time method
ms.assetid: f0da1d4e-337c-497d-9205-093defbc6d3d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a31e542445e89a0e2f3364d36ae44f8d2d4cf9bb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="gettime-method-date-javascript"></a>getTime Metodu (Tarih) (JavaScript)
Zaman değeri, milisaniye cinsinden alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getTime()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Gece yarısından, 1 Ocak 1970'ten ve saat değeri arasındaki milisaniye sayısını döndürür `Date` nesnesi. Yaklaşık 285,616 yıl taraflardan gece yarısı, 1 Ocak 1970'ten tarihleri aralığıdır. Negatif sayılar 1970'ten önce tarihleri belirtin.  
  
## <a name="remarks"></a>Açıklamalar  
 Birden çok tarih ve saat hesaplamaları yaparken, gün, saat veya dakika değişkenleri milisaniye sayısına eşit tanımlamak isteyebilirsiniz. Örneğin:  
  
```JavaScript  
var minute = 1000 * 60;  
var hour = minute * 60;  
var day = hour * 24;  
```  
  
 Bkz: [hesaplama tarihler ve saatler (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md) nasıl kullanılacağı hakkında daha fazla bilgi için `getTime` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `getTime` yöntemi.  
  
```JavaScript  
var minute = 1000 * 60;  
var hour = minute * 60;  
var day = hour * 24;  
  
date = new Date("1/1/2001");  
var time = date.getTime();  
  
document.write(Math.round(time / day) + " days from 1/1/1970 to 1/1/2001");  
  
// Output: 11323 days from 1/1/1970 to 1/1/2001  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [setTime yöntemi (tarih)](../../javascript/reference/settime-method-date-javascript.md)