---
title: "encodeURI işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: encodeURI
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: encodeURI method
ms.assetid: 17bab5a2-bcd4-46c2-8b52-b2b5a0ed98a3
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8cf9bbdf34c0481c889d1176bc32ab0246a333a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="encodeuri-function-javascript"></a>encodeURI İşlevi (JavaScript)
Bir metin dizesi geçerli bir Tekdüzen Kaynak Tanımlayıcısı (URI) olarak kodlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
encodeURI(  
URIString  
)  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `URIString` bağımsız değişkeni, kodlanmış bir URI temsil eden bir değerdir.  
  
 `encodeURI` İşlevi kodlanmış bir URI döndürür. Sonucu geçirirseniz `decodeURI`, özgün dizesi döndürdü. `encodeURI` İşlevi şu karakterleri kodlayın değildir: ":", "/", ";" ve "?". Kullanım `encodeURIComponent` bu karakterleri kodlamak için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, ilk kodlar ve bir URI kodunu çözer.  
  
```JavaScript  
var uriEncode = encodeURI ("http://www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write(uriEncode);  
document.write("<br/>");  
document.write(uriDecode);  
  
// Output:  
// http://www.Not%20a%20URL.com  
// http://www.Not a URL.com  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [decodeURI işlevi](../../javascript/reference/decodeuri-function-javascript.md)   
 [Decodeurıcomponent işlevi](../../javascript/reference/decodeuricomponent-function-javascript.md)