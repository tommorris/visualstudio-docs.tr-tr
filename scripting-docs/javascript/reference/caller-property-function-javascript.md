---
title: "caller özelliği (işlev) (JavaScript) | Microsoft Docs"
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
- caller
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- caller property
- function calls, functions that are executing
ms.assetid: ae210853-7160-4102-9cfd-ab489f180ce1
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c6eef1b8304612c2ed16a4cc389bf3b2a28b70f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="caller-property-function-javascript"></a>caller Özelliği (İşlev) (JavaScript)
Geçerli işlevi çağrılan işlevi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
functionName.caller  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `functionName` İşlevi Yürütülüyor herhangi adını nesne.  
  
 `caller` Özelliği tanımlanmış işlevi yalnızca sırasında için işlevi yürütüyor. İşlev üstten düzeyini çağrılırsa bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] program `caller` içeren `null`.  
  
 Varsa `caller` özelliği bir dize bağlamında kullanılan, aynı sonucu `functionName`.`toString`, diğer bir deyişle, işlevin decompiled metin görüntülenir.  
  
 Aşağıdaki örnek kullanımını göstermektedir `caller` özelliği:  
  
```JavaScript  
function CallLevel(){  
   if (CallLevel.caller == null)  
      return("CallLevel was called from the top level.");  
   else  
      return("CallLevel was called by another function.");  
}  
  
document.write(CallLevel());  
  
// Output: CallLevel was called from the top level.  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Function deyimi](../../javascript/reference/function-statement-javascript.md)