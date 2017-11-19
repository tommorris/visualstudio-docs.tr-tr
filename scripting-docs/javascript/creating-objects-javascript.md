---
title: "Nesneler (JavaScript) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- constructors, including properties and methods
- function constructor
- creating objects, constructor functions
- constructor functions
- prototype objects
- creating objects
- custom objects, creating
- creating objects, about creating objects
- objects, creating [JavaScript]
- creating objects, prototypes
- custom objects
- initializing objects, using constructors
ms.assetid: 58d1baa5-4fe8-4a56-a926-5b11765df704
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ba7962179cc2f0fcb972caee692edabee368c7d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="creating-objects-javascript"></a>Nesne Oluşturma (JavaScript)
Çeşitli yollarla JavaScript'te kendi nesneleri oluşturabilirsiniz vardır. Doğrudan örneği bir [nesne](../javascript/reference/object-object-javascript.md) ve kendi özellikleri ve yöntemleri ekleyin. Veya, nesneyi tanımlamak için nesne değişmez değer gösterimi kullanabilirsiniz. Oluşturucu işlevi, nesneyi tanımlamak için de kullanabilirsiniz. Oluşturucu işlevleri kullanma hakkında daha fazla bilgi için bkz: [türlerini tanımlamak için oluşturucular kullanma](../javascript/advanced/using-constructors-to-define-types.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, bazı özellikleri ekleyin ve bir nesne örneği gösterilmektedir. Bu durumda yalnızca `pasta` nesnesi `grain`, `width`, ve `shape` özellikleri.  
  
```JavaScript  
const pasta = new Object();  
pasta.grain = "wheat";  
pasta.width = 0.5;  
pasta.shape = "round";  
pasta.getShape = function() {   
    return this.shape;   
};  
document.write(pasta.grain);  
document.write("<br/>");  
document.write(pasta.getShape());  
  
// Output:  
// wheat  
// round  
  
```  
  
## <a name="object-literals"></a>Nesne değişmez değerleri  
 Bir nesne yalnızca bir örneğini oluşturmak istediğinizde nesne değişmez değer gösterimi de kullanabilirsiniz. Aşağıdaki kod, nesne değişmez değer gösterimini kullanarak bir nesne örneği gösterilmektedir.  
  
```JavaScript  
const pasta = {  
    grain: "wheat",  
    width: 0.5,  
    shape: "round"  
};  
```  
  
 Bir nesne içinde bir oluşturucu değişmez değer de kullanabilirsiniz.  
  
> [!CAUTION]
>  Aşağıda açıklanan özellikleri yalnızca desteklenen [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)].  
  
 İçinde [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)], toplu değer sözdizimi nesne değişmez değer oluşturmak için kullanabilirsiniz.  
  
```JavaScript  
const key = 'a';  
const value = 5;  
  
// Older version  
const obj1 = {  
    key: key,  
    value: value  
};  
  
// Edge mode  
const obj2 = {key, value};  
  
console.log(obj2);  
  
// Output:  
// [object Object] {key: "a", value: 5}  
```  
  
 Aşağıdaki örnek, nesne değişmez değerlerine yöntemlerini tanımlamak için toplu değer sözdizimi kullanımını göstermektedir.  
  
```JavaScript  
// Older versions  
const obj = {  
    method1: function() {},  
    method2: function() {}  
};  
  
// Edge mode  
const obj = {  
    method1() {},  
    method2() {}  
};  
```  
  
 Ayrıca özellik adları dinamik olarak nesne değişmez değerlerinde ayarlayabilirsiniz [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]. Aşağıdaki kod örneği, dinamik olarak kümesi sözdizimini kullanarak bir nesne için özellik adı oluşturur.  
  
```JavaScript  
const propName = "prop_42";  
  
const obj = {  
    value: 0,  
    set [propName](v) {  
        this.value = v;  
    }  
}  
  
console.log(obj.value);  
// Runs the setter property.  
obj.prop_42 = 777;  
console.log(obj.value);  
  
// Output:  
// 0  
// 777  
  
```  
  
 Aşağıdaki kod örneğinde get sözdizimini kullanarak dinamik olarak bir nesne için özellik adı oluşturur.  
  
```JavaScript  
const propName = "prop_42";  
  
const obj = {  
    get [propName]() {  
        return 777;  
    }  
}  
  
console.log(obj.prop_42);  
  
// Output:  
// 777  
```  
  
 Aşağıdaki kod örneğinde hesaplanan özelliği kullanılarak oluşturulur [oku işlev sözdizimi](../javascript/functions-javascript.md) özellik adına 42 eklenecek.  
  
```JavaScript  
const obj = {  
    [ 'prop_' + (() => 42)() ]: 42  
};  
```
