---
title: instanceof işleci (JavaScript) | Microsoft Docs
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
- instanceof_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- instanceOf operator
ms.assetid: 92467bdc-56b5-42dc-adbd-a219776454d2
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2124fe815c89c3c157be3ea729fa7edb9d96b39
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
ms.locfileid: "27799594"
---
# <a name="instanceof-operator-javascript"></a>instanceof İşleci (JavaScript)
Bir nesne belirli bir sınıfın örneği olup olmadığını gösteren bir Boole değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = object instanceof class  
```  
  
## <a name="parameters"></a>Parametreler  
 `result`  
 Gerekli. Herhangi bir değişken.  
  
 `object`  
 Gerekli. Herhangi bir nesne ifade.  
  
 `class`  
 Gerekli. Herhangi bir tanımlı nesne sınıfı.  
  
## <a name="remarks"></a>Açıklamalar  
 `instanceof` Operatörü döndürür `true` varsa `object` örneği `class`. Döndürdüğü `true` varsa `class` nesnenin prototip zincirinde mevcut. Döndürdüğü `false` varsa `object` bir örneği değil `class`, veya `object` olan `null`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `instanceof` işleci.  
  
```JavaScript  
function objTest(obj){  
    var i, t, s = "";  
    t = new Array();  
    t["Date"] = Date;  
    t["Object"] = Object;  
    t["Array"] = Array;  
        for (i in t){  
            if (obj instanceof t[i]) {   
                s += "obj is an instance of " + i + "<br/>";  
            }  
            else {  
                s += "obj is not an instance of " + i + "<br/>";  
        }  
    }  
    return(s);  
}  
  
var obj = new Date();  
document.write(objTest(obj));  
  
// Output:   
// obj is an instance of Date  
// obj is an instance of Object  
// obj is not an instance of Array  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç Özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)