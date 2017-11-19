---
title: "arguments özelliği (işlev) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: arguments
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arguments, arguments property
- Arguments property
ms.assetid: efc7a1ee-0880-4f05-b0f2-808f31a4af1d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b0b18fb8164639119e5db5e7a5d76b4280f9c9d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="arguments-property-function-javascript"></a>arguments Özelliği (İşlev) (JavaScript)
Şu anda yürütülmekte olan bağımsız değişkenleri alır `Function` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
function.arguments  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `function` Bağımsız değişkeni şu anda yürütülen işlevin adını ve bir atlanabilir.  
  
 Bu özellik değişken sayıda bağımsız değişken işlemek için bir işlev sağlar. **Uzunluğu** özelliği `arguments` nesnesini içeren işlevine geçirilen bağımsız değişken sayısı. İçinde yer alan bireysel değişkenleri `arguments` nesne dizi öğeleri erişilir aynı şekilde erişilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `arguments` özelliği:  
  
```JavaScript  
function ArgTest(arg1, arg2){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello"));  
  
//Output: function ArgTest(arg1, arg2){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello"));  
  
// Output: The individual arguments are: 1 2 hello  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [arguments nesnesi](../../javascript/reference/arguments-object-javascript.md)   
 [Function deyimi](../../javascript/reference/function-statement-javascript.md)