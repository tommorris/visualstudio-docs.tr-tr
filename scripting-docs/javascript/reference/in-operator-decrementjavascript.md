---
title: "işlecinde (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: in_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: in operator
ms.assetid: dcd8f901-96b8-4c91-848b-b1ec0ab1c11c
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eefcd4c53d2e3366a26f0d8dfb099f59038507ae
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="in-operator-javascript"></a>in İşleci (JavaScript)
Testleri bir nesne özelliğinde varlığı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = property in object  
```  
  
## <a name="parameters"></a>Parametreler  
 `result`  
 Gerekli. Herhangi bir değişken.  
  
 `property`  
 Gerekli. Bir dize ifadesi değerlendiren bir ifade.  
  
 `object`  
 Gerekli. Herhangi bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 `in` İşleci belirleyen bir nesne adında bir özelliğe sahip olup olmadığını `property`. Özelliğin nesnenin prototip zinciri parçası olup olmadığını belirler. Nesne prototipleri hakkında daha fazla bilgi için bkz: [prototipler ve prototip devralma](../../javascript/advanced/prototypes-and-prototype-inheritance.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `in` işleci:  
  
```JavaScript  
// Create an object that has some properties.  
var myObject = new Object();  
myObject.name = "James";  
myObject.age = "22";  
myObject.phone = "555 0234";  
  
if ("phone" in myObject)  
   document.write ("property is present");  
else  
   document.write ("property is not present");  
  
// Output: property is present  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)