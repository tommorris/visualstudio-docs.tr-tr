---
title: "getUTCHours yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- hours
- UTC times, returning
- getUTCHours method
ms.assetid: 7c9825dd-4b3a-4614-8e09-f40df123b630
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 34a07f9f63fe22d3101cc748e9dde978385a71ab
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getutchours-method-date-javascript"></a>getUTCHours Metodu (Tarih) (JavaScript)
Saat değerini alır bir `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getUTCHours()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 0 ile 23 saat gece yarısından sayısını belirten arasında bir tamsayı döndürür. Saat 1:00: 00'da önce ise sıfır döndürülür. Varsa bir `Date` nesnesi oluşturulduğu saat belirtmeden, varsayılan olarak 0 UTC saati saattir. Bu süre sıfır olabilir diğer saat diliminde.  
  
## <a name="remarks"></a>Açıklamalar  
 Saat sayısını almak üzere gece yarısından beri geçen yerel saat, kullanarak `getHours` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `getUTCHours` yöntemi.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getUTCHours());  
document.write("<br/>");  
  
var date2 = new Date("1/1/2001 11:22:33");  
document.write(datee.getUTCHours());  
  
// Output (in the PST time zone):  
// 8  
// 19  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getHours yöntemi (tarih)](../../javascript/reference/gethours-method-date-javascript.md)   
 [setHours yöntemi (tarih)](../../javascript/reference/sethours-method-date-javascript.md)   
 [setUTCHours yöntemi (tarih)](../../javascript/reference/setutchours-method-date-javascript.md)