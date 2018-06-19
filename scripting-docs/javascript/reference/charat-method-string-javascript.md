---
title: charAt yöntemi (dize) (JavaScript) | Microsoft Docs
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
- charAt
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- String object, returning characters
- charAt method
- characters, returning part of
ms.assetid: 63173e15-17f6-47c5-8f94-98ef1eb04c1a
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 201d85fec4ba184f0842c7401d986650b9ee078c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789128"
---
# <a name="charat-method-string-javascript"></a>charAt Yöntemi (Dize) (JavaScript)
Belirtilen dizindeki karakteri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
strObj. charAt(index)  
```  
  
## <a name="parameters"></a>Parametreler  
 `strObj`  
 Gerekli. Tüm `String` nesne veya dize sabit değeri.  
  
 `index`  
 Gerekli. İstenen karakter sıfır tabanlı dizini.  
  
## <a name="remarks"></a>Açıklamalar  
 `charAt` Yöntemi karakter değeri belirtilen karaktere eşit döndürür `index`. Bir dizedeki ilk karakter 0 dizininde, ikincisi dizin 1 ve benzeri. Değerleri `index` olan aralık dışında dönüş boş bir dize.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `charAt` yöntemi:  
  
```JavaScript  
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";  
document.write(str.charAt(str.length - 1));  
  
// Output: Z  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)