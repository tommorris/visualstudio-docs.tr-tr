---
title: Number.issafeınteger (sayı) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c7ef6ce8-fe71-4e53-be44-4dd440aef21d
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eebc2147bc5043341be7e883548af825922036f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791015"
---
# <a name="numberissafeinteger-number-javascript"></a>Number.isSafeInteger (Sayı) (JavaScript)
Bir sayı güvenle JavaScript'te temsil edilebilir olup olmadığını gösteren bir Boole değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Number.isSafeInteger(numValue)   
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`sayı arasında ise `Number.MIN_SAFE_INTEGER` ve `Number.MAX_SAFE_INTEGER`, kapsayıcı aksi `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir güvenli JavaScript içindeki herhangi bir yuvarlama uygulanmadan önce bir IEEE 754 çift Precision bilgisayarlar numarası olan bir tamsayıdır.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
// Returns true  
Number.isSafeInteger(-100)  
Number.isSafeInteger(9007199254740991)  
  
// Returns false  
Number.isSafeInteger(Number.NaN)  
Number.isSafeInteger(Infinity)  
Number.isSafeInteger("100")  
Number.isSafeInteger(9007199254740992);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **Uygulandığı öğe**: [sayı nesnesi](../../javascript/reference/number-object-javascript.md)