---
title: subarray yöntemi (ınt8array) | Microsoft Docs
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
ms.assetid: 46271ed6-a3c3-41fb-bd6f-81efa9e8dedc
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e32c3a0da7e3173273eb40bf52bb6583bd77df51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791513"
---
# <a name="subarray-method-int8array"></a>subarray Yöntemi (Int8Array)
Başında, dahil, yukarıdan sona ve hariç değerlerine başvurarak bu dizi için ArrayBuffer deposunun yeni bir Int8Array görünümünü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
var newInt8Array = int8Array.subset(begin, end);  
```  
  
## <a name="parameters"></a>Parametreler  
 `newInt8Array`  
 Bu yöntem tarafından döndürülen alt dizi.  
  
 `begin`  
 Dizinin başlangıcının dizini.  
  
 `end`  
 Dizinin sonunun dizini. Bu dahil değildir.  
  
## <a name="remarks"></a>Açıklamalar  
 Eğer başlangıç ya da bitiş negatif ise, dizinin başlangıcı yerine sonundan başlayan bir dizini ifade eder. Eğer bitiş belirtilmemişse, TypedArray'in başlangıcı ile sonu arasındaki tüm öğeleri içerir. Başlangıç ve bitiş değerleri tarafından belirtilen aralık geçerli dizi için geçerli dizin aralığına sıkıştırılır. Eğer yeni TypedArray'in hesaplanan uzunluğu negatif olacaksa, sıfır olarak sıkıştırılır. Döndürülen TypedArray üzerinde bu yöntemin çağırıldığı dizi ile aynı tür olacaktır.  
  
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
            var dataView = new DataView(buffer);  
            var intArr = new Int8Array(buffer.byteLength);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]