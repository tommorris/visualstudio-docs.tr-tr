---
title: setUint8 yöntemi (DataView) | Microsoft Docs
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
ms.assetid: b294262b-3f4b-4183-a292-5a6982cbdd27
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4ab533520d933b11657175d396433d732536c7a3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791360"
---
# <a name="setuint8-method-dataview"></a>setUint8 Yöntemi (DataView)
Görünüm başlangıç belirtilen bayt uzaklığı Uint8 değerinde depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
dataView.setUint8(byteOffset, value);   
```  
  
## <a name="parameters"></a>Parametreler  
 `byteOffset`  
 Değer ayarlanmalıdır arabellek yerinde.  
  
 `value`  
 Ayarlanacak değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemler bir özel durum olursa görünümü sonunu aşan yazarsınız.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl DataView içinde ilk Uint8 ayarlanacağını gösterir.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setUint8(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]