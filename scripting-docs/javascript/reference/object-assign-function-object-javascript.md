---
title: Object.Assign nesnesi (nesne) (JavaScript) | Microsoft Docs
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
ms.assetid: 2dd6b312-dcd3-414e-8d53-088c6341c46d
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c156369299e58eac556d43a87476de2ce09173e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="objectassign-function-object-javascript"></a>Object.assign Nesnesi (Nesne) (JavaScript)
Değerleri bir veya daha çok kaynak nesneden bir hedef nesnesine kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Object.assign(target, ...sources );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `target`  
 Gerekli. Numaralandırılabilir özellikleri kopyalanan sanal bir nesne.  
  
 `...sources`  
 Gerekli. Numaralandırılabilir özellikleri kopyalandığı bir veya daha fazla nesne.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Bu işlev oluşturur bir `TypeError` kopyalama işlemini sonlandırır bir atama hata varsa. A `TypeError` bir hedef özellik yazılabilir değilse oluşturulur.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev, hedef nesne döndürür. Yalnızca *numaralandırılabilir kendi* özellikler hedef nesnesi için kaynağı nesnesinden kopyalanır. Birleştirme veya nesneleri kopyalamak için bu işlevi kullanabilirsiniz.  
  
 `null`veya `undefined` boş nesneleri ve hedef nesnesi için hiçbir şey katkıda gibi kaynakları kabul edilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği kullanarak bir nesnenin birleştirme gösterilmektedir `Object.assign`.  
  
```JavaScript  
var first = { name: "Bob" };  
var last = { lastName: "Smith" };  
  
var person = Object.assign(first, last);  
console.log(person);  
  
// Output:  
// { name: "Bob", lastName: "Smith" }   
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örneği kullanarak bir nesnenin kopyalama gösterilmektedir `Object.assign`.  
  
```JavaScript  
var obj = { person: "Bob Smith"};  
var clone = Object.assign({}, obj);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]