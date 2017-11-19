---
title: "decodeURI işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: decodeURI
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: decodeURI method
ms.assetid: af6c81dc-10f4-4243-a7ce-d18ae3ea0fb8
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97291142083ae88c7dc84d9cd08af5c3c39ff9e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="decodeuri-function-javascript"></a>decodeURI İşlevi (JavaScript)
Kodlanmamış bir kodlanmış Tekdüzen Kaynak Tanımlayıcısı (URI), sürüm alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
decodeURI(URIstring)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `URIstring` bağımsız değişkeni, kodlanmış bir URI temsil eden bir değerdir.  
  
 Kullanım `decodeURI` kullanım dışı yerine işlevi `unescape` işlevi.  
  
 `decodeURI` İşlevi bir string değeri döndürür.  
  
 Varsa `URIString` URIError oluşur geçerli değil.  
  
 **Uygulandığı öğe**: [genel nesne](../../javascript/reference/global-object-javascript.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, ilk olarak bir URI bileşeni kodlar ve ardından kodunu çözer.  
  
```JavaScript  
var uriEncode = encodeURIComponent ("www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write (uriEncode);  
document.write ("<br/>");  
document.write (uriDecode);  
  
// Output:  
// www.Not%20a%20URL.com  
// www.Not a URL.com  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Decodeurıcomponent işlevi](../../javascript/reference/decodeuricomponent-function-javascript.md)   
 [encodeURI işlevi](../../javascript/reference/encodeuri-function-javascript.md)   
 [Genel nesne](../../javascript/reference/global-object-javascript.md)