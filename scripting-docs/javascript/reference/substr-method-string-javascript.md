---
title: "substr yöntemi (dize) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: substr
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: substr method
ms.assetid: f12541c1-2623-482e-941d-2e22bc3c4a4a
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b002bfefbeb81c534c882fa4a4720c93ccca185
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="substr-method-string-javascript"></a>substr Yöntemi (Dize) (JavaScript)
Belirtilen konumda başlayan ve belirtilen uzunluğa sahip bir alt dizeyi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringvar.substr(start [, length ])   
```  
  
## <a name="parameters"></a>Parametreler  
 `stringvar`  
 Gerekli. Bir dize veya `String` nesne alt dizenin ayıklanacağı gelen.  
  
 `start`  
 Gerekli. İstenen alt dizeyi başlangıç konumu. Dizedeki ilk karakter dizinini sıfır olur.  
  
 `length`  
 İsteğe bağlı. Döndürülen alt dizeyi içerecek şekilde karakter sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `length` sıfır veya negatif, boş bir dize döndürülür. Belirtilmezse, alt dizeyi sonuna kadar devam `stringvar`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `substr` yöntemi.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.substr(10, 5);    
document.write("[" + ss + "] <br>");  
  
ss = s.substr(10);  
document.write("[" + ss + "] <br>");  
  
ss = s.substr(10, -5);  
document.write("[" + ss + "] <br>");  
  
// Output:  
// [brown]   
// [brown fox jumps over the lazy dog.]   
// []  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [substring yöntemi (dize)](../../javascript/reference/substring-method-string-javascript.md)