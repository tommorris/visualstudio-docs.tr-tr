---
title: Bu deyimi (JavaScript) | Microsoft Docs
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
- this_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- this statement
- constructors, referring to current object
ms.assetid: 8510a00b-2f14-4700-a276-4d9a523c5112
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4afed1bd978d1985c151efa77873c93e699f0b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791606"
---
# <a name="this-statement-javascript"></a>this Deyimi (JavaScript)
Geçerli nesneye başvurur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
this.property  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `property` bağımsız değişkeni geçerli nesnenin özelliklerini biridir  
  
 `this` Anahtar sözcüğü geçerli nesneye başvurmak için nesne oluşturucular içinde kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, **bu** yeni oluşturulan araba nesnesine başvuruyor ve üç özellik değerleri atar:  
  
```JavaScript  
function Car(color, make, model){  
   this.color = color;  
   this.make = make;  
   this.model = model;  
}  
```  
  
 **Bu** anahtar sözcüğü genellikle başvurduğu **penceresi** herhangi bir nesne kapsam dışında kullanılan nesne. Ancak, olay işleyicileri içinde `this` olayı DOM öğesine başvuruyor.  
  
 Aşağıdaki kodda (Internet Explorer 9 ve sonrası için), olay işleyici "clicker" kimlikli bir düğmenin dize halini bastırır.  
  
```JavaScript  
document.getElementById("clicker").addEventListener("click", eventHandler, false);  
  
        function eventHandler(ev) {  
            document.write(this.toString());  
        }  
  
// Output (when you click the button): [object HTMLButtonElement]  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Bağlama yöntemini kullanma](../../javascript/advanced/using-the-bind-method-javascript.md)