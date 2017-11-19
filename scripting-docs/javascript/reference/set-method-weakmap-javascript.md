---
title: "set yöntemi (WeakMap) (JavaScript) | Microsoft Docs"
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
ms.assetid: 29fc72b1-224f-4f19-8c06-5d926d695b03
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c916bda13c7bd973b37c4e4cb6b81e327ee5de54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-weakmap-javascript"></a>set Yöntemi (WeakMap) (JavaScript)
Yeni bir öğe ekler bir `WeakMap` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
weakmapObj.set(key, value)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `weakmapObj`  
 Gerekli. A `WeakMap` nesnesi.  
  
 `key`  
 Gerekli. Eklenecek öğenin anahtarı temsil eden bir nesne. Bu nesne başvurusu olmalıdır.  
  
 `value`  
 Gerekli. Eklenecek öğenin değeri.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Döndürür `WeakMap` yeni bir anahtar/değer çifti içeren nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Mevcut bir anahtarı kullanarak koleksiyona bir değer eklerseniz, yeni değer eski değerin yerini alır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, üye eklemek gösterilmiştir bir `WeakMap` nesnesi.  
  
```JavaScript  
var dog = {  
    breed: "yorkie"  
}  
  
var cat = {  
    breed: "burmese"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.set(cat, "pepper");  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]