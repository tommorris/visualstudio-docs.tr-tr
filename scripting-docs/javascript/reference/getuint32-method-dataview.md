---
title: "getUint32 yöntemi (DataView) | Microsoft Docs"
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
ms.assetid: 266ee6b6-c0b6-417e-a64b-c8cda48fde86
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fc598239d65f371df78ade0c214b9961b022911
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getuint32-method-dataview"></a>getUint32 Metodu (DataView)
Uint32 değer görünümü başından belirtilen bayt uzaklığı alır. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerlerin herhangi uzaklığı getirilmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
var testInt = dataView.get Uint32 (byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>Parametreler  
 `testInt`  
 Gerekli. Yönteminden döndürülen Uint32 değeri.  
  
 `byteOffset`  
 Değeri alınması gereken arabellek yerinde.  
  
 `littleEndian`  
 İsteğe bağlı. Yanlış veya tanımsız big endian değeri okumanız gerekir, aksi takdirde little endian değeri okumanız gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemler bir özel durum olursa görünümü sonunu aşan okuduğunuz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek ilk Uint32 DataView içinde alma gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getUint32(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]