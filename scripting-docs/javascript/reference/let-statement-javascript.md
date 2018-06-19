---
title: let deyimi (JavaScript) | Microsoft Docs
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
- let_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- let statement
- declaring variables, let statement
ms.assetid: c7e4f8a9-8f54-47b6-aed2-956959c1ecfd
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c447a1bf0c430771ff146965a592f7e160e2055b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791177"
---
# <a name="let-statement-javascript"></a>let Deyimi (JavaScript)
Blok kapsamlı bir değişken bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
let variable1 = value1  
```  
  
#### <a name="parameters"></a>Parametreler  
 `variable1`  
 Bildirilen değişkeninin adı.  
  
 `value1`  
 Değişkenine atanan başlangıç değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `let` kapsamını bloğuna kısıtlı bir değişken bildirmek için deyimi, bildirildiği içinde. Bunları bildirirken değişkenleri veya daha sonra kodunuzu değerler atayabilirsiniz.  
  
 Bir değişken kullanarak bildirilen `let` kullanılamaz önce bildiriminden ya da hatayla sonuçlanır.  
  
 Değişken başlatmazsanız `let` deyimi, otomatik olarak atandı [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] değeri `undefined`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `let` deyimi.  
  
```JavaScript  
var  l = 10;  
{  
    let l = 2;  
   // At this point, l = 2.  
}  
// At this point, l = 10.  
  
// Additional ways to declare a variable using let.  
let index;  
let name = "Thomas Jefferson";  
let answer = 42, counter, numpages = 10;  
let myarray = new Array();  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [const deyimi](../../javascript/reference/const-statement-javascript.md)   
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)   
 [Değişkenleri](../../javascript/variables-javascript.md)