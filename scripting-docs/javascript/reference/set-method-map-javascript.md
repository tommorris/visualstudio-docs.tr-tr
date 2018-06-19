---
title: set yöntemi (eşleme) (JavaScript) | Microsoft Docs
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
ms.assetid: 31ee71a0-b09d-442a-9e02-825accf94ffa
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a84a5b2714fde55fba03d581faa851d7245e001
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791339"
---
# <a name="set-method-map-javascript"></a>set Yöntemi (Eşleme) (JavaScript)
Yeni bir öğe için bir harita ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
mapObj.set(key, value)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mapObj`  
 Gerekli. A `Map` nesnesi.  
  
 `key`  
 Gerekli. Yeni öğe için anahtar.  
  
 `value`  
 Gerekli. Eklenecek öğenin değeri.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Döndürür `Map` yeni bir anahtar/değer çifti içeren nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Mevcut bir anahtarı kullanarak koleksiyona bir değer eklerseniz, yeni değer eski değerin yerini alır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, üye eklemek gösterilmiştir bir `Map` ve sonra bunları alır.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
  
m.forEach(function (item) {  
    document.write(item.toString() + "<br />");  
});  
  
// Output:  
// black  
// red  
// 2  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]