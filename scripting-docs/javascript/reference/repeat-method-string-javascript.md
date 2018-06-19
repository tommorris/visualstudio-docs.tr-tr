---
title: repeat yöntemi (dize) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: fe02cdfd-f0f6-45a2-ad36-31c4300ef142
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1a3d6edce877a97b0e46a69c43b667231c26981
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791123"
---
# <a name="repeat-method-string-javascript"></a>repeat Yöntemi (Dize) (JavaScript)
Özgün dizeye eşit değerde olan yeni bir dize nesnesi belirtilen sayıda yinelenen döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
stringObj.repeat(count);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. Dize nesnesi.  
  
 `count`  
 Gerekli. Döndürülen dize özgün dizesinde tekrarlanacağı sayısı.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Bağımsız değişken negatif değer varsa ve yalnızca bu yöntem bir RangeError döndürürse veya + sonsuzluk.  
  
## <a name="remarks"></a>Açıklamalar  
 `repeat` Yöntemi, yeni bir dize olarak belirtilen sayıda özgün dizeyi art arda ekler `count`.  
  
 Bu yöntem bir hata döndürürse `count` pozitif bir sayı değil değerinden `Infinity`.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
"abc".repeat(3); // Returns "abcabcabc"  
"abc".repeat(0); // Returns an empty string.  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]