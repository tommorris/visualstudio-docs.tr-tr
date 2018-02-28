---
title: "compile yöntemi (normal ifade) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- compile
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- regular expressions, compiling
- Compile method
- compiling source code, regular expressions
ms.assetid: dc28cae3-478d-49b5-b5ea-203e5edfe195
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b8de23a9e4f0e03fbf042195867ad9426e4c6bb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="compile-method-regular-expression-javascript"></a>compile Yöntemi (Normal İfade) (JavaScript)
Daha hızlı yürütmek için dahili bir biçime normal bir ifade derler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
rgExp.compile(pattern, [flags])   
```  
  
## <a name="parameters"></a>Parametreler  
 `rgExp`  
 Gerekli. Örneği bir **normal ifade** nesnesi. Bir değişken adı veya bir hazır değer olabilir.  
  
 *düzeni*  
 Gerekli. Derlenecek bir normal ifade deseni içeren dize ifadesi  
  
 `flags`  
 İsteğe bağlı. Birleştirilebilir, kullanılabilir bayraklar şunlardır:  
  
-   g (tüm oluşumları için genel arama *düzeni*)  
  
-   t (servis talebi yoksay)  
  
-   m (çok satırlı arama)  
  
## <a name="remarks"></a>Açıklamalar  
 **Derleme** yöntemi dönüştürür *düzeni* daha hızlı yürütmek için dahili bir biçime. Bu döngü, normal ifadelerde daha verimli şekilde kullanılmasına örneğin sağlar. Derlenmiş bir normal ifade şeyleri aynı ifadeye sürekli olarak yeniden zaman hızlandırır. Bununla birlikte, normal ifade değişirse avantajlı kazanılan.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **derleme** yöntemi:  
  
```JavaScript  
function CompileDemo(){  
   var rs;  
   var s = "AaBbCcDdEeFfGgHhIiJjKkLlMmNnOoPp"  
   // Create regular expression for uppercase only.  
   var r = new RegExp("[A-Z]", "g");  
   var a1 = s.match(r)              // Find matches.  
   // Compile the regular expression for lowercase only.  
   r.compile("[a-z]", "g");  
// Find matches.  
   var a2 = s.match(r)                
   return(a1 + "\n" + a2);  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)