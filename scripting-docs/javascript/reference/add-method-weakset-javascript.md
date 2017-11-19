---
title: "add yöntemi (WeakSet) (JavaScript) | Microsoft Docs"
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
ms.assetid: d35d0287-6b33-4720-b9d7-8954c428ce4e
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3ab486beaba4a26c73930b5ceaee927f73aa077a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="add-method-weakset-javascript"></a>add Yöntemi (WeakSet) (JavaScript)
Yeni bir öğe ekler bir `WeakSet`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
weaksetObj.add(obj)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `weaksetObj`  
 Gerekli. A `WeakSet` nesnesi.  
  
 `obj`  
 Gerekli. Yeni öğesinin `WeakSet`.  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni öğe rastgele bir değeri yerine bir nesne olmalıdır ve benzersiz olması gerekir. Benzersiz olmayan bir öğeye eklerseniz, bir `WeakSet`, yeni öğe koleksiyona eklenemiyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir grup için üye eklemek ve bunlar eklendiğini doğrulamak gösterilmiştir.  
  
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