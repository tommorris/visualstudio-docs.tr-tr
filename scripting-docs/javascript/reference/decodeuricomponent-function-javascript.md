---
title: "Decodeurıcomponent işlevi (JavaScript) | Microsoft Docs"
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
- decodeURIComponent
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- decodeURIComponent method
ms.assetid: 486ccee2-afd7-4863-97ce-4adb50cf39c0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef7bdcd374a328bad632381d19e9823853d37f01
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="decodeuricomponent-function-javascript"></a>decodeURIComponent İşlevi (JavaScript)
Kodlanmamış sürüm kodlanmış bir bileşenin Tekdüzen Kaynak Tanımlayıcısı (URI) alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
decodeURIComponent(encodedURIString)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `encodedURIString` bağımsız değişkeni, kodlanmış bir URI bileşeni temsil eden bir değerdir.  
  
 Bir URIComponent tam bir URI'ın bir parçasıdır.  
  
 Varsa `encodedURIString` URIError oluşur geçerli değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, ilk kodlar ve bir URI kodunu çözer.  
  
```JavaScript  
var uriEncode = encodeURI ("http://www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write (uriEncode);  
document.write("<br/>");  
document.write (uriDecode);  
  
// Output:  
// http://www.Not%20a%20URL.com  
// http://www.Not a URL.com  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [decodeURI işlevi](../../javascript/reference/decodeuri-function-javascript.md)   
 [encodeURI işlevi](../../javascript/reference/encodeuri-function-javascript.md)