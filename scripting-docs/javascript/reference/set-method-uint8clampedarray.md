---
title: "set yöntemi (Uint8ClampedArray) | Microsoft Docs"
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
ms.assetid: 1298443d-5c4c-4329-9ad2-35e213dca157
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ed7635559e615746c577560f1a9266b26acd959d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-uint8clampedarray"></a>set yöntemi (Uint8ClampedArray)
Bir değer ya da değerler dizisi ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
uint8ClampedArray.set(index, value);  
uint8ClampedArray.set(array, offset);  
  
```  
  
## <a name="parameters"></a>Parametreler  
 `index`  
 Ayarlanacak konumun dizini.  
  
 `value`  
 Ayarlanacak değer.  
  
 `array`  
 Ayarlanacak, yazılmış veya yazılmamış değerler dizisi.  
  
 `offset`  
 Geçerli dizide, değerlerin yazılacağı dizin.  
  
## <a name="remarks"></a>Açıklamalar  
 Giriş dizisi belirtilmiş bir diziyse, iki dizisi aynı temel kullanabilir [ArrayBuffer](../../javascript/reference/arraybuffer-object.md). Bu durumda, tüm verileri ilk dizi ya da örtüşmediğinden geçici bir arabelleğe kopyalanmış sanki değerleri ayarlama gerçekleşir ve geçici arabellek verilerden geçerli diziye sonra kopyalanır.  
  
 Uzaklık artı geçerli yazılan dizi için aralığın dışında verilen dizi uzunluğu ise, bir özel durum oluşturulur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, dizinin ilk öğesinin nasıl ayarlanacağı gösterilmiştir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint8ClampedArray(buffer.byteLength);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md)   
 [Uint8ClampedArray nesnesi](../../javascript/reference/uint8clampedarray-object-javascript.md)