---
title: Deyimi (JavaScript) ile | Microsoft Docs
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
- with_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- With statement
ms.assetid: 892c7621-ae9e-4c10-8adb-05532274b1ca
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 35d49b13261c66cde0ecd53517a99361f6aecb79
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="with-statement-javascript"></a>with Deyimi (JavaScript)
Bir deyim için varsayılan nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
with (object) {  
    statements  
}   
```  
  
## <a name="parameters"></a>Parametreler  
 `object`  
 Varsayılan nesne.  
  
 `statements`  
 Kendisi için bir veya daha fazla deyimleri `object` varsayılan nesnesidir.  
  
## <a name="remarks"></a>Açıklamalar  
 `with` Deyimi belirli durumlarda yazmak zorunda kod miktarını kısaltmak için yaygın olarak kullanılır.  
  
> [!WARNING]
>  Kullanımını `with` katı modda izin verilmiyor. Kullanımını `with` kodu okuma ve hata ayıklama için daha zor hale getirebilir ve genellikle kaçınılmalıdır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, `Math` nesnesi sürekli olarak kullanılır:  
  
```JavaScript  
x = Math.cos(3 * Math.PI) + Math.sin(Math.LN10)   
y = Math.tan(14 * Math.E)  
```  
  
## <a name="example"></a>Örnek  
 Kullanılacak örnek yeniden yazma, `with` deyimi, kodunuzu daha kısa olur:  
  
```JavaScript  
with (Math){  
   x = cos(3 * PI) + sin (LN10)    
   y = tan(14 * E)  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bu bildirimi](../../javascript/reference/this-statement-javascript.md)