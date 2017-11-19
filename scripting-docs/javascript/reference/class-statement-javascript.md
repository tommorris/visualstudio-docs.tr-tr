---
title: class ifadesi (JavaScript) | Microsoft Docs
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
ms.assetid: bf45ebad-4678-4062-88df-55d32b603c69
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e828ae86c3f8f585179e3b097d98b3449c3f3b45
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="class-statement-javascript"></a>class İfadesi (JavaScript)
Yeni bir sınıf bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class classname () [extends object] {    [constructor([arg1 [,... [,argN]]]) {        statements    }]    [[static] method([arg1 [,... [,argN]]]) {        statements    }]}  
```  
  
#### <a name="parameters"></a>Parametreler  
 `classname`  
 Gerekli. Sınıfın adı.  
  
 `object`  
 İsteğe bağlı. Bir nesne veya yeni sınıf özellikleri ve yöntemleri devraldığı sınıfı.  
  
 `constructor`  
 İsteğe bağlı. Yeni sınıf örneği başlatır Oluşturucusu işlevi.  
  
 `arg1...argN`  
 İsteğe bağlı. Bağımsız değişkenler isteğe bağlı, virgülle ayrılmış bir listesini işlevi bilir.  
  
 `statements`  
 İsteğe bağlı. Bir veya daha fazla [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] deyimleri.  
  
 `static`  
 İsteğe bağlı. Bir statik yöntem belirtir.  
  
 `method`  
 İsteğe bağlı. Bir veya daha fazla [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] örneği veya üzerinde bir sınıf örneği çağrılabilir statik yöntemler.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sınıf, prototip tabanlı devralma, Oluşturucular, örnek yöntemleri ve statik yöntemler kullanarak yeni nesneler oluşturmanıza olanak sağlar. Kullanabileceğiniz `super` nesnesi bir sınıf oluşturucu veya aynı oluşturucuyu çağırmak için sınıf veya yöntemini üst sınıf veya nesne içinde. İsteğe bağlı olarak kullanmak `extends` sonraki deyime sınıfı veya yeni sınıfının devraldığı yöntemleri nesneyi belirlemek için sınıf adı.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
class Spelunking extends EXPERIENCE.Outdoor {  
  constructor(name, location) {  
    super(name, location);  
  
    this.minSkill = Spelunking.defaultSkill();  
    //...  
  }  
  update(minSkill) {  
    //...  
    super.update(minSkill);  
  }  
  static defaultSkill() {  
    return new EXPERIENCE.Level3();  
  }  
}  
```  
  
## <a name="example"></a>Örnek  
 Hesaplanmış özellik adları sınıflar için de oluşturabilirsiniz. Aşağıdaki kod örneği kullanarak bir hesaplanmış özellik adı oluşturur `set` sözdizimi.  
  
```JavaScript  
var propName = "prop_42";  
  
class Spelunking {  
    set [propName](v) {  
        this.value = v;  
    }  
};  
  
var s = new Spelunking();  
console.log(s.value);  
s.prop_42 = 42;  
console.log(s.value);  
  
// Output:  
// undefined  
// 42  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği kullanarak dinamik olarak bir sınıf için bir özellik adı oluşturur `get` sözdizimi.  
  
```JavaScript  
var propName = "prop_42";  
  
class Spelunking {  
    get [propName]() {  
        return 777;  
    }  
}  
  
var s = new Spelunking();  
console.log(s.prop_42);  
  
// Output:  
// 777  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12exp](../../javascript/reference/includes/jsv12exp-md.md)]