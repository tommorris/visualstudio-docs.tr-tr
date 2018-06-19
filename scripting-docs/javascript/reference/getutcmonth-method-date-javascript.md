---
title: getUTCMonth yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- getUTCMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- UTC dates, returning
- Month method
- getUTCMonth method
ms.assetid: eabae139-4da0-4e4a-a4cb-608e6375fc9e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07e7ecdc9a9ee8a49c12fc65e4b2ba1056bd377c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790550"
---
# <a name="getutcmonth-method-date-javascript"></a>getUTCMonth Metodu (Tarih) (JavaScript)
Ayın alır bir `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getUTCMonth()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 0 (Ocak) ile 11 (aralık) arasında bir tamsayı döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel saatle ay almak için **getMonth** yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `getUTCMonth` yöntemi.  
  
```JavaScript  
var date = new Date("2/2/2002");  
document.write(date.getUTCMonth());  
  
// Output: 1  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getMonth yöntemi (tarih)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [setMonth yöntemi (tarih)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCMonth yöntemi (tarih)](../../javascript/reference/setutcmonth-method-date-javascript.md)