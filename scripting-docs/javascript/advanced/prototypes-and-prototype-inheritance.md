---
title: Prototipler ve prototip devralma | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- prototype [JavaScript]
- prototype inheritance [JavaScript]
ms.assetid: 1e1d0631-2a9f-4011-b9fe-fa338e1ef34c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 200ca757e72b2eec8f09fd48a841cc8eb816c85d
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="prototypes-and-prototype-inheritance"></a>Prototipler ve Prototip Devralma
JavaScript içinde bir `prototype` işlevleri ve yapıcı işlevleri tarafından oluşturulan nesneleri özelliğidir. Bir işlevin prototipi bir nesnedir. Temelde bir işlev kullanıldığında bir oluşturucu olarak kullanılır.  
  
```JavaScript  
function Vehicle(wheels, engine) {  
    this.wheels = wheels;  
    this.engine = engine;  
}  
```  
  
 Prototipi yukarıdaki örnekte `Vehicle` işlevidir ile örneği herhangi bir nesnenin prototip `Vehicle` Oluşturucusu.  
  
## <a name="using-prototypes-to-add-properties-and-methods"></a>Özellik ve Yöntem Eklemek için Prototipler Kullanma  
 Kullanabileceğiniz `prototype` özellikleri ve yöntemleri nesneleri eklemek için önceden oluşturulmuş olanlar bile özelliği:  
  
```JavaScript  
var testVehicle = new Vehicle(2, false);  
Vehicle.prototype.color = "red";  
var testColor = testVehicle.color;  
```  
  
 Değeri `testColor` "kırmızı".  
  
 Hatta önceden tanımlanmış nesnelere özellikler ve yöntemler ekleyebilirsiniz. Örneğin, tanımlayabilirsiniz bir `Trim` yöntemi `String` prototip nesnesi ve komut dosyanızı tüm dizelerde yöntemi devralır.  
  
```JavaScript  
String.prototype.trim = function()  
{  
    // Replace leading and trailing spaces with the empty string  
    return this.replace(/(^\s*)|(\s*$)/g, "");  
}  
var s = "    leading and trailing spaces    ";  
// Displays "    leading and trailing spaces     (35)"  
window.alert(s + " (" + s.length + ")");  
// Remove the leading and trailing spaces  
s = s.trim();  
// Displays "leading and trailing spaces (27)"  
window.alert(s + " (" + s.length + ")");  
```  
  
### <a name="using-prototypes-to-derive-one-object-from-another-with-objectcreate"></a>Object.create İle Bir Nesneyi Başka Bir Nesneden Türetmek İçin Prototipler Kullanma  

Prototip `Object` bir nesne başka bir türetilen için kullanılabilir. Örneğin, kullanabileceğiniz [Object.create](../../javascript/reference/object-create-function-javascript.md) yeni bir nesne çıkarmaya işlevi `Bicycle` prototipi kullanarak `Vehicle` (gereksinim önceki tüm yeni özellikleri) tanımladığımız nesne.  
  
```JavaScript  
var bicycle = Object.create(Object.getPrototypeOf(Vehicle), {  
    "pedals" :{value: true}  
});  
  
```  
  
 `bicycle` Nesne özellikleri olan `wheels`, `engine`, `color`, ve `pedals`, ve kendi prototip `Vehicle.prototype`. JavaScript altyapısı bulur `pedals` özelliği `bicycle`, ve bulmak için prototip zincirinde sürdürmez `wheels`, `engine`, ve `color` özellikleri `Vehicle`.  
  
### <a name="changing-an-objects-prototype"></a>Bir Nesnenin Prototipini Değiştirme  
Internet Explorer 11, iç prototip nesne veya işlevi ile yeni bir örneğini kullanarak değiştirebilirsiniz [ __proto__ ](../../javascript/reference/proto-property-object-javascript.md) özelliği. Bu özelliği kullandığınızda, prototip zincirindeki diğer özellik ve yöntemlerle birlikte yeni prototipin özellik ve yöntemlerini de devralırsınız.  

> [!WARNING]
> `__proto__` Özelliği eski bir özelliktir. Kullanım [Object.getPrototypeOf](../reference/object-getprototypeof-function-javascript.md) yerine.
  
Aşağıdaki örnek, bir nesnenin prototipini nasıl değiştirebileceğinizi göstermektedir. Bu örnek, nesnenin prototipini değiştirdiğinizde nesnenin devralınan özelliklerinin nasıl değiştiğini göstermektedir.  
  
```JavaScript  
function Friend() {  
    this.demeanor = "happy";  
}  
  
function Foe() {  
    this.demeanor = "suspicious";  
}  
  
var friend = new Friend();  
var foe = new Foe();  
  
var player = new Object();  
player.__proto__ = foe;  
  
friend.ally = "Tom";  
  
if (console && console.log) {  
    console.log(player.demeanor === "happy" );      // Returns false  
    console.log(player.demeanor === "suspicious");  // Returns true  
    console.log(player.ally === "Tom");             // Returns false  
    // Turn the foe to a friend.  
    player.__proto__ = friend;  
    console.log(player.demeanor === "happy");       // Returns true  
    console.log(player.demeanor === "suspicious");  // Returns false  
    console.log(player.ally === "Tom");             // Returns true  
}  
```
