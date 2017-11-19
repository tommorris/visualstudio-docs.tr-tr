---
title: "Math.hypot işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 31488f5a-2230-4114-911e-b6d854c7b0a0
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a66c0b082356b8dde3f51f739c130378d694f3b4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="mathhypot-function-javascript"></a>Math.hypot İşlevi (JavaScript)
Bağımsız değişkenlerin kareler toplamı kare kökünü döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Math.hypot ( value1[, value2[, ...values] );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value1`  
 Gerekli. İlk sayı.  
  
 `value2`  
 İsteğe bağlı. İkinci sayı.  
  
 `values`  
 İsteğe bağlı. Bir veya daha fazla numarası.  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir bağımsız değişken NaN ise, NaN işlevi döndürür. Bağımsız değişkenler şunlardır sağlarsanız, işlev 0 döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kullanma örneği gösterir `Math.hypot` işlevi.  
  
```JavaScript  
Math.hypot(3, 4);  
// Returns 5  
  
Math.hypot(3, "4");  
// Returns 5  
  
Math.hypot(3, "four");  
// Returns NaN   
  
Math.hypot(3, 4, 10);  
// Returns 11.180339887498949  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]