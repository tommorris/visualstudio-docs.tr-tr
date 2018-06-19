---
title: Setınt16 yöntemi (DataView) | Microsoft Docs
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
ms.assetid: 901c6cf5-63fb-45bd-9ea8-185c1d892060
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04ea20079c217d1aeef8456e9c81996661fed356
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791330"
---
# <a name="setint16-method-dataview"></a>setInt16 Yöntemi (DataView)
Int16 değeri görünümü başından belirtilen bayt uzaklığı ayarlar. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerleri herhangi uzaklıkta ayarlanabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
dataView.setInt16(byteOffset, value, littleEndian);   
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
 Aşağıdaki örnekte nasıl DataView içinde ilk Int16 ayarlanacağını gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setInt16(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]