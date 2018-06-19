---
title: toUpperCase yöntemi (dize) (JavaScript) | Microsoft Docs
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
- toUpperCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toUpperCase method
ms.assetid: 4fd4ccc3-e794-498a-9db1-baf48fc1dda1
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0b84de440fc9e3cece3b831b57a90be394e819ac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791708"
---
# <a name="touppercase-method-string-javascript"></a>toUpperCase Yöntemi (Dize) (JavaScript)
Bir dizede alfabetik tüm karakterleri büyük harfe çevirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      strVariable.toUpperCase()  
"String Literal".toUpperCase()   
```  
  
## <a name="remarks"></a>Açıklamalar  
 `toUpperCase` Yöntemi alfabetik olmayan karakterler üzerinde hiçbir etkisi vardır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, etkilerini gösterir `toUpperCase` yöntemi:  
  
```JavaScript  
var str1 = "This is a STRING.";  
var str2 = str1.toUpperCase();  
document.write(str2);  
  
// Output: THIS IS A STRING.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleUpperCase yöntemi (dize)](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)   
 [toLowerCase yöntemi](../../javascript/reference/tolowercase-method-javascript.md)