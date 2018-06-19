---
title: toGMTString yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- toGMTString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toGMTString method
ms.assetid: 9dc1e722-5722-4b8c-a213-a2650f55f207
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cef8a61e04fbb5ada6e03fa946f434327422d9d7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791543"
---
# <a name="togmtstring-method-date-javascript"></a>toGMTString Yöntemi (Tarih) (JavaScript)
Bir tarihi Greenwich anlamına Time(GMT) kullanarak bir dizeye dönüştürülür döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.toGMTString()   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `dateObj` başvurudur herhangi `Date` nesnesi.  
  
 `toGMTString` Yöntemi kullanımdan kalkmıştır ve geriye dönük uyumluluk yalnızca sağlanır. Kullanmanız önerilir `toUTCString` yöntemi yerine.  
  
 `toGMTString` Yöntemi döndürür bir `String` tarihi içeren nesne biçimlendirilmiş GMT kuralını kullanarak. Dönüş değerinin biçimi şu şekildedir: "05 Oca 1996 00:00:00 GMT."  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toUTCString yöntemi (tarih)](../../javascript/reference/toutcstring-method-date-javascript.md)