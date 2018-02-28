---
title: "Eval işlevi (JavaScript) | Microsoft Docs"
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
- eval
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- eval function
- parsing, code
- parser
ms.assetid: 85587e39-9325-4b75-b9f9-9d7d475a2120
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 388e486f58bb70fd192701060a5faefaed8bd98e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="eval-function-javascript"></a>eval İşlevi (JavaScript)
Hesaplar [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kod ve yürütür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
eval(codeString)   
```  
  
## <a name="parameters"></a>Parametreler  
 `codeString`  
 Gerekli. A `String` geçerli içeren değer [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 `eval` İşlevi sağlayan dinamik yürütülmesi [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kaynak kodu.  
  
 `codeString` Dizesi tarafından ayrıştırılır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] Ayrıştırıcı ve yürütülür.  
  
 Kod geçirilen `eval` işlev çağrısı aynı bağlamda yürütüldüğünde `eval` işlevi.  
  
 Mümkün olduğunda kullanın [JSON.parse işlevi](../../javascript/reference/json-parse-function-javascript.md) JavaScript nesne gösterimi (JSON) metin seri durumdan için. `JSON.parse` İşlevi daha güvenli ve daha hızlı çalıştırır daha `eval` işlevi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod değişkenini `myDate` test tarih.  
  
```JavaScript  
var dateFn = "Date(1971,3,8)";  
var myDate;  
eval("myDate = new " + dateFn + ";");  
  
document.write(myDate);  
  
// Output: Thu Apr 8 00:00:00 PDT 1971  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [genel nesne](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)