---
title: valueOf yöntemi (dizi) | Microsoft Docs
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
ms.assetid: b694fe65-1297-4580-8af2-406932c06454
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 68dc5599a495df42629ec49f25e8f5344f67e3d5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791669"
---
# <a name="valueof-method-array"></a>valueOf Yöntemi (Dizi)
Belirtilen nesne ilkel değerini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array.valueOf()  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bu yöntem hiç parametre yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dizi örneğini döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki örnekte, örneklenen dizi nesnesi bu yöntemin dönüş değeri ile aynıdır.  
  
```JavaScript  
var arr = [1, 2, 3, 4];  
var s = arr.valueOf();  
  
if (arr === s)  
document.write("same");  
else  
document.write("different");  
  
// Output:  
// same  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]