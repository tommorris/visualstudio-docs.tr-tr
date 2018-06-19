---
title: Numaralandırıcı nesnesi (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- Enumerator
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Enumerator object
ms.assetid: 63f03c21-d58c-47db-a728-4d8d88b0a422
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50b1ebfb6e24ed734f008b3c05f10a1687c4aff5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790490"
---
# <a name="enumerator-object-javascript"></a>Numaralandırıcı Nesnesi (JavaScript)
Bir koleksiyondaki öğelerin numaralandırmasını etkinleştirir.  
  
> [!WARNING]
>  Bu nesne Internet Explorer'da yalnızca içinde değil desteklenmiyor [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
enumObj = new Enumerator([collection])   
```  
  
## <a name="parameters"></a>Parametreler  
 `enumObj`  
 Gerekli. Değişken adına `Enumerator` nesne atanır.  
  
 `collection`  
 İsteğe bağlı. Tüm koleksiyon nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir koleksiyonun üyelerini doğrudan erişilemeyen, koleksiyonları diziler farklı. Dizilerle gibi dizinleri kullanmak yerine, geçerli öğe işaretçisi yalnızca ilk veya bir sonraki öğeye bir koleksiyonun taşıyabilirsiniz.  
  
 `Enumerator` Nesne herhangi bir koleksiyonun üyesi erişmek için bir yol sağlar ve benzer şekilde davranır `For...Each` VBScript deyiminde.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod kullanımını gösterir `Enumerator` nesnesi:  
  
```JavaScript  
var bytesPerGB = 1024 * 1024 * 1024;  
  
var fso = new ActiveXObject("Scripting.FileSystemObject");  
  
document.write(fso.Drives);  
var e = new Enumerator(fso.Drives);  
  
var driveString = "";  
  
e.moveFirst();  
while (e.atEnd() == false)  
{  
    var drv = e.item();  
  
    driveString += drv.Path + " - ";  
  
    if (drv.IsReady){  
        var freeGB = drv.FreeSpace / bytesPerGB;  
        var totalGB = drv.TotalSize / bytesPerGB;  
  
        driveString += freeGB.toFixed(3) + " GB free of ";  
        driveString += totalGB.toFixed(3) + " GB";  
    }  
    else{  
        driveString += "Not Ready";  
    }  
  
    driveString += "<br />";;  
  
    e.moveNext();  
}  
document.write(driveString);  
  
// Output: <drive information  
  
```  
  
## <a name="properties"></a>Özellikler  
 `Enumerator` Nesnenin özellik vardır.  
  
## <a name="methods"></a>Yöntemler  
 [atEnd yöntemi](../../javascript/reference/atend-method-enumerator-javascript.md) &#124; [item yöntemi](../../javascript/reference/item-method-enumerator-javascript.md) &#124; [moveFirst yöntemi](../../javascript/reference/movefirst-method-enumerator-javascript.md) &#124; [moveNext yöntemi](../../javascript/reference/movenext-method-enumerator-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları ve Internet Explorer 10 standartları. İçinde desteklenmez [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Boole nesnesi](../../javascript/reference/boolean-object-javascript.md)