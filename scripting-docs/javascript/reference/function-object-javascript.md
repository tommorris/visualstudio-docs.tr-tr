---
title: İşlev nesnesi (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- function
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Function object
ms.assetid: d3834767-203c-475e-848c-95c423ba15b6
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4392fd57967e6312c96af50bdff2415d0f2dcd4d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790721"
---
# <a name="function-object-javascript"></a>İşlev Nesnesi (JavaScript)
Yeni bir işlev oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
function functionName([argname1  [, ...[, argnameN]]])  
{  
   body  
}  
```  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
functionName = new Function( [argname1,  [... argnameN,]] body );  
```  
  
## <a name="parameters"></a>Parametreler  
 `functionName`  
 Gerekli. Yeni oluşturulan işlevin adı  
  
 `argname1...argnameN`  
 İsteğe bağlı. İşlev kabul bağımsız değişkenler listesi.  
  
 `body`  
 İsteğe bağlı. Bloğunu içeren bir dize [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] işlevi çağrıldığında yürütülecek kod.  
  
## <a name="remarks"></a>Açıklamalar  
 İşlev temel veri türüdür [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Sözdizimi 1, bir işlev değer oluşturur [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dönüştüren bir `Function` nesne gerekli olduğunda. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]dönüştürür `Function` Sözdizimi 2 ile işlevi değerlere zamanında oluşturulan nesneler işlevi çağrılır.  
  
 Sözdizimi 1 yoludur yeni işlevler oluşturmak için standart [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Sözdizimi 2 işlev nesneleri açıkça oluşturmak için kullanılan alternatif bir biçimidir.  
  
 Örneğin, kendisine geçirilen iki bağımsız değişken ekleyen bir işlev bildirmek için bunu iki yoldan biriyle yapabilirsiniz:  
  
## <a name="example-1"></a>Örnek 1  
  
```JavaScript  
function add(x, y)  
{  
   return(x + y);  
}  
```  
  
## <a name="example-2"></a>Örnek 2  
  
```  
var add = function(x, y) {  
     return(x+y);  
}  
```  
  
 Her iki durumda da, bir kod satırı işleviyle aşağıdakine benzer da arayın:  
  
```JavaScript  
add(2, 3);  
```  
  
> [!NOTE]
>  Bir işlev çağırdığınızda, her zaman parantez ve gerekli herhangi bir bağımsız değişken eklediğinizden emin olun. Parantez olmadan bir işlevi çağırmak işlevi kendisi, işlevin dönüş değeri yerine döndürülecek neden olur.  
  
## <a name="properties"></a>Özellikler  
 [0... n özellikleri](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md) &#124;[ arguments özelliği](../../javascript/reference/arguments-property-function-javascript.md) &#124; [callee özelliği](../../javascript/reference/callee-property-arguments-javascript.md) &#124; [caller özelliği](../../javascript/reference/caller-property-function-javascript.md) &#124; [constructor özelliği](../../javascript/reference/constructor-property-object-javascript.md) &#124; [length özelliği (işlev)](../../javascript/reference/length-property-function-javascript.md) &#124; [prototype özelliği](../../javascript/reference/prototype-property-object-javascript.md)  
  
## <a name="methods"></a>Yöntemler  
 [apply yöntemi](../../javascript/reference/apply-method-function-javascript.md) &#124; [bağlama yöntemini](../../javascript/reference/bind-method-function-javascript.md) &#124; [yöntemini çağırın](../../javascript/reference/call-method-function-javascript.md) &#124; [toString yöntemi](../../javascript/reference/tostring-method-object-javascript.md) &#124; [valueOf yöntemi](../../javascript/reference/valueof-method-object-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Function deyimi](../../javascript/reference/function-statement-javascript.md)   
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)   
 [var deyimi](../../javascript/reference/var-statement-javascript.md)