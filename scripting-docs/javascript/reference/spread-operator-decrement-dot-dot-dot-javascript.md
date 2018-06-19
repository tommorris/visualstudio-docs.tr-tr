---
title: Spread işleci (...) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 10263a4c-bd27-4d87-9917-fb4b6bf373db
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a07d480360441906c445faa196f6d7771f97d75d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791579"
---
# <a name="spread-operator--javascript"></a>Spread İşleci (JavaScript)
Bir dizi bölümlerini değişmez değer (örneğin, başka bir dizi değişmez değer) iterable bir ifadeden başlatılması için izin verir veya bir ifade birden çok bağımsız değişkenler (işlev çağrıları) genişletilmesini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
var array = [[arg0ToN ,] ...iterable [, arg0ToN]]  
func([args ,] ...iterable [, args | ...iterable])  
  
```  
  
## <a name="parameters"></a>Parametreler  
 `iterable`  
 Gerekli. İterable bir nesne.  
  
 `arg0ToN`  
 İsteğe bağlı. Bir veya daha fazla dizi öğelerini değişmez.  
  
 `args`  
 İsteğe bağlı. Bir veya daha fazla bağımsız değişken bir işlev.  
  
## <a name="remarks"></a>Açıklamalar  
 Yineleyiciler hakkında daha fazla bilgi için bkz: [yineleyiciler ve oluşturucuları](../../javascript/advanced/iterators-and-generators-javascript.md). Rest parametre olarak forma işlecini kullanarak daha fazla bilgi için bkz: [işlevler](../../javascript/functions-javascript.md).  
  
## <a name="example"></a>Örnek  
 Bu aşağıdaki kod örneğinde kullanımı ile yayılan işleci kullanımı contrasted `concat` yöntemi.  
  
```JavaScript  
var a, b, c, d, e;  
a = [1,2,3];  
b = "dog";  
c = [42, "cat"];  
  
// Using the concat method.  
d = a.concat(b, c);  
  
// Using the spread operator.  
e = [...a, b, ...c];  
  
console.log(d);  
console.log(e);  
  
// Output:  
// 1, 2, 3, "dog", 42, "cat"  
// 1, 2, 3, "dog", 42, "cat"  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir işlev çağrısında yayılan işleci kullanmayı gösterir. Bu örnekte, iki dizi değişmez değerleri yayılan işlecini kullanarak işlevi iletilir ve diziler için birden fazla bağımsız değişkenini genişletilir.  
  
```JavaScript  
function f(a, b, c, x, y, z) {  
  return a + b + c + x + y + z;  
}  
  
var args = [1, 2, 3];  
console.log(f(...args, 4, ...[5, 6]));  
  
// Output:  
// 21  
  
```  
  
## <a name="example"></a>Örnek  
 Forma işleçlerle önceden kullanımını gerekli kod basitleştirebilir `apply`.  
  
```JavaScript  
function f(x, y, z) {  
    return x + y + z;  
}  
  
var args = [1, 2, 3];  
  
// Old method  
f.apply(this, args);  
// New method  
f(...args);  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)