---
title: Yineleyiciler ve oluşturucuları (JavaScript) | Microsoft Docs
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
ms.assetid: 68ef5b2f-0349-492b-b557-73ff2a2f90cf
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8a566e870c6e9589daed86d42e3fb933374cbb17
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="iterators-and-generators-javascript"></a>Yineleyiciler ve oluşturucuları (JavaScript)
Yineleyici bir listesi gibi bir kapsayıcı nesne geçiş yapmak için kullanılan bir nesnedir. JavaScript, yineleyici nesneyi ayrı bir yerleşik nesnesi değil, ancak uygulayan bir nesne bir `next` yöntem container nesnesi'na erişmek için.  
  
 İçinde [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)], kendi özel yineleyiciler oluşturabilirsiniz. Ancak, bunu yineleyiciler oluşturulmasını büyük ölçüde kolaylaştırma oluşturucuları kullanmak genellikle çok daha kolaydır. Oluşturucuları yineleyiciler için Fabrika işlevi türüdür. Oluşturucu işlevi kullanarak özel bir yineleyici oluşturmak için bkz: [oluşturucuları](#Generators).  
  
> [!CAUTION]
>  Üreticiler de desteklenmektedir [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)].  
  
## <a name="iterators"></a>Yineleyiciler  
 JavaScript yineleyici uyarlamasını belirli arabirimlere uygun iki veya üç nesneleri içerir:  
  
-   İterable arabirimi  
  
-   Yineleyici arabirimi  
  
-   IteratorResult arabirimi  
  
 Bu arabirimleri kullanarak özel yineleyiciler oluşturabilirsiniz. Bu sayede bir iterable nesnesini kullanarak çapraz geçiş `for…of` deyimi.  
  
### <a name="iterable-interface"></a>İterable arabirimi  
 Iterable arabirimi iterable bir nesne için gerekli bir arabirimdir (yineleyici edinilebilir nesnesi). Örneğin, `C` içinde `for (let e of C)` Iterable arabirimi uygulamalıdır.  
  
 İterable nesneyi yineleyici döndürür Symbol.iterator yöntemi sağlamanız gerekir.  
  
```JavaScript  
obj[Symbol.iterator] = function() { return iterObj; }  
```  
  
 Bu özellik bağımsız değişkenler kabul eder ve bir nesne döndüren bir işlev olmalıdır (`iterObject`) için uygun `Iterator` arabirimi.  
  
 Diziler dahil olmak üzere birçok yerleşik türleri iterable sunulmuştur. `for…of` Döngü iterable nesneyi kullanır. (Ancak, tüm yerleşik iterables yineleyiciler değildir. For example, bir dizi nesnesi bir yineleyici değildir, ancak bir ArrayIterator de iterable iken iterable,.)  
  
### <a name="iterator-interface"></a>Yineleyici arabirimi  
 Symbol.iterator yöntemi tarafından döndürülen nesne uygulamalıdır `next` yöntemi. `next` Yöntemi aşağıdaki söz dizimini sahiptir.  
  
```JavaScript  
iterObj.next() = function() { return iterResultObj; };  
```  
  
 `next` Yöntemi bir değer döndüren bir işlev değil. İşlevi bir nesne döndürür (`iterResultObj`) için uygun `IteratorResult` arabirimi. Önceki çağrı varsa `next` yineleyici yöntemi döndürülen bir `IteratorResult` nesnesindeki `done` özelliği true ise, ardından yineleme sonlandırılır ve `next` yöntemi yeniden çağrılmaz.  
  
 Yineleyiciler de içerebilir bir `return` betiği ile bittiğinde yineleyici düzgün bir şekilde elden emin olmak için yöntem.  
  
### <a name="iteratorresult-interface"></a>IteratorResult arabirimi  
 IteratorResult arabirimi sonucu için gerekli bir arabirimdir `next` yineleyici yöntemi. Tarafından döndürülen nesne `next` sağlamalısınız bir `done` ve `value` özelliği.  
  
