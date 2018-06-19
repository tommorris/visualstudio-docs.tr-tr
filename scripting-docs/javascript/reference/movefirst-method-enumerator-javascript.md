---
title: moveFirst yöntemi (Numaralandırıcı) (JavaScript) | Microsoft Docs
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
- moveFirst
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- MoveFirst method
ms.assetid: 96eedc66-7974-443c-b0cd-55373a7c0e59
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: af8c59194a5655730e8509b43533f699aeef51d2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791186"
---
# <a name="movefirst-method-enumerator-javascript"></a>moveFirst Yöntemi (Numaralandırıcı) (JavaScript)
Koleksiyondaki geçerli öğenin ilk öğeye sıfırlar.  
  
> [!WARNING]
>  Bu nesne yalnızca Internet Explorer'da desteklenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
enumObj.moveFirst( )   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli *enumObj* başvurudur herhangi `Enumerator` nesnesi.  
  
 Koleksiyondaki öğe varsa, geçerli öğenin tanımsız ayarlanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `moveFirst` yöntemi üyeleri değerlendirmek için kullanılan `Drives` listenin başından koleksiyonu:  
  
```JavaScript  
function ShowDrives()  
{  
    var s = "";  
    var bytesPerGB = 1024 * 1024 * 1024;  
  
    var fso = new ActiveXObject("Scripting.FileSystemObject");  
    var e = new Enumerator(fso.Drives);  
  
    e.moveFirst();  
    while (e.atEnd() == false)  
    {  
        var drv = e.item();  
  
        s += drv.Path + " - ";  
  
        if (drv.IsReady)  
        {  
            var freeGB = drv.FreeSpace / bytesPerGB;  
            var totalGB = drv.TotalSize / bytesPerGB;  
  
            s += freeGB.toFixed(3) + " GB free of ";  
            s += totalGB.toFixed(3) + " GB";  
        }  
        else  
        {  
            s += "Not Ready";  
        }  
  
        s += "<br />";  
  
        e.moveNext();  
    }  
    return(s);  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları ve Internet Explorer 10 standartları. İçinde desteklenmez [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
 **Uygulandığı öğe**: [Numaralandırıcı nesnesi](../../javascript/reference/enumerator-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [atEnd yöntemi (Numaralandırıcı)](../../javascript/reference/atend-method-enumerator-javascript.md)   
 [item yöntemi (Numaralandırıcı)](../../javascript/reference/item-method-enumerator-javascript.md)   
 [moveNext yöntemi (Numaralandırıcı)](../../javascript/reference/movenext-method-enumerator-javascript.md)