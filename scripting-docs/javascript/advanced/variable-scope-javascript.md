---
title: "Değişken kapsamı (JavaScript) | Microsoft Docs"
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
- scope, JavaScript
- variable scope [JavaScript]
- variables, scope [JavaScript]
ms.assetid: a811a9a6-856f-46e9-8be3-f2d22a0c245f
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5afc99bf3d1006b68e1d6c4c8d5bbcfc90eb776f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="variable-scope-javascript"></a>Değişken Kapsamı (JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]iki kapsamına sahiptir: Genel ve yerel. Bir işlev tanımı dışında bildirilmiş bir değişken genel bir değişkendir ve değerini erişilebilir ve programınızı boyunca değiştirilebilir. Bir işlev tanımı içinde bildirilen bir yerel değişkendir. Oluşturulan ve işlev yürütülür ve işlev dışındaki herhangi bir kod tarafından erişilemez her zaman yok. JavaScript blok kapsamı desteklemez (kaydedileceği küme ayraçları kümesi `{. . .}` yeni bir kapsam tanımlar), hariç blok kapsamlı değişkenler özel durumda.  
  
## <a name="scope-in-javascript"></a>JavaScript kapsamında  
 Yerel değişkene genel değişkeni ile aynı ada sahip olabilir, ancak tamamen ayrı; bir değişkenin değerini değiştirerek diğer üzerinde etkisi yoktur. Yalnızca yerel sürümü içinde bildirilmiş işlevi içinde bir anlamı yoktur.  
  
```JavaScript  
// Global definition of aCentaur.  
var aCentaur = "a horse with rider,";  
  
// A local aCentaur variable is declared in this function.  
function antiquities(){  
  
   var aCentaur = "A centaur is probably a mounted Scythian warrior";  
}  
  
antiquities();  
aCentaur += " as seen from a distance by a naive innocent.";  
  
document.write(aCentaur);  
  
// Output: "a horse with rider, as seen from a distance by a naive innocent."  
```  
  
 İçinde var kapsam başındaki bildirilen gibi JavaScript değişkenler değerlendirilir. Bazen bu beklenmeyen davranışlara, aşağıda gösterildiği gibi sonuçlanır.  
  
```JavaScript  
var aNumber = 100;  
tweak();  
  
function tweak(){  
  
    // This prints "undefined", because aNumber is also defined locally below.  
    document.write(aNumber);  
  
    if (false)  
    {  
        var aNumber = 123;    
    }  
}  
```  
  
 Zaman [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] bir işlev yürütülmeden önce tüm değişken bildirimleri için gibi görünüyor `var someVariable;`. Bir başlangıç değeriyle değişkenleri oluşturur `undefined`. Bir değişkene bir değer, örneğin, bildirilirse `var someVariable = "something";`, sonra da hala başlangıçta değerine sahip `undefined` ve bildirimi içeren satırı yürütüldüğünde bildirilen değerini alır.  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]bildirim koşullu bir blok veya diğer yapı içinde olup herhangi bir kod çalıştırmadan önce tüm değişken bildirimleri işler. Bir kez [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] sahip tüm değişkenleri bulundu, kod işlevinde yürütür. Atama ifadesinin sol tarafında görünür ancak ile bildirilmedi bir değişken örtük olarak bir işlev içinde - diğer bir deyişle, bildirilirse `var` -genel bir değişken olarak oluşturulur.  
  
 JavaScript'te, bir iç (iç içe) işlevi bile işlevi döndükten sonra işlevi kendisini aynı kapsamı yok yerel değişkenleri başvurular depolar. Bu başvurular kümesi bir kapanışı olarak adlandırılır. Aşağıdaki örnekte, çünkü birinci çağrı olarak aynı iletiyi ("Merhaba fatura") iç işlevi için ikinci çağrı yapılandırmayı çıkarır. dış işlev için giriş parametresi `name`, kapatma iç işlev için depolanan yerel bir değişkendir.  
  
```JavaScript  
function send(name) {  
    // Local variable 'name' is stored in the closure  
    // for the inner function.  
    return function () {  
        sendHi(name);  
    }  
}  
  
function sendHi(msg) {  
    console.log('Hello ' + msg);  
}  
  
var func = send('Bill');  
func();  
// Output:  
// Hello Bill  
sendHi('Pete');  
// Output:  
// Hello Pete  
func();  
// Output:  
// Hello Bill  
```  
  
## <a name="block-scoped-variables"></a>Blok kapsamlı değişkenler  
 Internet Explorer 11 desteği tanıtır [izin](../../javascript/reference/let-statement-javascript.md) ve [const](../../javascript/reference/const-statement-javascript.md), blok kapsamlı değişkenler olduğu. Bu değişkenler, küme ayraçları için `{. . .}` yeni bir kapsam tanımlayın. Bu değişkenlerinden biri belirli bir değeri ayarladığınızda, değer, ayarlandığı kapsam için geçerlidir.  
  
 Aşağıdaki örnek kullanımını göstermektedir `let` ve blok kapsamı.  
  
> [!NOTE]
>  Aşağıdaki kod, Internet Explorer 11 standartları modu ve sonraki sürümlerinde desteklenir.  
  
```JavaScript  
let x = 10;  
var y = 10;  
{  
    let x = 5;  
    var y = 5;  
    {  
        let x = 2;  
        var y = 2;  
        document.write("x: " + x + "<br/>");  
        document.write("y: " + y + "<br/>");  
        // Output:  
        // x: 2  
        // y: 2  
    }  
    document.write("x: " + x + "<br/>");  
    document.write("y: " + y + "<br/>");  
    // Output:  
    // x: 5  
    // y: 2  
}  
  
document.write("x: " + x + "<br/>");  
document.write("y: " + y + "<br/>");  
// Output:  
// x: 10  
// y: 2  
```