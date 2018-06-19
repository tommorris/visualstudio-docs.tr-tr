---
title: WeakSet nesnesi (JavaScript) | Microsoft Docs
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
ms.assetid: f97e6e7c-d678-4e32-978e-d949a7cafa3a
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e42849c03f698d6ed5f8b0e28725c85555a74d2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792002"
---
# <a name="weakset-object-javascript"></a>WeakSet Nesnesi (JavaScript)
Herhangi bir türde olabilir benzersiz nesneleri koleksiyonu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
setObj = new WeakSet()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Benzersiz olmayan bir nesneye eklemeyi deneyin bir `WeakSet`, yeni nesne koleksiyona eklenemiyor.  
  
 Farklı bir `Set`, yalnızca nesneleri koleksiyona eklenebilir. Rastgele değerler koleksiyonuna eklenemez.  
  
 İçinde bir `WeakSet` nesnesi, kümedeki nesnelere başvurular 'zayıf' tutulur. Bunun anlamı `WeakSet` oluşmasını nesnelerde çöp koleksiyonundan önlemez. Başvuru olduğunda (dışında `WeakSet`) nesnelere, nesnelerin atık toplayıcı toplayabilir.  
  
 `WeakSet`(veya `WeakMap`) nesneleri veya nesne meta verilerini önbelleğe alma ile ilgili bazı senaryolarda yararlı olabilir. Meta veri Genişletilebilir olmayan nesneler için örneğin, depolanabilir bir `WeakSet`, ya da bir önbellek kullanarak kullanıcı görüntülerinin oluşturabilir `WeakSet`.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `WeakSet` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|oluşturucusu|Bir küme oluşturur işlevi belirtir.|  
|prototip|Prototip kümesine ilişkin bir başvuru döndürür.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `WeakSet` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|add|Bir öğenin bir kümesine ekler.|  
|Sil|Belirtilen öğe bir kümeden kaldırır.|  
|sahip|Döndürür `true` kümesi belirtilen öğeyi içeriyorsa.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir grup için üye eklemek ve bunlar eklendiğini doğrulayın gösterilmektedir.  
  
```JavaScript  
var ws = new WeakSet();  
  
var str = new String("Thomas Jefferson");  
var num = new Number(1776);  
  
ws.add(str);  
ws.add(num);  
  
console.log(ws.has(str));  
console.log(ws.has(num));  
  
ws.delete(str);  
console.log(ws.has(str));  
  
// Output:  
// true  
// true  
// false  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]