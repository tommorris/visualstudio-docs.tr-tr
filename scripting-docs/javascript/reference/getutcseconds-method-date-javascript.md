---
title: "getUTCSeconds yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- UTC times, returning
- seconds method
- getUTCSeconds method
ms.assetid: 2d8ea7dc-79f8-4a9b-b2ab-732db2bcd5fd
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4f398145f8e31ed633bf3215de7d5a5ef669b7ef
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcseconds-method-date-javascript"></a>getUTCSeconds Metodu (Tarih) (JavaScript)
Saniye cinsinden alır bir `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getUTCSeconds()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 0 ile 59 arasında bir tamsayı döndürür. Bir saniyeden kısa bir süre içinde geçerli dakikada gerektiğinde sıfır döndürülür. Varsa bir `Date` nesnesi oluşturulduğu saat belirtmeden, varsayılan olarak UTC saniye değeri 0'dır.  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel saatle saniye sayısını almak için `getSeconds` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `getUTCSeconds` yöntemi.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date. getUTCSeconds());  
  
// Output: 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getSeconds yöntemi (tarih)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [setSeconds yöntemi (tarih)](../../javascript/reference/setseconds-method-date-javascript.md)   
 [setUTCSeconds yöntemi (tarih)](../../javascript/reference/setutcseconds-method-date-javascript.md)