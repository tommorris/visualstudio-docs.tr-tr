---
title: arguments nesnesi (JavaScript) | Microsoft Docs
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
- arguments
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arguments, arguments object
- arguments object
ms.assetid: 5eb79ca9-bbb8-4a42-aaf5-16a93ecb425f
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a5c526d19ad5469d9d099f51cc5a2e2d089814f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789170"
---
# <a name="arguments-object-javascript"></a>arguments Nesnesi (JavaScript)
Bağımsız değişken şu anda yürütülen işlevi ve adlı işlevleri temsil eden bir nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[function.]arguments[n]  
```  
  
## <a name="parameters"></a>Parametreler  
 *işlevi*  
 İsteğe bağlı. Şu anda yürütülmekte olan adı `Function` nesnesi.  
  
 *n*  
 Gerekli. Geçirilen bağımsız değişken değeri sıfır tabanlı dizini `Function` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Açıkça oluşturulamıyor bir **bağımsız değişkenleri** nesnesi. **Bağımsız değişkenleri** nesne yalnızca kullanılabilir bir işlev yürütme başladığında. **Bağımsız değişkenleri** işlevi nesnesinin bir dizi değildir, ancak dizi öğeleri erişilir aynı şekilde bireysel değişkenleri erişilir. Dizin  *n*  gerçekten birini başvurusudur **0**  ***n***  özelliklerini **bağımsız değişkenleri** nesnesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **bağımsız değişkenleri** nesnesi.  
  
```JavaScript  
function ArgTest(a, b)  
{  
   var s = "";  
  
   s += "Expected Arguments: " + ArgTest.length;  
   s += "<br />";  
   s += "Passed Arguments: " + arguments.length;  
   s += "<br />";  
  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++)  
   {  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
  
   document.write(s);  
}  
  
ArgTest(1, 2, "hello", new Date())  
  
// Output:  
// Expected Arguments: 2  
// Passed Arguments: 4  
// The individual arguments are: 1 2 hello Tues Jan 8 08:27:09 PST 20xx  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [0... n özellikleri (bağımsız değişkenler)](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md)   
 [callee özelliği (bağımsız değişkenler)](../../javascript/reference/callee-property-arguments-javascript.md)   
 [length özelliği (bağımsız değişkenler)](../../javascript/reference/length-property-arguments-javascript.md)