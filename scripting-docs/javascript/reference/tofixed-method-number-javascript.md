---
title: "toFixed yöntemi (sayı) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toFixed
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toFixed method
ms.assetid: b5f03400-865e-4ab2-818c-f734c0f6d6f0
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd51dd67632f4e6417fee72fd19575025423bbf1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="tofixed-method-number-javascript"></a>toFixed Yöntemi (Sayı) (JavaScript)
Sabit noktalı gösterim sayıyı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
numObj.toFixed([fractionDigits])  
```  
  
## <a name="parameters"></a>Parametreler  
 `numObj`  
 Gerekli bir `Number` nesnesi.  
  
 `fractionDigits`  
 İsteğe bağlı. Ondalık basamak sayısı. 0 - 20 (bunlar dahil) aralığında olmalıdır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sabit noktalı gösterimde, bir sayı dize gösterimini döndürür içeren `fractionDigits` ondalık basamak.  
  
 Varsa `fractionDigits` sağlanmadığında veya **tanımsız**, varsayılan değer sıfır olur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `toFixed`.  
  
```JavaScript  
var num = new Number(123);  
var fix = num.toFixed();  
document.write(fix);  
document.write("<br/>");  
  
num = new Number(123.456);  
fix = num.toFixed(5);  
document.write(fix);  
  
// Output:  
// 123  
123.45600  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [sayı nesnesi](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toExponential yöntemi (sayı)](../../javascript/reference/toexponential-method-number-javascript.md)   
 [toPrecision yöntemi (sayı)](../../javascript/reference/toprecision-method-number-javascript.md)