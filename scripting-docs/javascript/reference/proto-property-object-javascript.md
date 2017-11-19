---
title: "__proto__ özelliği (nesne) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __proto__
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 97c3f84d-125e-4905-b921-b021264964ee
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e38669c400acba6f4ed3c4ee3fb5836c31b1bc00
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="proto-property-object-javascript"></a>__proto__ özelliği (nesne) (JavaScript)
Belirtilen nesnenin iç prototip başvuru içeriyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
object.__proto__  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Nesnede prototip ayarlanacak.  
  
## <a name="remarks"></a>Açıklamalar  
 `__proto__` Özelliği, bir nesne için prototip ayarlamak için kullanılabilir.  
  
 Nesne veya işlev tüm yöntemler ve tüm yöntemleri ve özellikleri yeni prototip 's prototip zincirindeki yanı sıra yeni prototip özelliklerini devralır. Bir nesne (devralınan prototipler ve prototip zincirine hariç) yalnızca bir tek prototip, bu nedenle olabilir çağırdığınızda `__proto__` özelliği, önceki prototip değiştirin.  
  
 Prototip yalnızca genişletilebilir bir nesne üzerinde ayarlayabilirsiniz. Daha fazla bilgi için bkz: [Object.preventExtensions işlevi](../../javascript/reference/object-preventextensions-function-javascript.md).  
  
> [!NOTE]
>  `__proto__` Özellik adı başlar ve biter iki alt çizgi ile.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir nesne için prototip ayarlamak gösterilmiştir.  
  
```JavaScript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
if (console && console.log) {  
    console.log(rec.__proto__ === Rectangle.prototype);  // Returns true  
    rec.__proto__ = Object.prototype;  
    console.log(rec.__proto__ === Rectangle.prototype);  // Returns false  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği için prototip ekleyerek özellikleri bir nesne eklemek nasıl gösterir.  
  
```JavaScript  
var proto = { y: 2 };  
  
var obj = { x: 10 };  
obj.__proto__ = proto;  
  
proto.y = 20;  
proto.z = 40;  
  
if (console && console.log) {  
    console.log(obj.x === 10);  // Returns true  
    console.log(obj.y === 20);  // Returns true  
    console.log(obj.z === 40);  // Returns true  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği için özellikleri ekler `String` üzerinde yeni bir prototip ayarlayarak nesnesi.  
  
```JavaScript  
var stringProp = { desc: "description" };  
  
String.__proto__ = stringProp;  
var s1 = "333";  
var s2 = new String("333");  
  
if (console && console.log) {  
  
    console.log(String.desc === "description"); // Returns true  
    console.log(s1.desc === "description");     // Returns false  
    console.log(s2.desc === "description");     // Returns false  
  
    s1.__proto__ = String;  // Can't be set.  
    s2.__proto__ = String;  
  
    console.log(s1.desc === "description"); // Returns false  
    console.log(s2.desc === "description"); // Returns true  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Prototipler ve prototip devralma](../../javascript/advanced/prototypes-and-prototype-inheritance.md)