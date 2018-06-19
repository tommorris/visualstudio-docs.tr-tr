---
title: getFloat64 yöntemi (DataView) | Microsoft Docs
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
ms.assetid: 347adeb6-b24c-4e7d-8b6b-8e36aacdcae1
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab6d52fcaa82cc957ba47b5ef2acdfbef90152d7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790448"
---
# <a name="getfloat64-method-dataview"></a>getFloat64 Metodu (DataView)
Float64 değer görünümü başından belirtilen bayt uzaklığı alır. Hiçbir hizalama kısıtlama yoktur; çok baytlı değerlerin herhangi uzaklığı getirilmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
var testFloat = dataView.getFloat64(byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>Parametreler  
 `testFloat`  
 Gerekli. Yönteminden döndürülen Float64 değeri.  
  
 `byteOffset`  
 Değeri alınması gereken arabellek yerinde.  
  
 `littleEndian`  
 İsteğe bağlı. Yanlış veya tanımsız big endian değeri okumanız gerekir, aksi takdirde little endian değeri okumanız gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemler bir özel durum olursa görünümü sonunu aşan okuduğunuz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek ilk Float64 DataView içinde alma gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getFloat64(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]