```JavaScript  
var iterResultObj = { done: true|false, value: value }  
```  
  
 `done` Özelliği döndürür yineleyici'nin durumunu `next` yöntem çağrısı, true veya false. Yineleyici sonuna ulaşıldı, `done` true değerini döndürür. Sonuna ulaşıldı değil, `done` false ve değeri kullanılabilir döndürür. Varsa `done` özelliği (ya da kendi kendi veya devralınmış bir özellik) yok, sonucu `done` false olarak kabul edilir.  
  
 Varsa `done` false, `value` özelliği geçerli yineleme öğe değerini döndürür. Varsa `done` budur yineleyici dönüş değerini dönüş değeri sağlanmazsa, doğrudur. Yineleyici bir dönüş değeri yoksa `value` tanımlanmadı. Bu durumda, `value` özelliği mevcut bir açık bir değer özelliği devralmıyor durumunda uyumlu nesnesinden.  
  
<a name="Generators"></a>   
## <a name="generators"></a>Oluşturucuları  
 Kolayca oluşturun ve özel yineleyiciler kullanmak için bir veya daha fazla ile birlikte işlevi * sözdizimini kullanarak oluşturucu işlevi oluşturma `yield` ifadeler. Oluşturucu işlevi yürütmek oluşturucu işlev gövdesi sağlayan bir yineleyici (diğer bir deyişle, bir oluşturucu), döndürür. Sonraki işlev yürütür `yield` veya `return` deyimi.  
  
 Çağrı `next` Oluşturucu işlevinden sonraki değeri döndürmek için yineleyici yöntemi.  
  
 Aşağıdaki örnek, bir dize nesnesi için bir yineleyici döndüren bir oluşturucuyu gösterir.  
  
```JavaScript  
function* stringIter() {  
    var str = "bobsyouruncle";  
    var idx = 0;  
    while(idx < str.length)  
        yield str[idx++];  
}  
  
var si = stringIter();  
  
console.log(si.next().value);  
console.log(si.next().value);  
console.log(si.next().value);  
  
// Output:  
// b  
// o  
// b  
  
```  
  
 Bir üreteci verim işleneni ifade çağrısı sonlandırır `next` ve döndürür bir `IteratorResult` iki özellik nesnesiyle `done` (`done=false`) ve `value` (`value=operand`). `operand` isteğe bağlıdır ve ardından değerini bırakılırsa tanımlanmadı.  
  
 Bir oluşturucuyu içinde bir `return` açıklamayı sonlandıran oluşturucunun döndürerek bir `IteratorResult` ile `done=true` değer özelliği için isteğe bağlı işlenen sonuç yanı sıra.  
  
 Aynı zamanda bir `yield*` ifade yerine `yield` başka bir oluşturucu veya bir dizi veya dize gibi başka bir iterable nesneye temsilci seçmek için.  
  
 Aşağıdaki kod önceki örneğe eklerseniz `yield*` için temsilciler `stringIter` üreteci.  
  
```JavaScript  
function* strIter() {  
    yield "jo";  
    yield* stringIter();  
}  
  
var si2 = strIter();  
  
console.log(si2.next().value);  
console.log(si2.next().value);  
console.log(si2.next().value);  
console.log(si2.next().value);  
  
// Output:  
// jo  
// b  
// o  
// b  
```  
  
 Bağımsız değişken geçirme daha gelişmiş oluşturucuları oluşturabilirsiniz `next` ve oluşturucunun durumunu değiştirmek için bir bağımsız değişken kullanma. `next` daha önce yürütülen sonuç değeri olur `yield` ifade. Aşağıdaki örnekte bir değeri 100'e geçirdiğinizde `next` yöntemi, oluşturucunun 's iç dizin değeri sıfırlayın.  
  
```  
function* strIter() {  
    var str = "jobob";  
    var idx = 0;  
    while(idx < str.length) {  
        var modify = yield str[idx++];  
        if(modify == 100) {  
            idx = 0;  
        }  
    }
}
  
var si3 = strIter();  
  
console.log(si3.next().value);  
console.log(si3.next().value);  
console.log(si3.next().value);  
console.log(si3.next(100).value);  
  
// Output:  
// j  
// o  
// b  
// j  
  
```  
  
 Diğer gelişmiş oluşturucuları oluşturucunun 's çağırabilir `throw` yöntemi. Oluşturucunun burada duraklatıldı noktada durum için atılmış hata görünür (sonraki önce `yield` deyimi).
