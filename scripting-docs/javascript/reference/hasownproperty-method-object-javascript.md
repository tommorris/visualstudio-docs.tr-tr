---
title: "hasOwnProperty yöntemi (nesne) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: hasOwnProperty
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: hasOwnProperty method
ms.assetid: 3eb69d69-486f-4792-9518-4452aef369ca
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 397b68fc87bf730886c928e099037ff0183a7f63
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="hasownproperty-method-object-javascript"></a>hasOwnProperty Yöntemi (Nesne) (JavaScript)
Bir nesneyi belirtilen ada sahip bir özellik olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
object.hasOwnProperty(proName)  
```  
  
## <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Bir nesne örneği.  
  
 `proName`  
 Gerekli. Dize değeri, bir özellik adı.  
  
## <a name="remarks"></a>Açıklamalar  
 `hasOwnProperty` Yöntemi döndürür `true` varsa `object` belirtilen adla özelliğine `false` mevcut değilse. Bu yöntem nesnenin prototip zinciri özelliklerinde denetlemez; özellik nesnesinin bir üyesi olması gerekir.  
  
 Bu özellik, Internet Explorer 8 ve aşağıda ana nesneler üzerinde desteklenmiyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, tüm `String` nesneleri ortak bir yöntemi bölme paylaşır. Aşağıdaki kodu görüntüler **false** ve **doğru**.  
  
```JavaScript  
var s = new String("Sample");  
document.write(s.hasOwnProperty("split"));  
document.write("<br/>");  
document.write(String.prototype.hasOwnProperty("split"));  
  
// Output:  
// false  
// true  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [in işleci](../../javascript/reference/in-operator-decrementjavascript.md)