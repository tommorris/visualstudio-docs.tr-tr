---
title: var deyimi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- var_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- declaring variables, var statement
- var statement
ms.assetid: 56f900af-a5c4-4667-9664-5956d30f0aae
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 839b6904fa59b6f4ea9a5c4d8e00213cd351517a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="var-statement-javascript"></a>var Deyimi (JavaScript)
Değişken bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
var variable1 = value1  
```  
  
## <a name="parameters"></a>Parametreler  
 `variable1`  
 Bildirilen değişkeninin adı.  
  
 `value1`  
 Değişkenine atanan başlangıç değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `var` deyimi değişkenleri bildirin. Bunları bildirirken değişkenleri veya daha sonra kodunuzu değerler atayabilirsiniz.  
  
 Bir değişken ilk kez bildirilmiş komut dosyanıza görüntülenir.  
  
 Bir değişken kullanmadan bildirebilir `var` anahtar sözcüğü ve bir değere atayın. Bu olarak bilinen bir *örtük bildirimi*, ve önerilmez. Değişken genel kapsam örtük bir bildirim sağlar. Yordam düzeyinde bir değişkeni bildirirken rağmen genellikle genel kapsama sahip istediğiniz değil. Değişken genel kapsam vermekten kaçının için kullanmanız gerekir `var` değişken bildirimi anahtar sözcük.  
  
 Değişken başlatmazsanız `var` deyimi, otomatik olarak atandı [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] değeri `undefined`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler kullanımını göstermek `var` deyimi.  
  
```JavaScript  
var index;  
var name = "Thomas Jefferson";  
var answer = 42, counter, numpages = 10;  
var myarray = new Array();  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Function deyimi](../../javascript/reference/function-statement-javascript.md)   
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)   
 [Değişkenleri](../../javascript/variables-javascript.md)