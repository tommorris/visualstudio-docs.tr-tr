---
title: "getMinutes yöntemi (tarih) (JavaScript) | Microsoft Docs"
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
- getMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetMinutes method
- minutes method
ms.assetid: d4139b5d-04e1-474c-9a83-e9d40597243a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff08fd84345c9ceb816444a1b44643a8353b60b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getminutes-method-date-javascript"></a>getMinutes Metodu (Tarih) (JavaScript)
Dakika cinsinden alır bir `Date` nesnesi, yerel saat kullanarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getMinutes()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 0 ile 59 arasında bir tamsayı döndürür. Sıfır bir dakikadan az bir saat sonra saattir döndürülür. Varsa bir `Date` nesnesi oluşturulduğu saat belirtmeden, varsayılan olarak dakika değeri 0'dır.  
  
## <a name="remarks"></a>Açıklamalar  
 Evrensel Eşgüdümlü saate (UTC) ile dakika değerini almak için kullanın `getUTCMinutes` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl `getMinutes` yöntemi.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getMinutes());  
document.write("<br/>");  
  
date.setMinutes(5);  
document.write(date.getMinutes());  
  
// Output:  
// 0  
// 5  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getUTCMinutes yöntemi (tarih)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setMinutes yöntemi (tarih)](../../javascript/reference/setminutes-method-date-javascript.md)   
 [setUTCMinutes yöntemi (tarih)](../../javascript/reference/setutcminutes-method-date-javascript.md)