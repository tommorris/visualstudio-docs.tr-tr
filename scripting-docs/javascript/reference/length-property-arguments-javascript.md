---
title: length özelliği (bağımsız değişkenler) (JavaScript) | Microsoft Docs
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
- length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- length property (arguments)
- Length property
ms.assetid: 3cf36823-15bc-489b-a951-24c4923d9dba
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cede75a91244442f5f28ec9f71b7128814bed5d2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790883"
---
# <a name="length-property-arguments-javascript"></a>length Özelliği (bağımsız değişkenler) (JavaScript)
Gerçek bir işleve çağıran tarafından geçirilen bağımsız değişken sayısı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[function.]arguments.length  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı *işlevi* şu anda yürütülmekte olan adı olmayan bağımsız değişken `Function` nesnesi.  
  
 **Uzunluğu** özelliği **bağımsız değişkenleri** nesne gerçek geçirilen bağımsız değişken sayısı için komut dosyası altyapısı tarafından başlatılır bir `Function` yürütme Bu işlevde başladığında nesne.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **uzunluğu** özelliği **bağımsız değişkenleri** nesnesi. Örnek tam olarak anlamak için beklenen 2 bağımsız işlevi için daha fazla bağımsız değişken geçirin:  
  
```JavaScript  
function ArgTest(a, b){  
   var s = "";  
  
   s += "Expected Arguments: " + ArgTest.length;  
   s += "<br />";  
   s += "Passed Arguments: " + arguments.length;  
  
   document.write (s);  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı**: [arguments nesnesi](../../javascript/reference/arguments-object-javascript.md)&#124; [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [arguments özelliği (işlev)](../../javascript/reference/arguments-property-function-javascript.md)   
 [length özelliği (dizi)](../../javascript/reference/length-property-array-javascript.md)   
 [length özelliği (dize)](../../javascript/reference/length-property-string-javascript.md)