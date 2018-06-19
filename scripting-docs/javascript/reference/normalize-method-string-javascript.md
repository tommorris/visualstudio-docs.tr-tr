---
title: Yöntemi (dize) (JavaScript) normalleştirin | Microsoft Docs
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
ms.assetid: d50077c1-b5fa-4e7a-9c9d-dc66cfc423ac
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aece38339ea1ce8924f404938b2d35d07504d539
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791132"
---
# <a name="normalize-method-string-javascript"></a>normalleştirme yöntemi (dize) (JavaScript)
Belirtilen dize Unicode normalleştirme biçiminde döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
stringObj.normalize([form]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. Sınanacak dize nesnesi.  
  
 `form`  
 İsteğe bağlı. Unicode normalleştirme Form değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dize Unicode normalleştirme biçimidir.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `form` desteklenmeyen bir değer olan bir `RangeError` oluşturulur.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `stringObj` bir dize değil dize Unicode normalleştirme formunu döndürmek yöntemin çalışmadan önce bir dizeye dönüştürülür.  
  
 `form`Unicode normalleştirme Form değer "NFC", "NFD", "NFKC" veya "NFKD" için belirtilen değerlere karşılık gelen olması gereken [Unicode standart eki #15](http://www.unicode.org/reports/tr15/). Varsayılan değer olan `form` "NFC" değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod kullanımını örnekler `normalize` yöntemi.  
  
```JavaScript  
// ANGSTORM SIGN and LATIN CAPITAL A WITH RING ABOVE is canonically equivalent  
"\u212b".normalize("NFC") === "\u00c5";  
  
// Decomposed, ANGSTOM SIGN is LATIN CAPITAL A followed by COMBINING RING ABOVE  
"\u212b".normalize("NFD") === "\u0041\u030a"  
  
// Normalization Form C will combine the result back into the precombined character  
"\u0041\u030a".normalize("NFC") === "\u00c5"  
  
// LATIN SMALL LIGATURE FI is compatibility equivalent with LATIN SMALL LETTER F followed by  
// LATIN SMALL LETTER I.  
"\ufb01".normalize("NFKD") === "fi";  
  
// Same mapping in NFKC  
"\ufb01".normalize("NFKC") === "fi";  
  
// NFKC will not recombine compatibility characters.  
"fi".normalize("NFKC") === "fi";  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]