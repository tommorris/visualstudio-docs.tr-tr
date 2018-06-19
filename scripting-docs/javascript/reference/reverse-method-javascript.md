---
title: reverse yöntemi (JavaScript) | Microsoft Docs
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
- reverse
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arrays [Visual Studio], reversing elements
- reverse method
- transposing elements
ms.assetid: 02ab051b-79b8-4646-b502-381671e78c12
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a34385ccf89557688698b50384b3dfe359478df
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791423"
---
# <a name="reverse-method-javascript"></a>reverse Yöntemi (JavaScript)
Öğeleri ters bir `Array`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
arrayObj.reverse()   
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Tüm `Array` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ters dizisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `arrayObj` başvurusu olan bir `Array` nesnesi.  
  
 `reverse` Yöntemi tersine çevirir öğelerini bir `Array` nesneyi yerinde. Yeni bir oluşturmaz `Array` yürütme sırasında nesne.  
  
 Dizi bitişik, değilse `reverse` yöntemi dizi doldurmak dizideki öğeler oluşturur. Bu öğeleri oluşturulan her değerine sahip `undefined`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `reverse` yöntemi.  
  
```JavaScript  
var arr = new Array(0,1,2,3,4);   
var reverseArr = arr.reverse();  
document.write(reverseArr);  
  
// Output:  
// 4,3,2,1,0  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [concat yöntemi (dizi)](../../javascript/reference/concat-method-array-javascript.md)