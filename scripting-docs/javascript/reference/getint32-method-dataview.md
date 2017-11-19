---
title: "Getınt32 yöntemi (DataView) | Microsoft Docs"
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
ms.assetid: 7a985681-ddb1-4c2b-815c-514c17392e82
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bae788801a81265d39be5ef090e5820122cbb09b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getint32-method-dataview"></a>getInt32 Metodu (DataView)
Int32 değeri belirtilen bayt uzaklığı görünümü başından alır. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerlerin herhangi uzaklığı getirilmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
var testInt = dataView.getInt32(byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>Parametreler  
 `testInt`  
 Gerekli. Yönteminden döndürülen Int32 değeri.  
  
 `byteOffset`  
 Değeri alınması gereken arabellek yerinde.  
  
 `littleEndian`  
 İsteğe bağlı. Yanlış veya tanımsız big endian değeri okumanız gerekir, aksi takdirde little endian değeri okumanız gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemler bir özel durum olursa görünümü sonunu aşan okuduğunuz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek ilk Int32 DataView içinde alma gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getInt32(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]