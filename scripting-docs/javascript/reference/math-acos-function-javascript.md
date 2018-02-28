---
title: "Math.acos işlevi (JavaScript) | Microsoft Docs"
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
- acos
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- acos method
- arcosine method
ms.assetid: 828cb3c3-bdf7-4bb7-97ae-3617ce4b2d62
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 773499287e215fbc161f289954811d3ef62bcba6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="mathacos-function-javascript"></a>Math.acos İşlevi (JavaScript)
Bir sayının ark kosinüsünü (veya ters kosinüsünü) döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Math.acos(number)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `number` bağımsız değişken sayısal bir ifadedir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ark kosinüsünü `number` radyan cinsinden bağımsız değişkeni.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `acos` işlevi.  
  
```JavaScript  
var v1 = Math.acos(-1.0);  
var v2 = Math.cos(-1.0);  
  
document.write(v1);  
document.write("<br/>");  
document.write(v2);  
  
// Output:  
// 3.141592653589793  
// 0.5403023058681398  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Uygulandığı öğe**: [matematik nesnesi](../../javascript/reference/math-object-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Math.asin işlevi](../../javascript/reference/math-asin-function-javascript.md)   
 [Math.atan işlevi](../../javascript/reference/math-atan-function-javascript.md)   
 [Math.cos işlevi](../../javascript/reference/math-cos-function-javascript.md)   
 [Math.sin işlevi](../../javascript/reference/math-sin-function-javascript.md)   
 [Math.tan işlevi](../../javascript/reference/math-tan-function-javascript.md)   
 [Matematik nesnesi](../../javascript/reference/math-object-javascript.md)