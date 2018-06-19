---
title: callee özelliği (bağımsız değişkenler) (JavaScript) | Microsoft Docs
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
- callee
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- callee property
ms.assetid: ad9d4d21-73f0-44f6-8bec-502f3456cd23
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33f1c2926d76c0a1f088c8f4222b6f24c004b73b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789098"
---
# <a name="callee-property-arguments-javascript"></a>callee Özelliği (bağımsız değişkenler) (JavaScript)
Döndürür `Function` yürütülmekte olan nesne başka bir deyişle, gövde metni belirtilen `Function` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[function.]arguments.callee  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı *işlevi* şu anda yürütülmekte olan adı olmayan bağımsız değişken `Function` nesnesi.  
  
 `callee` Özelliği üyesi olduğu **bağımsız değişkenleri** ilişkili işlevi yalnızca zaman yürütüyor kullanılabilir nesne.  
  
 Başlangıç değeri `callee` özelliği `Function` yürütülmekte olan nesne. Bu özyinelemeli olarak anonim işlevler sağlar.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
function factorial(n){  
  if (n <= 0)  
     return 1;  
  else  
     return n * arguments.callee(n - 1)  
}  
document.write(factorial(4));  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı**: [arguments nesnesi](../../javascript/reference/arguments-object-javascript.md)&#124; [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [caller özelliği (işlev)](../../javascript/reference/caller-property-function-javascript.md)