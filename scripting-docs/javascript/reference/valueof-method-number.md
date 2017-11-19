---
title: "valueOf yöntemi (sayı) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 0242a9ce-d41a-4c9b-af59-e8df32bbd913
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7918fb94673803e99d476d63fd814bce19bf9a5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="valueof-method-number"></a>valueOf Yöntemi (Sayı)
Belirtilen ilkel değerini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
number.valueOf()  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bu yöntem hiç parametre yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sayı döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki örnekte, örneklenen sayı nesnesi bu yöntemin dönüş değeri ile aynıdır.  
  
```JavaScript  
var num = 1234;  
var s = num.valueOf();  
  
if (num === s)  
document.write("same");  
else  
document.write("different");  
  
// Output:  
// same  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]