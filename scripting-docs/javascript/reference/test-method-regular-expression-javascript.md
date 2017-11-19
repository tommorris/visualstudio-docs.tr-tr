---
title: "test yöntemi (normal ifade) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: test
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: test method
ms.assetid: 4f4b6e39-cb1a-4be9-a66f-7b846075580d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53e2d2c23821cba5149367c7b5a735fa471bf581
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="test-method-regular-expression-javascript"></a>test Yöntemi (Normal İfade) (JavaScript)
Bir desen Aranan dizesinde var olup olmadığını gösteren bir Boole değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
rgExp.test(str)   
```  
  
## <a name="parameters"></a>Parametreler  
 `rgExp`  
 Gerekli. Örneği bir **normal ifade** normal ifade deseni ve geçerli bayrakları içeren nesne.  
  
 `str`  
 Gerekli. Arama gerçekleştirileceği dizesi.  
  
## <a name="remarks"></a>Açıklamalar  
 **Test** yöntemi denetler bir desen dizesi içinde var ve döndürür olmadığını **true** Öyleyse ve **false** Aksi takdirde.  
  
 Genel özelliklerini `RegExp` nesnesi tarafından değiştirilmez **test** yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **test** yöntemi. Bu örneği kullanmak için bir normal ifade deseni ve bir dize işlevi geçirin. İşlev dizesindeki normal ifade deseni geçtiği test ve arama sonuçlarını gösteren bir dize döndürür:  
  
```JavaScript  
function TestDemo(re, teststring)  
{  
   // Test string for existence of regular expression.  
   var found = re.test(teststring)  
  
   // Format the output.  
   var s = "";  
   s += "'" + teststring + "'"  
  
   if (found)  
      s += " contains ";  
   else  
      s += " does not contain ";  
  
   s += "'" + re.source + "'"  
   return(s);  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RegExp nesnesi](../../javascript/reference/regexp-object-javascript.md)   
 [Normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)