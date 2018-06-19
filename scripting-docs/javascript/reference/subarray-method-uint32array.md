---
title: subarray yöntemi (Uint32Array) | Microsoft Docs
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
ms.assetid: 4c183208-12ec-4051-bf0f-a4f7c112cea1
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1c76c5c83bcb1e43b51b4f49618e72311d5df86
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791501"
---
# <a name="subarray-method-uint32array"></a>subarray Yöntemi (Uint32Array)
Yeni Uint32Array görünümünü alır [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md) subarray ilk ve son üyeleri belirtme bu dizi için depolama.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
var newUint32Array = uint32Array.subarray(begin, end);  
```  
  
## <a name="parameters"></a>Parametreler  
 `newUint32Array`  
 Bu yöntem tarafından döndürülen alt dizi.  
  
 `begin`  
 Dizinin başlangıcının dizini.  
  
 `end`  
 Dizinin sonunun dizini. Bu dahil değildir.  
  
## <a name="remarks"></a>Açıklamalar  
 Her iki `begin` veya `end` olan negatif dizinin sonuna bir dizinden tersine baştan ifade eder. Varsa `end` olan belirtilmezse, tüm öğeleri subarray içeren `begin` yazılı dizinin sonuna. Tarafından belirtilen aralık `begin` ve `end` değerleri clamped geçerli dizi için geçerli dizin aralığı. Eğer yeni türü belirlenmiş dizinin hesaplanan uzunluğu negatif olacaksa, sıfır olarak sıkıştırılır. Döndürülen dizi üzerinde bu yöntemin çağırıldığı dizi ile aynı türdür.  
  
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
            var intArr = new Uint32Array(buffer.byteLength / 4);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]