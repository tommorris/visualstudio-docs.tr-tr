---
title: "slice yöntemi (dize) (JavaScript) | Microsoft Docs"
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
- slice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- strings [Visual Studio], returning characters
- slice method
ms.assetid: 80cd77a6-3718-492e-8e96-f909d8721d91
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1baa0a05a2d6aa8c06cc962761c8e557632d034c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="slice-method-string-javascript"></a>slice Yöntemi (Dize) (JavaScript)
Bir dizenin bir bölümünü döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. A `String` nesne veya dize sabit değeri.  
  
 `start`  
 Gerekli. Belirtilen kısmını başlangıç dizini `stringObj`.  
  
 `end`  
 İsteğe bağlı. Belirtilen kısmını sonu dizinine `stringObj`. Alt dizeyi en fazla karakter içerir, ancak tarafından karakteri belirtilen dahil değil, `end`. Bu değer belirtilmezse, alt dizeyi sonuna kadar devam `stringObj`.  
  
## <a name="remarks"></a>Açıklamalar  
 `slice` Yöntemi döndürür bir `String` belirtilen bölümünü içeren bir nesne `stringObj`.  
  
 `slice` Yöntemi kopyalar kadar ancak dahil değil belirttiği karakter `end`.  
  
 Varsa `start` olan negatif, onu olarak işlem görür *uzunluğu*  +  `start` nerede *uzunluğu* dize uzunluğu. Varsa `end` olan negatif, onu olarak işlem görür *uzunluğu* + `end`. Varsa `end` olan atlanırsa, kopyalama, sonuna kadar devam eder `stringObj`. Varsa `end` önce oluşur `start`, hiçbir karakter yeni dizesine kopyalanır.  
  
## <a name="example"></a>Örnek  
 İlk örnekteki `slice` yöntemi tüm dizeyi döndürür. İkinci örnekteki `slice` yöntemi son karakter dışındaki tüm dize döndürür.  
  
```JavaScript  
var str1 = "all good boys do fine";  
  
var slice1 = str1.slice(0);  
var slice2 = str1.slice(0,-1);  
var slice3 = str1.slice(4);  
var slice4 = str1.slice(4, 8);  
  
document.write(slice1 + "<br/>");  
document.write(slice2 + "<br/>");  
document.write(slice3 + "<br/>");  
document.write(slice4);  
  
// Output:  
// all good boys do fine  
// all good boys do fin  
// good boys do fine  
// good  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [slice yöntemi (dizi)](../../javascript/reference/slice-method-array-javascript.md)