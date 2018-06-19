---
title: Object.getOwnPropertySymbols Function (JavaScript) | Microsoft Docs
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
ms.assetid: 68dd69b9-5a33-44c2-ba5f-21a4ae6c0879
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cc47ae365841332f11cb02da1469a4c9fff80c3
ms.sourcegitcommit: abae48f476832f79cc2c5bac43bb1226d3fe4e48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2018
ms.locfileid: "27814966"
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
  
console.log(symbols[0].toString());  
  
// Output:  
// undefined  
// Symbol(description)  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]