---
title: "getSeconds yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- seconds method
- GetSeconds method
ms.assetid: 97b10674-af0b-4681-a846-38f972196501
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 151d720b92fb9d7068c320983a25b965078f1b2e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getseconds-method-date-javascript"></a>getSeconds Metodu (Tarih) (JavaScript)
Saniye cinsinden alır bir `Date` nesnesi, yerel saat kullanarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getSeconds()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 0 ile 59 arasında bir tamsayı döndürür. Bir saniyeden kısa bir süre içinde geçerli dakikada gerektiğinde sıfır döndürülür. Varsa bir `Date` nesnesi oluşturulduğu saat belirtmeden, varsayılan olarak saniye değeri 0'dır.  
  
## <a name="remarks"></a>Açıklamalar  
 Evrensel Eşgüdümlü saate (UTC) kullanarak değeri saniye almak için `getUTCSeconds` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `getSeconds` yöntemi.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getSeconds());  
document.write("<br/>");  
  
date.setSeconds(5);  
document.write(date.getSeconds());  
  
// Output:  
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getUTCSeconds yöntemi (tarih)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setSeconds yöntemi (tarih)](../../javascript/reference/setseconds-method-date-javascript.md)   
 [setUTCSeconds yöntemi (tarih)](../../javascript/reference/setutcseconds-method-date-javascript.md)