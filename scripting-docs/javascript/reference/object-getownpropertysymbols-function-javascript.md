---
title: "Object.getOwnPropertySymbols işlevi (JavaScript) | Microsoft Docs"
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
ms.assetid: 68dd69b9-5a33-44c2-ba5f-21a4ae6c0879
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2bcddba77305e30e4c5ae13f6b1fc5c9385b7108
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="objectgetownpropertysymbols-function-javascript"></a>Object.getOwnPropertySymbols İşlevi (JavaScript)
Bir nesnenin kendi Sembol Özellikleri döndürür. Bir nesnenin kendi sembol özellikleri doğrudan nesnede tanımlanır ve nesnenin prototip devralınmaz izinlerdir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Object.getOwnPropertySymbols(object);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Kendi sembolleri içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Nesnenin kendi sembolleri içeren bir dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmanız gereken `Object.getOwnPropertySymbols` nesnenin sembol özellikleri alınamıyor. `Object.getOwnPropertyNames`Sembol Özellikleri döndürmez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir nesne sembol özelliklerini alma gösterir.  
  
```JavaScript  
var obj = {};  
var key = Symbol('description');  
  
obj[key] = 'data';  
  
var symbols = Object.getOwnPropertySymbols(obj);  
  
console.log(s[0].toString());  
  
// Output:  
// undefined  
// Symbol(description)  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]