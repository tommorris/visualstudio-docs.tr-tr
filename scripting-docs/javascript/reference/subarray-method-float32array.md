---
title: subarray yöntemi (Float32Array) | Microsoft Docs
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
ms.assetid: 97aa27c0-d650-411e-b929-dd9c4a2ae9a5
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78d8c729298fe80d841d7c4750e4e6817120c9d3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791471"
---
# <a name="subarray-method-float32array"></a>subarray Yöntemi (Float32Array)
Yeni Float32Array görünümünü alır [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md) subarray ilk ve son üyeleri belirtme bu dizi için depolama.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
var newFloat32Array = float32Array.subarray(begin, end);  
```  
  
## <a name="parameters"></a>Parametreler  
 `newFloat32Array`  
 Bu yöntem tarafından döndürülen alt dizi.  
  
 `begin`  
 Dizinin başlangıcının dizini.  
  
 `end`  
 Dizinin sonunun dizini.  
  
## <a name="remarks"></a>Açıklamalar  
 Her iki `begin` veya `end` olan negatif dizinin sonuna bir dizinden tersine baştan ifade eder. Varsa `end` olan belirtilmezse, tüm öğeleri subarray içeren `begin` yazılı dizinin sonuna. Tarafından belirtilen aralık `begin` ve `end` değerleri clamped geçerli dizi için geçerli dizin aralığı. Eğer yeni türü belirlenmiş dizinin hesaplanan uzunluğu negatif olacaksa, sıfır olarak sıkıştırılır. Döndürülen dizi üzerinde bu yöntemin çağırıldığı dizi ile aynı türdür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, üç öğelerini uzun dizisinin ilk öğesi ile başlayan bir subarray alma gösterilmektedir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var floatArr = new Float32Array(buffer.byteLength / 4);  
            var subArr = floatArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]