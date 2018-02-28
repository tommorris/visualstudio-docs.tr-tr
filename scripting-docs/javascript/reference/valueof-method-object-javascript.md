---
title: "valueOf yöntemi (nesne) (JavaScript) | Microsoft Docs"
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
- valueOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- valueOf method
ms.assetid: c555e38b-f451-4341-8fcd-4c8b02906a2c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 677b56fd6fc142ce175b130d2f83291c1ac9535f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="valueof-method-object-javascript"></a>valueOf Yöntemi (Nesne) (JavaScript)
Belirtilen nesne ilkel değerini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
object.valueOf( )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `object` başvurudur herhangi iç [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesnesi.  
  
 `valueOf` Yöntemi tanımlanmış farklı her biri için iç [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesnesi.  
  
|Nesne|Dönüş Değeri|  
|------------|------------------|  
|Dizi|Dizi örneğini döndürür.|  
|Boole değeri|Boole değeri.|  
|Tarih|Gece yarısından, 1 Ocak 1970 UTC milisaniye saklı saat değeri.|  
|İşlev|İşlev kendisi.|  
|Sayı|Sayısal değer.|  
|Nesne|Nesne kendisi. Bu varsayılandır.|  
|Dize|Dize değeri.|  
  
 **Matematik** ve `Error` nesneleri sahip bir `valueOf` yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 **Uygulandığı öğe**: [dizi nesnesi](../../javascript/reference/array-object-javascript.md)&#124; [Boolean nesnesi](../../javascript/reference/boolean-object-javascript.md)&#124; [Tarih nesne](../../javascript/reference/date-object-javascript.md)&#124; [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)&#124; [Sayı nesne](../../javascript/reference/number-object-javascript.md)&#124; [Nesne nesne](../../javascript/reference/object-object-javascript.md)&#124; [Dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toString yöntemi (nesne)](../../javascript/reference/tostring-method-object-javascript.md)