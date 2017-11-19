---
title: "lastIndexOf yöntemi (dize) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: lastIndexOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- lastIndexOf method, string
- string, lastIndexOf method
ms.assetid: 1ed36ccd-0f0b-4f16-be45-0567207670af
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0fa0f35e970435a4d0296493c20afdeaac128cae
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="lastindexof-method-string-javascript"></a>lastIndexOf Yöntemi (Dize) (JavaScript)
Bir dizenin son a geçişi dizeyi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
strObj.lastIndexOf(substring[, startindex])  
```  
  
## <a name="parameters"></a>Parametreler  
 `strObj`  
 Gerekli. A `String` nesne veya dize sabit değeri.  
  
 `substring`  
 Gerekli. Aranacak alt dizeyi.  
  
 `startindex`  
 İsteğe bağlı. Arama başlanan dizini. Atlanırsa, arama dizesi sonunda başlar.  
  
## <a name="remarks"></a>Açıklamalar  
 **LastIndexOf** yöntemi döndürür içindeki alt dizenin başlangıcını belirten bir tamsayı değeri `String` nesnesi. Alt dizeyi bulunmazsa -1 döndürülür.  
  
 Varsa `startindex` negatif `startindex` sıfır olarak kabul edilir. En büyük karakter konum dizini büyükse, en büyük olası dizin olarak kabul edilir.  
  
 Arama dizedeki son karakter başlayarak gerçekleştirilir. Aksi takdirde, bu yöntem aynıdır **indexOf**.  
  
 Aşağıdaki örnek kullanımını göstermektedir **lastIndexOf** yöntemi.  
  
```JavaScript  
var str = "time, time";  
  
var s = "";  
s += "time is at position " + str.lastIndexOf("time");  
s += "<br />";  
s += "abc is at position " + str.lastIndexOf("abc");  
  
document.write(s);  
  
// Output:  
// time is at position 6  
// abc is at position -1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [indexOf yöntemi (dize)](../../javascript/reference/indexof-method-string-javascript.md)