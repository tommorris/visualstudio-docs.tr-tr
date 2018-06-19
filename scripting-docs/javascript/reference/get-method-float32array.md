---
title: get yöntemi (Float32Array) | Microsoft Docs
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
ms.assetid: f859481c-0bb8-43d3-9d54-38d303e44397
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea17b3d26a1f192843a2fb9d2d87f62fe26fceff
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790472"
---
# <a name="get-method-float32array"></a>get Metodu (Float32Array)
Atlanabilir. Belirtilen dizindeki öğeyi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
var value = float32Array.get(index);  
```  
  
## <a name="parameters"></a>Parametreler  
 `value`  
 Bu yöntem tarafından döndürülen değer.  
  
 `index`  
 Dizinin öğesinin alınacağı dizin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, dizinin ilk öğesinin nasıl alınacağı gösterilmiştir.  
  
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
            var element = floatArr.getFloat32(0);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]