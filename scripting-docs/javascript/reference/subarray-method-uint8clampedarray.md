---
title: subarray yöntemi (Uint8ClampedArray) | Microsoft Docs
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
ms.assetid: 309ed9e8-5805-47ab-b3ed-501cae1323dd
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76cda8b123b02b4c19a7fd162f3bfbce4540d149
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791675"
---
# <a name="subarray-method-uint8clampedarray"></a>subarray Yöntemi (Uint8ClampedArray)
Yeni bir alır [Uint8ClampedArray](../../javascript/reference/uint8array-object.md) görünümünü [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) subarray ilk ve son üyeleri belirtme bu dizi için depolama.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
var newUint8ClampedArray = uint8ClampedArray.subarray(begin, end);  
```  
  
## <a name="parameters"></a>Parametreler  
 `newUint8ClampedArray`  
 Gerekli. Bu yöntem tarafından döndürülen alt dizi.  
  
 `begin`  
 İsteğe bağlı. Dizinin başlangıcının dizini.  
  
 `end`  
 İsteğe bağlı. Dizinin sonunun dizini. Bu dahil değildir.  
  
## <a name="remarks"></a>Açıklamalar  
 Her iki `begin` veya `end` olan negatif dizinin sonuna bir dizinden tersine baştan ifade eder. Varsa `end` olan belirtilmezse, tüm öğeleri subarray içeren `begin` yazılı dizinin sonuna. Tarafından belirtilen aralık `begin` ve `end` değerleri clamped geçerli dizi için geçerli dizin aralığı. Eğer yeni türü belirlenmiş dizinin hesaplanan uzunluğu negatif olacaksa, sıfır olarak sıkıştırılır. Verilen dizi üzerinde bu yöntem çağrılır dizi olarak aynı türe sahip.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek dizinin ilk öğesinden başlayarak iki öğe uzunluğunda bir alt dizinin nasıl alındığını gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var intArr = new Uint8ClampedArray(buffer.byteLength);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uint8Array nesnesi](../../javascript/reference/uint8array-object.md)   
 [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md)   
 [Uint8ClampedArray nesnesi](../../javascript/reference/uint8clampedarray-object-javascript.md)