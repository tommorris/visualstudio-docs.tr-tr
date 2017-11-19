---
title: if... else deyimi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- else_JavaScriptKeyword
- if_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- if statement, if...else
- loop structures, if...else statements
ms.assetid: dfbe86e8-9c1e-4ef5-bb9c-7d1db7ce2506
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fad12b970f69a15040acb59195f957a2a6eec3e0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="ifelse-statement-javascript"></a>if...else Deyimi (JavaScript)
İfadenin değerine bağlı olarak bir deyim grubunu koşullu yürütür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
if (condition1) {  
    statement1  
}  
[else if (condition2) {  
    statement2  
}]  
[else {  
    statement3]   
}]  
```  
  
## <a name="parameters"></a>Parametreler  
 `condition1`  
 Gerekli. Boole ifadesi. Varsa `condition1` olan `null` veya `undefined`, `condition1` olarak işlem görür `false`.  
  
 `statement1`  
 İsteğe bağlı. Deyim, yürütülecek `condition1` olan **doğru**. Bileşik deyim olabilir.  
  
 `condition2`  
 Değerlendirilecek koşulu.  
  
 `statement2`  
 İsteğe bağlı. Deyim, yürütülecek `condition2` olan `true`. Bileşik deyim olabilir.  
  
 `statement3`  
 Her iki `condition1` ve `condition2` olan `false`, bu deyimi yürütülür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `if`, `if else`, ve `else`.  
  
 İçine iyi bir uygulamadır `statement1` ve `statement2` kaşlı ayraçlar daha anlaşılır olması ve yanlışlıkla hatalarını önlemek için de.  
  
```JavaScript  
var z = 3;  
if (x == 5) {  
    z = 10;  
}  
else if (x == 10) {  
    z = 15;  
}  
else {  
    z = 20;  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koşullu (üçlü) işleç (?:)](../../javascript/reference/conditional-ternary-operator-decrement-javascript.md)