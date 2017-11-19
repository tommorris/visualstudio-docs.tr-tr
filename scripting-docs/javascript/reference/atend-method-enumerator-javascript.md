---
title: "atEnd yöntemi (Numaralandırıcı) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: atEnd
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: atEnd method
ms.assetid: 326808fb-9a0f-428e-aff1-b11b237913f1
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b5097d00c11ffafc314264f134aedda3981c8e2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="atend-method-enumerator-javascript"></a>atEnd Yöntemi (Numaralandırıcı) (JavaScript)
Numaralayıcı topluluğun sonunda olup olmadığını gösteren bir Boole değeri döndürür.  
  
> [!WARNING]
>  Bu nesne yalnızca Internet Explorer'da desteklenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
myEnum.atEnd()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli *myEnum* başvurudur herhangi `Enumerator` nesnesi.  
  
 `atEnd` Yöntemi döndürür **doğru** bir koleksiyondaki geçerli öğedir koleksiyonu boş olan veya geçerli öğeye tanımlanmadı. Aksi takdirde, döndürür **false**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodda `atEnd` yöntemi sürücülerin listesini sonuna ulaşıldı, belirlemek için kullanılır:  
  
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
 [item yöntemi (Numaralandırıcı)](../../javascript/reference/item-method-enumerator-javascript.md)   
 [moveFirst yöntemi (Numaralandırıcı)](../../javascript/reference/movefirst-method-enumerator-javascript.md)   
 [moveNext yöntemi (Numaralandırıcı)](../../javascript/reference/movenext-method-enumerator-javascript.md)   
 [Numaralandırıcı nesnesi](../../javascript/reference/enumerator-object-javascript.md)