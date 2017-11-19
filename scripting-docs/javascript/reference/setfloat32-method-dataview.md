---
title: "setFloat32 yöntemi (DataView) | Microsoft Docs"
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
ms.assetid: b3f68048-c817-48d2-bc17-945e3bcc94d7
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a72bf2781bfbae7c7cd301d02ad71ebfbeffa13
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="setfloat32-method-dataview"></a>setFloat32 Yöntemi (DataView)
Float32 değeri görünümü başından belirtilen bayt uzaklığı ayarlar. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerleri herhangi uzaklıkta ayarlanabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
dataView.setFloat32 (byteOffset, value, littleEndian);   
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
 Aşağıdaki örnekte nasıl DataView içinde ilk Float32 ayarlanacağını gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setFloat32(0, 9.1);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]