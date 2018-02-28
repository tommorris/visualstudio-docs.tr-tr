---
title: "charCodeAt yöntemi (dize) (JavaScript) | Microsoft Docs"
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
- charCodeAt
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- charCodeAt method
ms.assetid: 5b0290a7-ee4d-4738-a909-c02ef64a2f1a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e7b8e62dfd29aa42d9816d0c5e27cc90440751a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="charcodeat-method-string-javascript"></a>charCodeAt Yöntemi (Dize) (JavaScript)
Belirtilen konumda karakterin Unicode değerini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
strObj. charCodeAt(index)  
```  
  
## <a name="parameters"></a>Parametreler  
 `strObj`  
 Gerekli. Tüm `String` nesne veya dize sabit değeri.  
  
 `index`  
 Gerekli. İstenen karakter sıfır tabanlı dizini. Belirtilen dizindeki hiçbir karakter ise `NaN` döndürülür.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `charCodeAt` yöntemi.  
  
```JavaScript  
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";   
document.write(str.charCodeAt(str.length - 1));  
  
// Output: 90   
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [String.fromCharCode işlevi](../../javascript/reference/string-fromcharcode-function-javascript.md)