---
title: prototype özelliği (hata) | Microsoft Docs
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
ms.assetid: 6c268a51-1a3d-4397-abf8-e54ca4e598fe
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7d0413d3541691a38672e7c0720b58245725b76
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791354"
---
# <a name="prototype-property-error"></a>prototype Özelliği (Hata)
Bir hata prototipi bir başvuru döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
error.prototype  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `error` Bağımsız değişkeni bir hata adıdır.  
  
 Kullanım `prototype` özelliği için bir hata işlevselliği temel kümesi sağlar. Bir nesnenin "Bu nesneye atanmış prototip davranışını devral" yeni örnekleri.  
  
 Örneğin, bir yöntem eklemek için `Error` dizisinin en büyük öğenin değerini döndürür nesne, işlev bildirme, ekleyin `Error.prototype`ve ardından onu kullanabilirsiniz.  
  
```JavaScript  
function getSeverity(){  
    if (this.number > 1000)  
        return "high";  
    else  
        return "low";  
}  
Error.prototype.getSev = getSeverity;  
var myError = new Error();  
myError.number = 5000;  
  
document.write(myError.getSev());   
  
// Output: high  
  
```  
  
 Tüm iç [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneler sahip bir `prototype` salt okunur özellik. Özellikleri ve yöntemleri için prototip eklenebilir, ancak nesne farklı bir prototip atanmamış olabilir. Ancak, kullanıcı tanımlı nesneler, yeni bir prototip atanabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]