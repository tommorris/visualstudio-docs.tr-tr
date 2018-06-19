---
title: RegExp nesnesi (JavaScript) | Microsoft Docs
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
- RegExp
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- RegExp object, overview
- RegExp object
ms.assetid: 7f6b1073-8cbb-49ed-94b6-56833ba663c5
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7319e4556721bcfd397061ce525acfb3278c6b9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791747"
---
# <a name="regexp-object-javascript"></a>RegExp Nesnesi (JavaScript)
Normal ifade deseni sonuçlarıyla ilgili bilgileri depolayan bir iç global nesne eşleşir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
RegExp.property   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli *özelliği* bağımsız değişkeni, aşağıdakilerden biri olabilir `RegExp` nesne özellikleri.  
  
 `RegExp` Nesne doğrudan oluşturulamıyor, ancak her zaman kullanılabilir durumda. Başarılı normal ifade araması tamamlanana kadar çeşitli özelliklerini ilk değerlerini `RegExp` nesne aşağıdaki gibidir:  
  
|Özellik|Toplu|Başlangıç değeri|  
|--------------|---------------|-------------------|  
|dizin||-1|  
|giriş|$_|Boş bir dize.|  
|lastIndex||-1|  
|lastMatch|$&|Boş bir dize.|  
|lastParen|$+|Boş bir dize.|  
|leftContext|$`|Boş bir dize.|  
|rightContext|$'|Boş bir dize.|  
|$1 - $9|$1 - $9|Boş bir dize.|  
  
 Başarılı normal ifade araması tamamlanana kadar özelliklerini kendi değeri olarak tanımlanmamış.  
  
 Genel `RegExp` nesnesi ile karıştırılmamalıdır **normal ifade** nesnesi. Aynı şey gibi ses olsa bile, farklı ve ayrıdır. Genel özelliklerini `RegExp` nesne içeren her eşleşme hakkında sürekli güncel bilgi işlem sırasında özelliklerini gerçekleştiğinde gibi **normal ifade** nesne yalnızca oluşan eşleşme hakkında bilgiler içerir Bu örneği **normal ifade**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir normal ifade araması gerçekleştirir. Eşleşmeleri görüntüler ve genel submatches `RegExp` nesnesi tarafından döndürülen dizi gelen ve giden `exec` yöntemi.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
<a name="js56jsobjregexpprop"></a>   
## <a name="properties"></a>Özellikler  
 [$1... $9 özellikleri](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md) &#124; [index özelliği](../../javascript/reference/index-property-regexp-javascript.md) &#124; [input özelliği](../../javascript/reference/input-property-dollar-regexp-javascript.md) &#124; [lastIndex özelliği](../../javascript/reference/lastindex-property-regexp-javascript.md) &#124; [lastMatch özelliği](../../javascript/reference/lastmatch-property-dollar-regexp-javascript.md) &#124; [lastParen özelliği](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md) &#124; [leftContext özelliği](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md) &#124; [rightContext özelliği](../../javascript/reference/rightcontext-property-dollar-regexp-javascript.md)  
  
## <a name="methods"></a>Yöntemler  
 `RegExp` Nesnesi yöntemlerin hiçbiri sahiptir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)