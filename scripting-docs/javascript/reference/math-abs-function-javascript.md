---
title: "Math.abs işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: abs
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- absolute values, calculating
- absolute values
- numeric expressions
- abs method
ms.assetid: 9af4b5b8-de77-47bb-bb59-abdde371e4c3
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5719905a7de375f1b409378f0579e3d8b25209fc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="mathabs-function-javascript"></a>Math.abs İşlevi (JavaScript)
(Olumlu veya olumsuz olup dikkate almaksızın değer) bir sayının mutlak değerini döndürür. Örneğin, mutlak değeri -5, 5 mutlak değerini aynıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Math.abs(number)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `number` bağımsız değişkeni olan sayısal ifadenin mutlak değeri gereklidir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Mutlak değerini `number` bağımsız değişkeni.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `abs` işlevi.  
  
```JavaScript  
var s;  
var v1 = Math.abs(6);  
var v2 = Math.abs(-6);  
if (v1 == v2) {  
    document.write("Absolute values are the same.");  
}  
else {  
document.write("Absolute values are different.");  
}  
  
// Output: Absolute values are the same.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [matematik nesnesi](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Matematik nesnesi](../../javascript/reference/math-object-javascript.md)