---
title: unescape işlevi (JavaScript) | Microsoft Docs
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
- unescape
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Unescape method
ms.assetid: 4adf0270-88b5-4d54-8110-d879d6ae97c2
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 96601fc21f47c86aec8c3702a6861c3676aacacf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791942"
---
# <a name="unescape-function-javascript"></a>unescape İşlevi (JavaScript)
Kodunu çözer `String` nesneleri kodlanmış ile `escape` işlevi. Kullanım dışı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unescape(charString)   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `charString` bağımsız değişkeni bir `String` nesne veya çözülecek sabit değer.  
  
 `unescape` İşlevi döndürür içeriğini içeren bir dize değeri `charstring`. Tüm karakterleri % kodlanmış*xx* onaltılık biçimde ASCII karakter kümesi eşdeğerlerine tarafından değiştirilir.  
  
 Karakter kodlanmış **%u** *xxxx* biçimi (Unicode karakter), onaltılık kodlama ile Unicode karakteri ile değiştirilir *xxxx*.  
  
> [!NOTE]
>  `unescape` İşlevi Tekdüzen Kaynak Tanımlayıcıları (URI) kodunu çözmek için kullanılmamalıdır. Kullanım `decodeURI` ve `decodeURIComponent` yerine çalışır.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [genel nesne](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [decodeURI işlevi](../../javascript/reference/decodeuri-function-javascript.md)   
 [Decodeurıcomponent işlevi](../../javascript/reference/decodeuricomponent-function-javascript.md)   
 [escape işlevi](../../javascript/reference/escape-function-javascript.md)   
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)