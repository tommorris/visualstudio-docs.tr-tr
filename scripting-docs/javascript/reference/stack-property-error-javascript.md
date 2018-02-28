---
title: "stack özelliği (hata) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Error.stack
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript error stack
- error stack [JavaScript]
ms.assetid: 1dc21fdd-853c-4664-bf1c-24eb1f6f2daf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14e4a2537b1543b7e8d9727afdeb8ea5dee61bbc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="stack-property-error-javascript"></a>stack Özelliği (Hata) (JavaScript)
Alır veya hata yığını yığın izleme çerçeveleri içeren bir dize ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
object  
.stack   
```  
  
## <a name="remarks"></a>Açıklamalar  
 `stack` Özelliği ayarlanmış `undefined` olduğunda hata oluşturulur ve hata oluştuğunda izleme bilgilerini alır. Birden çok kez, bir hata oluşursa `stack` özelliği, hata oluşturulur her zaman güncelleştirilir.  
  
 Yığın çerçeveleri şu biçimde görüntülenir: **FunctionName adresindeki (\<tam adı/URL >:\<satır numarası >:\<sütun numarası >)**  
  
 Kendi hata nesnesi oluşturun ve yığın izleme bir değere ayarlayın hata oluştuğunda değerin üzerine olmaz.  
  
 `stack` Özelliği, çerçevelere satır içi işlevler göstermiyor. Yalnızca fiziksel yığını gösterir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir hata yakalama yığını edilirken gösterilmektedir.  
  
```JavaScript  
try  
    {  
        var x = y.name;  
    }  
catch(e)  
    {  
        document.write ("Error stack: ")  
        document.write (e.stack);  
    }  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ayarlama ve yığın alma gösterilmektedir.  
  
```JavaScript  
try  
    {  
        var err = Error("my error");  
        err.stack = "my stack trace";  
        throw err;  
    }  
catch(e)  
    {  
        document.write ("Error stack: ")  
        document.write (e.stack);  
    }  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]  
  
 **Uygulandığı öğe**: [hata nesnesi](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Description özelliği (hata)](../../javascript/reference/description-property-error-javascript.md)   
 [message özelliği (hata)](../../javascript/reference/message-property-error-javascript.md)   
 [name özelliği (hata)](../../javascript/reference/name-property-error-javascript.md)   
 [stackTraceLimit özelliği (hata)](../../javascript/reference/stacktracelimit-property-error-javascript.md)