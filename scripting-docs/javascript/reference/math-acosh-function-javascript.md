---
title: Math.ACOSH işlevi (JavaScript) | Microsoft Docs
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
ms.assetid: 881dd2a0-36a5-403b-a3dc-523d8e1e1317
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1fd75140dfcf3d9ac703c2aeadf68bea4da9e0dc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791222"
---
# <a name="mathacosh-function-javascript"></a>Math.acosh İşlevi (JavaScript)
Bir sayının hiperbolik kosinüsünü (veya ters hiperbolik Kosinüs) döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Math.acosh(number)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `number` bağımsız değişken sayısal bir ifadedir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ters hiperbolik kosinüsünü `number` radyan cinsinden bağımsız değişkeni.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `acosh` işlevi.  
  
```JavaScript  
var v1 = Math.acosh(3);  
vary v2 = Math.acosh(-1);  
  
document.write(v1);  
document.write("</br>");  
document.write(v2);  
  
// Output:  
// 1.762747174039086  
// NaN  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Uygulandığı öğe**: [matematik nesnesi](../../javascript/reference/math-object-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Math.acos işlevi](../../javascript/reference/math-acos-function-javascript.md)   
 [Math.asin işlevi](../../javascript/reference/math-asin-function-javascript.md)   
 [Math.atan işlevi](../../javascript/reference/math-atan-function-javascript.md)   
 [Math.cos işlevi](../../javascript/reference/math-cos-function-javascript.md)   
 [Math.sin işlevi](../../javascript/reference/math-sin-function-javascript.md)   
 [Math.tan işlevi](../../javascript/reference/math-tan-function-javascript.md)   
 [Matematik nesnesi](../../javascript/reference/math-object-javascript.md)