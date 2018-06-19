---
title: Sembol nesnesi (JavaScript) | Microsoft Docs
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
ms.assetid: 2ad059f1-4b7f-4758-882a-c74ce1283ab0
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd755d5b753eb91b89b869645287685a97f8f571
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791903"
---
# <a name="symbol-object-javascript"></a>Sembol Nesnesi (JavaScript)
Benzersiz bir tanımlayıcı oluşturmanıza olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
obj = Symbol(desc)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `desc`  
 İsteğe bağlı. Simgenin açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 Simgenin nesneleri girişim varolan nesne özellikleri, istenmeyen bir görünürlük ve diğer eşgüdümlü olmayan eklemeler hiçbir olasılığıyla birlikte var olan nesneleri başka bir kodla eklenecek özellikleri sağlar.  
  
 Simge bir temel veri türüdür. Simgenin nesneleri kullanarak oluşturulamıyor `new` işleci.  
  
 Sembol genel sembol kayıt defteri nesneleri eklemek için kullanın `Symbol.for` ve `Symbol.keyFor` işlevleri. Simgeler dizeleri olarak seri, belirli bir dizenin tüm aramaları için doğru simge eşler emin olmak için genel sembol kayıt defteri kullanın.  
  
 JavaScript genel kapsamda kullanılabilir aşağıdaki yerleşik simge değerlerini içerir.  
  
|Simgesi|Açıklama|  
|------------|-----------------|  
|`Symbol.hasInstance`|Bu yöntem Oluşturucusu nesne bir nesne Oluşturucusu 's örnekleri biri olarak tanır olup olmadığını belirler. Tarafından dahili olarak kullanılan `instanceof` işleci.|  
|`Symbol.isConcatSpreadable`|Bu özellik bir nesne tarafından dizi öğeleri için düzleştirilmiş olup olmadığını gösteren bir Boole değeri döndürür `Array.concat`.|  
|`Symbol.iterator`|Bu yöntem bir nesne için varsayılan yineleyici döndürür. Tarafından dahili olarak kullanılan `for...of` deyimi.|  
|`Symbol.toPrimitive`|Bu yöntem bir nesnenin karşılık gelen bir ilkel değerine dönüştürür. Tarafından dahili olarak kullanılan `ToPrimitive` soyut işlemi.|  
|`Symbol.toStringTag`|Bu özellik, bir nesne varsayılan dize açıklamasını oluşturmaya yardımcı olmak için kullanılan bir string değeri döndürür. Yerleşik bir yöntem tarafından dahili olarak kullanılan `Object.toString` yöntemi.|  
|`Symbol.unscopables`|Bu özellik özellikleri dışında bir nesne döndürür `with` ortamı bağlamaları ilişkili nesne.|  
  
## <a name="functions"></a>İşlevler  
 Aşağıdaki tabloda işlevlerini listeler `Symbol` nesnesi.  
  
|||  
|-|-|  
|Özellik|Açıklama|  
|[Symbol.for](../../javascript/reference/symbol-for-function-javascript.md)|Belirtilen anahtar için simge döndürür veya anahtar mevcut değilse yeni bir anahtar kullanılarak yeni bir sembol nesnesi oluşturur.|  
|[Symbol.keyFor](../../javascript/reference/symbol-keyfor-function-javascript.md)|Belirtilen bir simgeyi anahtarı döndürür.|  
|||  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
(function() {  
  
    // module-scoped symbol  
    var key = Symbol("description");  
  
    function MyClass(privateData) {  
      this[key] = privateData;  
    }  
  
    MyClass.prototype = {  
      someFunc: function() {  
        return "data: " + this[key];  
      }  
    };  
  
    var c = new MyClass("private data")  
    console.log(key);  
    console.log(c["key"]);  
    console.log(c.someFunc());  
  
})();  
  
// Output:  
// undefined  
// undefined  
// data: private data  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]