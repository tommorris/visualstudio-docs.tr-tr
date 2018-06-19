---
title: switch deyimi (JavaScript) | Microsoft Docs
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
- switch_JavaScriptKeyword
- default_JavaScriptKeyword
- case_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- switch statement
ms.assetid: 61f80e8b-3739-4146-a893-c2832d92b28c
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a301fc8bcc72b48c6ba8e999c0ebb70fe9d92b41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791906"
---
# <a name="switch-statement-javascript"></a>switch Deyimi (JavaScript)
Belirtilen ifadenin değeri bir etiket eşleştiğinde bir veya daha fazla deyimleri yürütülmesini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
switch (expression) {  
    case label :  
        statementlist  
    case label :  
    default :  
        statementlist  
}   
```  
  
## <a name="parameters"></a>Parametreler  
 `expression`  
 Değerlendirilecek ifade.  
  
 `label`  
 Eşleştirme yapılacak bir tanımlayıcı `expression`. Varsa `label` olan bir `expression`, yürütme ile başlayan `statementlist` hemen sonra iki nokta üst üste ve ya da bulduğu kadar devam eder bir `break` isteğe bağlıdır, deyim ya da sonunda `switch` deyimi.  
  
 `statementlist`  
 Yürütülecek bir veya daha fazla deyim.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `default` yan tümcesi etiket hiçbiri eşleşen değerleri, yürütülecek bir deyim sağlamak için `expression`. İçinde herhangi bir yerde görünebilir `switch` kod bloğu.  
  
 Sıfır veya daha fazla `label` blokları belirtilebilir. Öyle değilse `label` değeri ile eşleşen `expression`ve bir `default` durumda sağlanmadı, hiçbir deyimleri yürütülür.  
  
 Yürütme akar aracılığıyla bir `switch` deyimi aşağıdaki gibi:  
  
-   Değerlendirme `expression` ve bakmak `label` bir eşleşme bulunana kadar sırayla.  
  
-   Varsa bir `label` değerine eşittir `expression`, kendi eşlik eden yürütme `statementlist`.  
  
     Yürütme kadar devam bir `break` deyimi karşılaştı, veya `switch` deyimi sona erer. Bu, birden çok anlamına gelir `label` blokları çalışıp çalışmadığını bir `break` deyimi kullanılmaz.  
  
-   Öyle değilse `label` eşittir `expression`gidin `default` durumda. Varsa hiçbir `default` durumda, son adıma geçin.  
  
-   Sonuna aşağıdaki ifadesine yürütme devam `switch` kod bloğu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne türü için sınar.  
  
```JavaScript  
function MyObjectType(obj) {  
    switch (obj.constructor) {  
        case Date:  
            document.write("Object is a Date.");  
            break;  
        case Number:  
            document.write("Object is a Number.");  
            break;  
        case String:  
            document.write("Object is a String.");  
            break;  
        default:  
            document.write("Object is unknown.");  
    }  
}  
  
// Output when obj is a Date:  
// Object is a Date.  
  
// Output when obj is a Number:  
// Object is a Number.  
  
// Output when obj is a String:  
// Object is a String.  
  
// Output when obj is something other than a Date, Number, or String:  
// Object is unknown.  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod kullanmıyorsanız, ne olacağını gösterir bir `break` deyimi.  
  
```JavaScript  
function MyObjectType(obj) {  
    switch (obj.constructor) {  
        case Date:  
            document.write("Object is a Date.");  
        case Number:  
            document.write("Object is a Number.");  
        case String:  
            document.write("Object is a String.");  
        default:  
            document.write("Object is unknown.");  
    }  
}  
  
// Output when obj is a Date:  
// Object is a Date.Object is a Number.Object is a String.Object is unknown.  
  
// Output when obj is a Number:  
// Object is a Number.Object is a String.Object is unknown.  
  
// Output when obj is a String:  
// Object is a String.Object is unknown.  
  
// Output when obj is something other than a Date, Number, or String:  
// Object is unknown.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [break deyimi](../../javascript/reference/break-statement-javascript.md)   
 [if... else deyimi](../../javascript/reference/if-dot-dot-dot-else-statement-javascript.md)