---
title: "Symbol.for işlevi (JavaScript) | Microsoft Docs"
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
ms.assetid: 27db15f3-9108-4892-8f89-e84031729cb6
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b7e47c00fbaa321d71a3eeba79e523eee719fb2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="symbolfor-function-javascript"></a>Symbol.for İşlevi (JavaScript)
Belirtilen anahtar için simge döndürür veya anahtar mevcut değilse yeni bir anahtar kullanılarak yeni bir sembol nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb  
Symbol.for(key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `key`  
 Gerekli. Açıklama olarak da kullanılan simge için anahtar.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem simgenin genel sembol kayıt defterinde arar. Simgeler dizeleri olarak seri, belirli bir dizenin tüm aramaları için doğru simge eşler emin olmak için genel sembol kayıt defteri kullanın.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
var sym = Symbol.for("desc");  
  
console.log(sym.toString());  
  
// Two different object references.  
console.log(Symbol("symbol") === Symbol.for("symbol");)  
// Single object reference.   
console.log(Symbol.for("symbol") === Symbol.for("symbol");)  
  
// Output:  
// Symbol(desc);  
// false  
// true  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]