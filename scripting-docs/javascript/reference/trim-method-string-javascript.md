---
title: trim yöntemi (dize) (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- trim method
ms.assetid: 03d38c7e-25cd-4ede-b58e-1a10b5249bab
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de358981cfbf569ef35be95b55b3e9856027df35
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791729"
---
# <a name="trim-method-string-javascript"></a>trim Yöntemi (Dize) (JavaScript)
Dizedeki tüm baş ve sondaki boşlukları ve satır sonlandırıcı karakterleri kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringObj.trim()  
```  
  
## <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. A `String` nesne veya dize sabit değeri. Bu dize tarafından değiştirilmez `trim` yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Orijinal dizenin başındaki ve sonundaki boşluk ve satır sonlandırıcı karakterler kaldırıldı.  
  
## <a name="remarks"></a>Açıklamalar  
 Kaldırılan karakterler boşluk, sekme, form besleme, satır besleme, satır başı ve satır beslemeyi kapsar. Bkz: [özel karakterler](../../javascript/advanced/special-characters-javascript.md) boşluk ve satır Sonlandırıcı karakteri kapsamlı bir listesi.  
  
 Kırpma yönteminizi uygulamak gösteren örnek için bkz: [prototipler ve prototip devralma](../../javascript/advanced/prototypes-and-prototype-inheritance.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `trim` yöntemi.  
  
```JavaScript  
var message = "    abc def     \r\n  ";  
  
document.write("[" + message.trim() + "]");  
document.write("<br/>");  
document.write("length: " + message.trim().length);  
  
// Output:  
//  [abc def]  
//  length: 7  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel karakterler](../../javascript/advanced/special-characters-javascript.md)   
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)   
 [Kaydırma, kaydırma ve yakınlaştırma örnek uygulaması](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)