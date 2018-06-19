---
title: parseFloat işlevi (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- parseFloat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parseFloat method
ms.assetid: a7d87a69-1919-4623-be85-972e6376dd2d
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb8f6d179abba887542e59d083141534732ed42a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791207"
---
# <a name="parsefloat-function-javascript"></a>parseFloat İşlevi (JavaScript)
Bir dizeyi bir kayan nokta sayıya dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
parseFloat(numString)   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `numString` bağımsız değişkeni bir kayan noktalı sayı içeren bir dize değil.  
  
 `parseFloat` İşlevi bir sayısal değer sayısına eşit içinde yer alan döndürür `numString`. Hiçbir öneki varsa `numString` bir kayan noktalı sayının başarıyla ayrıştırılabilir `NaN` (sayı değil) döndürülür.  
  
```JavaScript  
parseFloat("abc")      // Returns NaN.  
parseFloat("1.2abc")   // Returns 1.2.  
```  
  
 İçin test edebilirsiniz `NaN` kullanarak `isNaN` işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [genel nesne](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [isNaN işlevi](../../javascript/reference/isnan-function-javascript.md)   
 [parseInt işlevi](../../javascript/reference/parseint-function-javascript.md)   
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)