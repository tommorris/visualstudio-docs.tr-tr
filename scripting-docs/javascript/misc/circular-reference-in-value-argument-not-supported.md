---
title: "Desteklenmeyen değer bağımsız değişkeninde döngüsel başvuru | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5034
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d06f0fa-86f5-49d1-8d50-af1759990f43
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d25489065ceece41108a75c9d3763a95e4adb924
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="circular-reference-in-value-argument-not-supported"></a>Değer bağımsız değişkeninde döngüsel başvuru desteklenmez
Çağırmak için bir girişimde bulunuldu `JSON.stringify` geçersiz bir değere sahip. `value` Bağımsız değişkeni, bir dizi veya nesne, döngüsel başvuru içeriyor.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Döngüsel başvuru bağımsız değişkende kaldırın.  
  
## <a name="example"></a>Örnek  
 Bu örnek kodda bir çalışma zamanı hatası neden olur `john` başvuruyor `mary` ve `mary` başvuruyor `john`. Döngüsel başvuru kaldırmak için aşağıdakilerden birini kaldırın veya unset özelliği `brother` gelen `mary` nesne veya `sister` özelliğinden `john` nesnesi.  
  
```JavaScript  
var john = new Object();  
var mary = new Object();  
john.sister = mary;  
mary.brother = john;  
  
// This line causes a runtime error.  
var error = JSON.stringify(john);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JSON nesnesi](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse işlevi](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript çalışma zamanı hataları](../../javascript/reference/javascript-run-time-errors.md)