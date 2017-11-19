---
title: "getMonth yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, month value
- Month method
- GetMonth method
ms.assetid: c20dd8ba-1d78-42f1-8717-ed3dfd2362dd
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeffd7ffc7bee5fa63607e342a9a9dced7088d35
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getmonth-method-date-javascript"></a>getMonth Metodu (Tarih) (JavaScript)
Yerel saat kullanarak ay alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getMonth()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `getMonth` Yöntemi, 0 (Ocak) ile 11 (aralık) arasında bir tamsayı döndürür. İçin bir `Date` "5 Oca 1996 ile" oluşturulan `getMonth` 0 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Evrensel Eşgüdümlü saate (UTC) kullanarak ay değeri almak için kullanmak `getUTCMonth` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `getMonth` yöntemi.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getMonth());  
  
// Output: 0  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getUTCMonth yöntemi (tarih)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setMonth yöntemi (tarih)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCMonth yöntemi (tarih)](../../javascript/reference/setutcmonth-method-date-javascript.md)