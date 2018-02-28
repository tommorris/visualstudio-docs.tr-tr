---
title: "Encodeurıcomponent işlevi (JavaScript) | Microsoft Docs"
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
- encodeURIComponent
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- encodeURIComponent method
ms.assetid: 8202bce6-1342-40dc-a5ef-ac6d210a7d15
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 56680e9bcfe1de61d8a1eabd0ff8d2eced01d603
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="encodeuricomponent-function-javascript"></a>encodeURIComponent İşlevi (JavaScript)
Bir metin dizesi Tekdüzen Kaynak Tanımlayıcısı (URI) geçerli bir bileşeni olarak kodlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
encodeURIComponent(encodedURIString)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `encodedURIString` bağımsız değişkeni, kodlanmış bir URI bileşeni temsil eden bir değerdir.  
  
 `encodeURIComponent` İşlevi kodlanmış bir URI döndürür. Sonucu geçirirseniz `decodeURIComponent`, özgün dizesi döndürdü. Çünkü `encodeURIComponent` işlevi tüm karakterleri kodlar, dize gibi bir yolunu temsil ediyorsa dikkatli olun **/folder1/folder2/default.html**. Eğik çizgi karakterleri kodlanmış olmalıdır ve bir istek olarak bir web sunucusuna gönderilen geçerli olmaz. Kullanım `encodeURI` dize en fazla tek bir URI bileşen içeriyorsa, işlev.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, ilk olarak bir URI bileşeni kodlar ve ardından kodunu çözer.  
  
```JavaScript  
var uriEncode = encodeURIComponent ("www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write(uriEncode);  
document.write("<br/>");  
document.write(uriDecode);  
  
// Output:  
// www.Not%20a%20URL.com  
// www.Not a URL.com  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [decodeURI işlevi](../../javascript/reference/decodeuri-function-javascript.md)   
 [Decodeurıcomponent işlevi](../../javascript/reference/decodeuricomponent-function-javascript.md)