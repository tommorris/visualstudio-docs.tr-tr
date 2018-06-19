---
title: set yöntemi (Float32Array) | Microsoft Docs
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
ms.assetid: 0d486ed3-72eb-4af2-b0a6-ae727c588883
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fdd3d5b350f44aaf5b96a320e0b447587c07ac22
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791348"
---
# <a name="set-method-float32array"></a>set Yöntemi (Float32Array)
Bir değer ya da değerler dizisi ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
float32Array.set(index, value);  
float32Array.set(array, offset);  
  
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
 Giriş dizisi bir TypedArray ise, iki dizi aynı temel ArrayBuffer'ı kullanabilir. Bu durumda, değerler ayarlanırken tüm veriler önce dizilerin hiçbiri ile örtüşmeyen geçici bir arabelleğe kopyalanmış, ardından geçici arabellekteki veriler geçerli diziye kopyalanmış gibi düşünülür.  
  
 Uzaklık ve ona ek olarak belirtilen dizinin uzunluğu geçerli TypedArray için aralık dışında ise bir özel durum oluşturulur.  
  
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
            var floatArr = new Float32Array(buffer.byteLength / 4);  
            floatArr.set(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]