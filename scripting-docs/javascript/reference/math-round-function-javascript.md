---
title: Math.round işlevi (JavaScript) | Microsoft Docs
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
- round
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Round method
- Math object
ms.assetid: 51008df3-5d0c-4951-84cb-4f41000db0be
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9543d529e3d0e4e45cff29f1286edbfad8dc0e27
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791267"
---
# <a name="mathround-function-javascript"></a>Math.round İşlevi (JavaScript)
En yakın tamsayıya yuvarlanan sağlanan sayısal bir ifade döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
Math.round(  
number  
)   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `number` bağımsız değişkeni, sistemi, en yakın tamsayıya yuvarlanacak değerdir.  
  
 Pozitif sayıları için ondalık kısmı `number` 0,5 veya daha büyükse, dönüş değeri sıfırdan küçük tamsayı değerine eşit olan `number`. Ondalık kısmı 0,5 değerinden dönüş değeri en büyük tamsayı küçük veya eşit ise, `number`.  
  
 Negatif sayı ondalık kısmı tam olarak ise-0.5, dönüş değeri olan sayısından daha büyük olan en küçük tamsayı.  
  
 Örneğin, `Math.round(8.5)` 9, verir ancak `Math.round(-8.5)` -8 döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [matematik nesnesi](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Math.random işlevi](../../javascript/reference/math-random-function-javascript.md)