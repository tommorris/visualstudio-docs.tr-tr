---
title: "String.fromCharCode işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: fromCharCode
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- fromCharCodeAt method
- characters, from Unicode
ms.assetid: f64120c1-23a7-48ca-8d1c-db3e8856cab4
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dbcd9062d7da0b73647c1d9eb6cc207af23c3532
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="stringfromcharcode-function-javascript"></a>String.fromCharCode İşlevi (JavaScript)
Unicode karakter değerlerinden bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
String.fromCharCode([code1[, code2[, ...[, codeN]]]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `String`  
 Gerekli. `String` Nesnesi.  
  
 `code1`, . biçimindeki telefon numarasıdır. biçimindeki telefon numarasıdır. , `codeN`  
 İsteğe bağlı. Unicode karakter değeri bir dizeye dönüştürmek için bir dizi. Bağımsız değişkenler sağlandıysa boş dize sonucudur.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevi çağırmak `String` nesne yerine bir dize örneği.  
  
 Aşağıdaki örnekte bu yöntemin nasıl kullanılacağı gösterilmektedir:  
  
```JavaScript  
var test = String.fromCharCode(112, 108, 97, 105, 110);  
document.write(test);  
  
// Output: plain  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [charCodeAt yöntemi (dize)](../../javascript/reference/charcodeat-method-string-javascript.md)