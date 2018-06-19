---
title: setFloat64 yöntemi (DataView) | Microsoft Docs
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
ms.assetid: 63d2c631-876f-4d4b-b3b6-62b0aaffe6c5
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e22552e4190c74b520dfce853be6e9d1364764e3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791498"
---
# <a name="setfloat64-method-dataview"></a>setFloat64 Yöntemi (DataView)
Float64 değeri görünümü başından belirtilen bayt uzaklığı ayarlar. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerleri herhangi uzaklıkta ayarlanabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
dataView.setFloat64 (byteOffset, value, littleEndian);   
```  
  
## <a name="parameters"></a>Parametreler  
 `byteOffset`  
 Değeri alınması gereken arabellek yerinde.  
  
 `value`  
 Ayarlanacak değer.  
  
 `littleEndian`  
 İsteğe bağlı. Yanlış veya tanımsız big endian değer yazılması gerekir, aksi takdirde little endian değer yazılması gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemler bir özel durum olursa görünümü sonunu aşan yazarsınız.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl DataView içinde ilk Float64 ayarlanacağını gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setFloat64(0, 9.1);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]