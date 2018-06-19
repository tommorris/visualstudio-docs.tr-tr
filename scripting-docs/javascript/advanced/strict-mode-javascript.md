---
title: Katı mod (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1038
- VS.WebClient.Help.SCRIPT1050
- VS.WebClient.Help.SCRIPT1042
- VS.WebClient.Help.SCRIPT1041
- VS.WebClient.Help.SCRIPT1046
- VS.WebClient.Help.SCRIPT1045
- VS.WebClient.Help.SCRIPT1037
- VS.WebClient.Help.SCRIPT1039
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- strict mode
- use strict
ms.assetid: 0f27022a-f41c-4504-965c-5a2701f342cd
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77ee7d54dd265026b2bf4c9af52a71cccf9a7675
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789263"
---
# <a name="strict-mode-javascript"></a>Katı Mod (JavaScript)
Katı mod, daha iyi hata denetimi kodunuza tanıtmak için bir yoldur. Katı mod kullandığınızda, olamaz, örneğin, örtük olarak bildirilen değişkenleri kullanın veya salt okunur bir özellik için bir değer atamak veya Genişletilebilir değil bir nesne için özellik ekleme. Kısıtlamalar listelenen [katı mod kodda kısıtlamalar](../../javascript/advanced/strict-mode-javascript.md#rest) bu konunun ilerleyen bölümlerinde. Katı mod hakkında ek bilgi için bkz: [ECMAScript dil belirtimi, 5 edition](http://www.ecma-international.org/publications/standards/Ecma-262.htm).  
  
> [!WARNING]
>  Katı mod, Internet Explorer 10'dan önceki Internet Explorer sürümlerinde desteklenmiyor.  
  
## <a name="declaring-strict-mode"></a>Katı mod bildirme  
 Katı mod ekleyerek bildirebilir `"use strict";` başında bir dosya, bir program veya bir işlev. Bu tür bir bildirim olarak bilinen bir *yönerge başlangıç*. Katı mod bildirimi kapsamını kendi bağlama bağlıdır. (İşlev kapsamı dışında) bir genel bağlamda bildirilirse, tüm programda katı modda kodudur. Bir işlev bildirilirse, tüm işlevinde katı modda kodudur. Örneğin, aşağıdaki örnekte tüm katı modda kodudur ve "Değişkeni katı modda tanımsız." işlev dışındaki değişken bildirimi sözdizimi hatası neden olur  
  
```JavaScript  
"use strict";  
function testFunction(){  
    var testvar = 4;  
    return testvar;  
}  
  
// This causes a syntax error.  
testvar = 5;  
  
```  
  
 Aşağıdaki örnekte, yalnızca kod içinde `testFunction` katı modda değil. Değişken bildirimi işlevi dışındaki bir sözdizimi hatası neden olmaz ancak işlev içinde bildirimi desteklemez.  
  
```JavaScript  
function testFunction(){  
    "use strict";  
    // This causes a syntax error.  
    testvar = 4;  
    return testvar;  
}  
testvar = 5;  
  
```  
  
<a name="rest"></a>   
## <a name="restrictions-on-code-in-strict-mode"></a>Katı mod kodda kısıtlamalar  
 Aşağıdaki tabloda katı modda uygulanan en önemli kısıtlamaları listeler.  
  
|||||  
|-|-|-|-|  
|**Language öğesi**|**Kısıtlama**|**Hata:**|**Örnek**|  
|Değişken|Bir değişken bildirme olmadan kullanma.|SCRIPT5042: Değişken katı modda tanımlanmamış.|`testvar = 4;`|  
|Salt okunur özelliği|Salt okunur bir özellik yazma.|SCRIPT5045: Salt okunur özellikler için katı modda izin verilmiyor|`var testObj = Object.defineProperties({}, {     prop1: {         value: 10,         writable: false // by default     },     prop2: {         get: function () {         }     } }); testObj.prop1 = 20;  testObj.prop2 = 30;`|  
|Olmayan Genişletilebilir özelliği|Bir nesne için özellik ekleme, `extensible` özniteliği `false`.|SCRIPT5046: Genişletilebilir olmayan bir nesne için özellik oluşturulamıyor|`var testObj = new Object();  Object.preventExtensions(testObj);  testObj.name = "Bob";`|  
|`delete`|Bir değişken, bir işlev veya bir bağımsız değişken siliniyor.<br /><br /> Bir özelliği silmeye, `configurable` özniteliği `false`.|SCRIPT1045: Arama Sil \<ifade > katı modda izin verilmiyor|`var testvar = 15; function testFunc() {}; delete testvar; delete testFunc;  Object.defineProperty(testObj, "testvar", {     value: 10,     configurable: false     }); delete testObj.testvar;`|  
|Bir özellik çoğaltma|Özellik, birden çok kez bir nesne değişmez değer tanımlama.|SCRIPT1046: Birden fazla tanımı bir özelliğin katı modda izin verilmiyor|`var testObj = {     prop1: 10,     prop2: 15,     prop1: 20 };`|  
|Bir parametre adı çoğaltma|Bir parametre adı birden çok kez bir işlevde kullanma.|SCRIPT1038: katı modda izin verilmiyor yinelenen biçimsel parametresi adları|`function testFunc(param1, param1) {     return 1; };`|  
|Gelecekteki ayrılmış anahtar sözcükler|Gelecekteki ayrılmış bir anahtar sözcük değişken veya işlev adı olarak kullanma.|SCRIPT1050: Bir tanımlayıcı için gelecekte ayrılmış bir sözcük kullanımı geçersiz. Tanımlayıcı adı katı modda ayrılmıştır.|-                      `implements`<br /><br /> -                      `interface`<br /><br /> -                      `package`<br /><br /> -                      `private`<br /><br /> -                      `protected`<br /><br /> -                      `public`<br /><br /> -                      `static`<br /><br /> -                      `yield`|  
|Octals|Sekizlik değer tamsayısal bir hazır değer atama veya bir sekizli değerini bir kaçış kullanılmaya çalışılıyor.|SCRIPT1039: Sayısal sekizlik değişmez değerler ve katı modunda izin verilmeyen kaçış karakterleri|`var testoctal = 010; var testescape = \010;`|  
|`this`|Değeri `this` olduğunda genel nesne dönüştürülmedi `null` veya `undefined`.||`function testFunc() {     return this; } var testvar = testFunc();`<br /><br /> Katı olmayan modda değerini `testvar` genel nesne ancak katı modda değer `undefined`.|  
|`eval`bir tanımlayıcı olarak|"Eval" dize (değişken veya işlev adı, parametre adı vb.) bir tanımlayıcı olarak kullanılamaz.||`var eval = 10;`|  
|Bir deyim veya bir bloğu içinde bildirilen işlevi|Bir deyim veya bir bloğu içinde bir işlev bildiremezsiniz.|SCRIPT1047: katı modda işlev bildirimleri deyimi veya bloğunun yerleştirilemez. Yalnızca en üst düzeyinde veya doğrudan bir işlev gövdesi içinde görünebilir.|`var arr = [1, 2, 3, 4, 5]; var index = null; for (index in arr) {     function myFunc() {}; }`|  
|İçinde bildirilen değişken bir `eval` işlevi|İçinde bir değişken bildirilirse bir `eval` işlevi, bu işlevin dışında kullanılamaz.|SCRIPT1041: Kullanımı geçersiz 'Değerlendirme sürümü' katı mod|`eval("var testvar = 10"); testvar = 15;`<br /><br /> Dolaylı değerlendirme mümkündür, ancak hala dışında bildirilen bir değişken kullanamazsınız `eval` işlevi.<br /><br /> `var indirectEval = eval; indirectEval("var testvar = 10;"); document.write(testVar);`<br /><br /> Bu kodu bir hata SCRIPT5009 neden olur: 'testVar' tanımlanmadı.|  
|`Arguments`bir tanımlayıcı olarak|"Bağımsız değişkenler" dize (değişken veya işlev adı, parametre adı vb.) bir tanımlayıcı olarak kullanılamaz.|SCRIPT1042: Katı mod 'değişkenlerinde' geçersiz kullanımı|`var arguments = 10;`|  
|`arguments`bir işlev içinde|Yerel üyeleri değerlerini değiştiremezsiniz `arguments` nesnesi.||`function testArgs(oneArg) {     arguments[0] = 20; }`<br /><br /> Katı olmayan modda değerini değiştirebilir `oneArg` parametre değerini değiştirerek `arguments[0]`, böylece her ikisinin de değeri `oneArg` ve `arguments[0]` 20'dir. Değerinin katı modda değiştirilmesi `arguments[0]` değerini etkilemez `oneArg`, çünkü `arguments` yalnızca yerel bir kopya nesnesidir.|  
|`arguments.callee`|İzin verilmiyor.||`function (testInt) {     if (testInt-- == 0)         return;     arguments.callee(testInt--); }`|  
|`with`|İzin verilmiyor.|SCRIPT1037: katı modda 'with' deyime izin verilmez|`with (Math){     x = cos(3);     y = tan(7); }`|