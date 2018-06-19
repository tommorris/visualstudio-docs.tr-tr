---
title: substring yöntemi (dize) (JavaScript) | Microsoft Docs
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
- substring
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- substrings
- substring method
ms.assetid: 9cf9a005-cbe3-42fd-828b-57a39f54224c
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 15ebaadc7b24fa97f531a22f6deb1453ff52b3e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791792"
---
# <a name="substring-method-string-javascript"></a>substring Yöntemi (Dize) (JavaScript)
İçinde belirtilen konumda alt dizeyi döndürür bir `String` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      strVariable. substring(start [, end])  
"String Literal".substring(start [, end])   
```  
  
## <a name="parameters"></a>Parametreler  
 `start`  
 Gerekli. Alt dizenin başlangıcını gösteren sıfır tabanlı dizin tamsayı.  
  
 `end`  
 İsteğe bağlı. Alt dizeyi sonuna gösteren sıfır tabanlı dizin tamsayı. Alt dizeyi en fazla karakter içerir, ancak tarafından karakteri belirtilen dahil değil, `end`.  
  
 Varsa `end` atlanırsa, karakterlerinden `start` özgün dizeye ucu aracılığıyla döndürülür.  
  
## <a name="remarks"></a>Açıklamalar  
 `substring` Yöntemi alt dizeyi içeren dizeyi döndürür `start` kadar ancak dahil değil, `end`.  
  
 **Substring** yöntemi alt değerini kullanır `start` ve `end` alt dizeyi, başlangıç noktası olarak. Örneğin, strvar.substring (0, 3 **)** ve strvar.substring (3, 0), aynı alt dizeyi döndürür.  
  
 Her iki `start` veya `end` olan `NaN` veya negatif, sıfır ile değiştirilir.  
  
 Alt dizenin uzunluğunu arasındaki farkı mutlak değerini eşittir `start` ve `end`. Örneğin, alt dizenin uzunluğunu strvar.substring (0, 3) döndürülür ve üç (3, 0) strvar.substring değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **substring** yöntemi.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.substring(10, 15);  
document.write(ss);  
  
// Output:  
// brown  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [substr yöntemi (dize)](../../javascript/reference/substr-method-string-javascript.md)