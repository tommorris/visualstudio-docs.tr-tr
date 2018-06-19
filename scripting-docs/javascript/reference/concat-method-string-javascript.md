---
title: concat yöntemi (dize) (JavaScript) | Microsoft Docs
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
- concat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- concat method (String)
- Concat method
ms.assetid: 5d28ebb2-d534-4179-9297-a4c821ee9f24
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b6419cc6404e06fc780802a30a3b4add8320881
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789074"
---
# <a name="concat-method-string-javascript"></a>concat Yöntemi (Dize) (JavaScript)
İki veya daha fazla birleşimini içeren bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
string1. concat([string2[, string3[, . . . [, stringN]]]])  
```  
  
## <a name="parameters"></a>Parametreler  
 `string1`  
 Gerekli. `String` Nesne veya olduğu diğer tüm değişmez dize değeri belirtilen dizeleri art arda eklenmiş.  
  
 `string2,. . ., stringN`  
 İsteğe bağlı. Dizelerin sonuna `string1`.  
  
## <a name="remarks"></a>Açıklamalar  
 Sonucu `concat` yöntemi eşdeğerdir: `result`  =  `string1`  +  `string2`  +  `string3`  +  `stringN`. Bir kaynak veya sonucu dize değerinin bir değişiklik bir dize değeri etkilemez. Bağımsız değişkenlerden biri dizeleri değilse, bunlar ilk dizeleri için birleştirilmiş önce dönüştürülür `string1`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `concat` bir dizeyle kullanıldığında yöntemi:  
  
```JavaScript  
var str1 = "ABCD"  
var str2 = "EFGH";  
var str3 = "1234";  
var str4 = "5678";  
document.write(str1.concat(str2, str3, str4));  
  
// Output: "ABCDEFGH12345678"  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Toplama işleci (+)](../../javascript/reference/addition-operator-decrement-javascript.md)