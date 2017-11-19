---
title: "buffer özelliği (ınt32array) | Microsoft Docs"
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
ms.assetid: 9e165880-7f16-4845-a41f-5b0c6e8605c5
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d07448c44bd9f3a79731aebff5370f2ef7e7ad6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="buffer-property-int32array"></a>buffer Özelliği (Int32Array)
Salt okunur. Bu dizi tarafından başvurulan ArrayBuffer nesnesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
var arrayBuffer = int32Array.buffer;  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek dizinin ArrayBuffer alma gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int32Array(buffer.byteLength / 4);  
            alert(intArr.buffer.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]