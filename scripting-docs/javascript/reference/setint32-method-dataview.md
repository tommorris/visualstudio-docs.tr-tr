---
title: "Setınt32 yöntemi (DataView) | Microsoft Docs"
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
ms.assetid: 07e5f068-0e3f-4c23-84b3-c72658d7f194
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 00f3f6b03cdd3a8d5d7b95184f1c0ff5c356592a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="setint32-method-dataview"></a>setInt32 Yöntemi (DataView)
Int32 değeri görünümü başından belirtilen bayt uzaklığı ayarlar. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerleri herhangi uzaklıkta ayarlanabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
dataView.setInt32 (byteOffset, value, littleEndian);   
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
 Aşağıdaki örnekte nasıl DataView içinde ilk Int32 ayarlanacağını gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setInt32(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]