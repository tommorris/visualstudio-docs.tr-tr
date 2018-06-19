---
title: Nesneler ve diziler (JavaScript) | Microsoft Docs
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
- arrays [JavaScript]
- arrays [JavaScript], objects
ms.assetid: f5106284-1240-4f47-8c3b-5a45e227e5e1
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6776701ba108ae0ecefc2331c2b12272e0c1be19
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789134"
---
# <a name="objects-and-arrays-javascript"></a>Nesneler ve Diziler (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]nesne özellikleri ve yöntemleri koleksiyonlarıdır. Bir yöntem bir nesne üyesi olan bir işlevdir. Bir değer veya bir nesne üyesi (biçiminde bir dizi veya nesne) değerleri kümesi özelliğidir. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]dört nesne türlerini destekler:  
  
-   Gibi dahili nesneleri `Array` ve `String`.  
  
-   Oluşturduğunuz nesneleri.  
  
-   Nesneleri gibi ana bilgisayar `window` ve `document`.  
  
-   ActiveX nesneleri.  
  
## <a name="expando-properties-and-methods"></a>Expando Özellikleri ve Yöntemleri  
 Tüm nesneler [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] expando özellikleri ve eklenebilir ve çalışma zamanında kaldırılabilir yöntemleri destekler. Bu özellikleri ve yöntemleri numaralarına göre tanımlanabilir ve herhangi bir ad olabilir. Özellik veya yöntem adını basit bir tanımlayıcı ise, bu nesne adında bir süre sonra gibi yazılabilir `myObj.name`, `myObj.age`, ve `myObj.getAge` aşağıdaki kodda:  
  
```JavaScript  
var myObj = new Object();  
myObj.name = "Fred";  
myObj.age = 42;  
  
myObj.getAge =   
    function () {  
        return this.age;  
    };  
  
document.write(myObj.name);  
document.write("<br/>");  
document.write(myObj.age);  
document.write("<br/>");  
document.write(myObj.getAge());  
  
// Output:  
// Fred  
// 42  
// 42  
  
```  
  
 Özellik veya yöntem adını basit bir tanımlayıcı değil veya komut dosyası yazma aynı anda bilinmiyor, index özelliği için bir ifade köşeli ayraç içinde kullanabilirsiniz. Tüm expando özellik adlarını [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] dizelere nesnesine eklenmeden önce dönüştürülür.  
  
```JavaScript  
var myObj = new Object();  
  
// Add two expando properties that cannot be written in the  
// object.property syntax.  
// The first contains invalid characters (spaces), so must be  
// written inside square brackets.  
myObj["not a valid identifier"] = "This is the property value";  
  
// The second expando name is a number, so it also must  
// be placed inside square brackets  
myObj[100] = "100";  
```  
  
 Bir nesne bir tanımından oluşturma hakkında daha fazla bilgi için bkz: [nesneleri oluşturma](../javascript/creating-objects-javascript.md).  
  
## <a name="arrays-as-objects"></a>Nesne Olarak Diziler  
 İçinde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], nesneler ve diziler işlenir neredeyse aynı, diziler yalnızca bir özel tür olduğundan nesne. Nesneler ve diziler özellikleri ve yöntemleri olabilir.  
  
 Diziler sahip bir `length` özelliği, ancak nesneleri yapın. Bir değer bir dizi öğesine dizinini atadığınızda uzunluğundan (örneğin, `myArray[100] = "hello"`), `length` özelliği otomatik olarak yeni uzunluğa yükseltilmiştir. Benzer şekilde, yaptığınız `length` özelliği küçük olan dizindir dizi uzunluğu dışında herhangi bir öğe silinir.  
  
```JavaScript  
// An array with three elements  
var myArray = new Array(3);  
  
// Add some data  
myArray[0] = "Hello";  
myArray[1] = 42;  
myArray[2] = new Date(2000, 1, 1);  
  
document.write("original length is: " + myArray.length);  
document.write("<br/>");  
// Add some expando properties  
myArray.expando = "JavaScript!";  
myArray["another Expando"] = "Windows";  
  
// This will still display 3, since the two expando properties  
// don't affect the length.  
document.write("new length is : " + myArray.length);  
  
// Output:  
// original length is: 3  
// new length is : 3  
  
```  
  
 Diziler üzerinden yineleme ve üyeleri işlemek için yöntemleri sağlar. Aşağıdaki örnek bir dizide saklanan nesnelerin özelliklerini edinme gösterir.  
  
```JavaScript  
var myArray = new Array(3);  
  
// Add some data  
for(var i = 1; i <= 3; i++) {  
    myArray[i] = new Date(2000 + i, 1, 1);  
}  
  
myArray.forEach(function (item) {  
    document.write(item.getFullYear());  
});  
  
// Output:  
// 2001  
// 2002  
// 2003  
```  
  
## <a name="multi-dimensional-arrays"></a>Çok Boyutlu Diziler  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]doğrudan destek çok boyutlu diziler yapar ancak başka bir dizinin öğeleri içindeki diziler depolayarak çok boyutlu diziler davranışını elde edebilirsiniz. (Verileri diğer diziler dahil olmak üzere, dizi öğeleri içinde herhangi bir tür depolayabilirsiniz.) Örneğin, aşağıdaki kodu en fazla 5 numaraları için çarpma tablosu oluşturur.  
  
```JavaScript  
// The size of the table.  
var iMaxNum = 5;  
// Loop counters.  
var i, j;  
  
// Set the length of the array to iMaxNum + 1.   
// The first array index is zero, not 1.  
var MultiplicationTable = new Array(iMaxNum + 1);  
  
// Loop for each major number (each row in the table)  
for (i = 1; i <= iMaxNum; i++)  
{  
    // Create the columns in the table  
    MultiplicationTable[i] = new Array(iMaxNum + 1);  
  
    // Fill the row with the results of the multiplication  
    for (j = 1; j <= iMaxNum; j++)  
    {  
        MultiplicationTable[i][j] = i * j;  
    }  
}  
  
document.write(MultiplicationTable[3][4]);  
document.write("<br/>");   
document.write(MultiplicationTable[5][2]);  
document.write("<br/>");  
document.write(MultiplicationTable[1][4]);  
  
// Output:  
// 12  
// 10  
// 4  
  
```