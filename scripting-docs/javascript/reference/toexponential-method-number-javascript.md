---
title: "toExponential yöntemi (sayı) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toExponential
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toExponential method
ms.assetid: 7c4a6d84-3c1f-4cc4-a67d-7753e5d4ed66
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fff2f2bc0c443fa9308c8d01dcea42a3cec9ff04
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="toexponential-method-number-javascript"></a>toExponential Yöntemi (Sayı) (JavaScript)
Sayıyı üstel gösterimde temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
numObj. toExponential([fractionDigits])  
```  
  
## <a name="parameters"></a>Parametreler  
 `numObj`  
 Gerekli. A **numarası** nesnesi.  
  
 `fractionDigits`  
 İsteğe bağlı. Ondalık basamak sayısı. 0 - 20 (bunlar dahil) aralığında olmalıdır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Üstel gösterimde birkaç dize gösterimini döndürür. Dizeyi bir sayı ondalık ayırıcıdan önce içerir ve içerebilir `fractionDigits` onu basamak.  
  
 Varsa `fractionDigits` sağlanmaz, `toExponential` yöntemi sayıda basamak sayısı benzersiz olarak belirlemek gerekli döndürür.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
var num = new Number(123);  
var exp = num.toExponential();  
document.write(exp);  
document.write("<br/>");  
  
num = new Number(123.456);  
exp = num.toExponential(5);  
document.write(exp);  
  
// Output:   
// 1.23e+2  
// 1.23456e+2  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [sayı nesnesi](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toFixed yöntemi (sayı)](../../javascript/reference/tofixed-method-number-javascript.md)   
 [toPrecision yöntemi (sayı)](../../javascript/reference/toprecision-method-number-javascript.md)