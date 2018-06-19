---
title: prototype özelliği (dize) | Microsoft Docs
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
ms.assetid: 437ce478-9c45-45f7-8952-bd71856cfcd8
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df8c6abbd64fce9172d805c2e22dee51f4fbbee4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791264"
---
# <a name="prototype-property-string"></a>prototype Özelliği (Dize)
Prototip dizesinin bir sınıf için bir başvuru döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
string.prototype  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `string` Bağımsız değişken bir dize adıdır.  
  
 Kullanım `prototype` temel nesne sınıfı için işlevselliği sağlamak için özellik. Bir nesnenin "Bu nesneye atanmış prototip davranışını devral" yeni örnekleri.  
  
 Örneğin, bir yöntem eklemek için `String` dizenin son öğenin değerini döndürür nesne, işlev bildirme, ekleyin `String.prototype`ve ardından onu kullanabilirsiniz.  
  
```JavaScript  
function string_last( ){  
    return this.charAt(this.length - 1);  
}  
String.prototype.last = string_last;  
var myString = new String("every good boy does fine");  
document.write(myString.last());  
  
// Output:  
// e  
```  
  
 Tüm iç [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneler sahip bir `prototype` salt okunur özellik. Özellikleri ve yöntemleri için prototip eklenebilir, ancak nesne farklı bir prototip atanmamış olabilir. Ancak, kullanıcı tanımlı nesneler, yeni bir prototip atanabilir.  
  
 Bu dil başvurusu iç her nesne için yöntem ve özellik listeleri hangilerinin nesnenin prototip parçası olan ve olmayan gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]