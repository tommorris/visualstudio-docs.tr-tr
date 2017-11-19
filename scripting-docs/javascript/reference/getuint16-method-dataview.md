---
title: "getUint16 yöntemi (DataView) | Microsoft Docs"
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
ms.assetid: 3c0d9ad8-30b0-42a3-b0fe-aa805398c396
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2da1ea7bdbbbc1d99f9b7b6c33e4b3d83e0ba84f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getuint16-method-dataview"></a>getUint16 Metodu (DataView)
Uint16 değer görünümü başından belirtilen bayt uzaklığı alır. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerlerin herhangi uzaklığı getirilmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
var testInt = dataView.getUint16(byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>Parametreler  
 `testInt`  
 Gerekli. Yönteminden döndürülen Uint16 değeri.  
  
 `byteOffset`  
 Değeri alınması gereken arabellek yerinde.  
  
 `littleEndian`  
 İsteğe bağlı. Yanlış veya tanımsız big endian değeri okumanız gerekir, aksi takdirde little endian değeri okumanız gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemler bir özel durum olursa görünümü sonunu aşan okuduğunuz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek ilk Uint16 DataView içinde alma gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getUint16(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]