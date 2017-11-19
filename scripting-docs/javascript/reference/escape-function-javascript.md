---
title: "escape işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: escape
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- encoding string objects
- Escape method
- hexadecimal
- String object, encoding
ms.assetid: caa92bea-ba69-4109-a68a-6e2debda463a
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b53a447ae6dde917c12a4711d9038136dc4500cf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="escape-function-javascript"></a>escape İşlevi (JavaScript)
Tüm bilgisayarlarda okumak için dizeleri kodlar. Kullanım dışı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
escape(charString)   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `charString` bağımsız değişkeni olan herhangi bir `String` nesne veya sabit kodlanmış olmalıdır.  
  
 **Kaçış** işlevi döndürür içeriğini içeren bir dize değeri (Unicode biçiminde) `charstring`. Noktalama işaretleri, tüm alanları vurgulu karakterlerin ve başka bir ASCII olmayan karakterler ile değiştirilir `%` *xx* kodlama, burada *xx* onaltılık sayı temsil eden için eşdeğerdir karakter. Örneğin, bir alan "% 20." döndürülür  
  
 255 kullanılarak depolanır daha büyük bir değer karakterlerle **%u** *xxxx* biçimi.  
  
> [!NOTE]
>  **Kaçış** işlevi Tekdüzen Kaynak Tanımlayıcıları (URI) kodlamak için kullanılmamalıdır. Kullanım `encodeURI` ve `encodeURIComponent` yerine çalışır.  
  
 **Uygulandığı öğe**: [genel nesne](../../javascript/reference/global-object-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [encodeURI işlevi](../../javascript/reference/encodeuri-function-javascript.md)   
 [Encodeurıcomponent işlevi](../../javascript/reference/encodeuricomponent-function-javascript.md)   
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)   
 [unescape işlevi](../../javascript/reference/unescape-function-javascript.md)