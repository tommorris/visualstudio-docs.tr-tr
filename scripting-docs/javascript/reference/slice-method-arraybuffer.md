---
title: slice yöntemi (ArrayBuffer) | Microsoft Docs
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
ms.assetid: 2dcc51ff-f444-4d51-80ba-3bcd845ba0ae
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25fc10a02b4a3422a6720ad91c8bba29906da0e5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791657"
---
# <a name="slice-method-arraybuffer"></a>slice Yöntemi (ArrayBuffer)
Bir bölümünü döndürür bir [ArrayBuffer](../../javascript/reference/arraybuffer-object.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
arrayBufferObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayBufferObj`  
 Gerekli. [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) bölüm kopyalanacak nesne.  
  
 `start`  
 Gerekli. Kopyalanacak bölüm başına bayt dizini.  
  
 `end`  
 İsteğe bağlı. Kopyalanacak bölümün sonuna bayt dizini.  
  
## <a name="remarks"></a>Açıklamalar  
 `slice` Yöntemi döndürür bir [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) belirtilen bölümünü içeren nesne `arrayBufferObj`.  
  
 `slice` Yöntemi kopyalar kadar ancak dahil değil tarafından belirtilen bayt `end`. Varsa `start` veya `end` olan negatif belirtilen dizin olarak işlem görür `length`  +  `start` veya `end`, sırasıyla nerede `length` uzunluğu [ArrayBuffer](../../javascript/reference/arraybuffer-object.md). Varsa `end` girilmezse, ayıklama sonuna kadar devam `arrayBufferObj`. Varsa `end` önce oluşur `start`, hiçbir bayt yeni kopyalanır [ArrayBuffer](../../javascript/reference/arraybuffer-object.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler nasıl kullanılacağını `slice` yöntemi.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer1 = req.response;  
            var buffer2 = buffer1.slice(40, 48);  
            var dataview = new DataView(buffer2);  
            var ints = new Int32Array(buffer2.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[1]);  
        }  
    }  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md)