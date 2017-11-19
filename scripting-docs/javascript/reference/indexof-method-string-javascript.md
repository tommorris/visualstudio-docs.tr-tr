---
title: "indexOf yöntemi (dize) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: indexOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- indexOf method, string
- string, indexOf method
ms.assetid: a17372fa-669b-471b-9240-46927a265152
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ecd96acb21f9d7711f9ee00dbf1c1bb70705c0d8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="indexof-method-string-javascript"></a>indexOf Yöntemi (Dize) (JavaScript)
Bir alt dizenin ilk bulunduğu konumu döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
strObj. indexOf(subString[, startIndex])  
```  
  
## <a name="parameters"></a>Parametreler  
 `strObj`  
 Gerekli. A `String` nesne veya dize sabit değeri.  
  
 `subString`  
 Gerekli. Dize içinde aranacak alt dize  
  
 `startIndex`  
 İsteğe bağlı. Aramaya başlamak dizin `String` nesnesi. Eğer atlanırsa, arama dizenin başından başlar.  
  
## <a name="remarks"></a>Açıklamalar  
 **İndexOf** yöntemi substring başlangıcını döndürür `String` nesnesi. Eğer alt dize bulunamazsa, -1 döndürülür.  
  
 Varsa `startindex` negatif `startindex` sıfır olarak kabul edilir. Eğer en yüksek dizinden daha büyük ise, en yüksek dizin alınır.  
  
 Arama soldan sağa yapılır. Aksi takdirde, bu yöntem aynıdır **lastIndexOf**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **indexOf** yöntemi.  
  
```JavaScript  
var str = "original equipment manufacturer";  
  
var s = "equip is at position " + str.indexOf("equip");  
s += "<br />";  
s += "abc is at position " + str.indexOf("abc");  
  
document.write(s);  
  
// Output:  
// equip is at position 9  
// abc is at position -1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [lastIndexOf yöntemi (dize)](../../javascript/reference/lastindexof-method-string-javascript.md)   
 [Kaydırma, kaydırma ve yakınlaştırma örnek uygulaması](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)