---
title: const deyimi (JavaScript) | Microsoft Docs
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
- const_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- declaring variables, const statement
- const statement
ms.assetid: 3ad0840f-437f-4163-9571-86ecc5ddb987
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 68130cec4f1b1fe89d2fe3e673b28963d79aebde
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789113"
---
# <a name="const-statement-javascript"></a>const Deyimi (JavaScript)
Blok kapsamlı bir değişkeni sabit bir değer ile bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const constant1 = value1  
```  
  
#### <a name="parameters"></a>Parametreler  
 `constant1`  
 Bildirilen değişkeninin adı.  
  
 `value1`  
 Değişkenine atanan başlangıç değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `const` kapsamını bloğuna kısıtlıdır sabit bir değere sahip bir değişken bildirmek için deyimi, bildirildiği içinde. Değişkenin değeri değiştirilemez.  
  
 Bir değişken kullanarak bildirilen `const` onu bildirilmişse başlatılması gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `const` deyimi.  
  
```JavaScript  
var c = 10;  
{  
    const c = 2;  
   // At this point, c = 2.  
}  
// At this point, c = 10.  
  
// Additional ways to declare a variable using const.  
const name = "Thomas Jefferson";  
const answer = 42, numpages = 10;  
const myarray = new Array();  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [let deyimi](../../javascript/reference/let-statement-javascript.md)   
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)   
 [Değişkenleri](../../javascript/variables-javascript.md)