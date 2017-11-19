---
title: "getFloat32 yöntemi (DataView) | Microsoft Docs"
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
ms.assetid: adecf671-bde4-46be-a875-33b6d6e970b1
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75fc5be6d8563a44504ae2d1c7ddd9429eccb390
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getfloat32-method-dataview"></a>getFloat32 Metodu (DataView)
Float32 değeri belirtilen bayt uzaklığı görünümü başından alır. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerlerin herhangi uzaklığı getirilmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
var testFloat = dataView.getFloat32(byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>Parametreler  
 `testFloat`  
 Gerekli. Yönteminden döndürülen Float32 değeri.  
  
 `byteOffset`  
 Değeri alınması gereken arabellek yerinde.  
  
 `littleEndian`  
 İsteğe bağlı. Yanlış veya tanımsız big endian değeri okumanız gerekir, aksi takdirde little endian değeri okumanız gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemler bir özel durum olursa görünümü sonunu aşan okuduğunuz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek ilk Float32 DataView içinde alma gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getFloat32(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]