---
title: toJSON yöntemi (tarih) (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- toJSON method
ms.assetid: f91df030-e9c9-425e-8e6d-b46bdda66cb6
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a131c7b248ca0486ab0b3b02d40e4351136c37c9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791900"
---
# <a name="tojson-method-date-javascript"></a>toJSON Yöntemi (Tarih) (JavaScript)
Tarafından kullanılan [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md) verilerinin dönüştürülmesi, nesnenin JavaScript nesne gösterimi (JSON) Serileştirmenin etkinleştirmek için yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
objectname.toJSON()  
```  
  
## <a name="parameters"></a>Parametreler  
 `objectname`  
 Gerekli. Hangi JSON için seri hale getirme isteyen bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 `toJSON` Yöntemi tarafından kullanılan `JSON.stringify` işlevi. `JSON.stringify`serileştiren bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] JSON metin değeri. Varsa bir `toJSON` yöntemi sağlanan `JSON.stringify`, `toJSON` yöntemi çağrılır `JSON.stringify` olarak adlandırılır.  
  
 `toJSON` Yöntemi yerleşik üyesi olduğu [tarih](../../javascript/reference/date-object-javascript.md) [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesnesi. UTC saat dilimi (Z soneki tarafından gösterilen) için bir tarih ISO biçimli dize döndürür.  
  
 Geçersiz kılabilirsiniz `toJSON` yöntemi `Date` yazın ya da tanımlayan bir `toJSON` JSON seri hale getirme önce belirli nesne türü için veri dönüştürme elde etmek diğer nesne türleri için yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `toJSON` dize üye değerleri büyük serileştirmek için yöntem. `toJSON` Yöntemi çağrılır `JSON.stringify` olarak adlandırılır.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
contact.toJSON = function(key)  
 {  
    var replacement = new Object();  
    for (var val in this)  
    {  
        if (typeof (this[val]) === 'string')  
            replacement[val] = this[val].toUpperCase();  
        else  
            replacement[val] = this[val]  
    }  
    return replacement;  
};  
  
var jsonText = JSON.stringify(contact);  
  
/* The value of jsonText is:  
'{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}'  
*/  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını anlatan `toJSON` yerleşik üyesi yöntemi [tarih](../../javascript/reference/date-object-javascript.md) nesnesi.  
  
```JavaScript  
var dt = new Date('8/24/2009');  
dt.setUTCHours(7, 30, 0);  
var jsonText = JSON.stringify(dt);  
  
/* The value of jsonText is:  
'"2009-08-24T07:30:00Z"'  
*/  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]**İçin geçerlidir:** [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JSON nesnesi](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse işlevi](../../javascript/reference/json-parse-function-javascript.md)   
 [JSON.stringify işlevi](../../javascript/reference/json-stringify-function-javascript.md)   
 [JavaScript yöntemleri](../../javascript/reference/javascript-methods.md)