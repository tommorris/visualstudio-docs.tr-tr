---
title: getUTCFullYear yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- getUTCFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getUTCFullYear method
- Date object
- UTCFullYear method
- dates, UTC
- UTC dates, returning
- Full Year method
- UTC dates, getting
ms.assetid: f11e5363-ef8a-48dd-9d56-4ee7290c7c48
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c8268631a96eed1f61ef4ba908b78680c8522096
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790565"
---
# <a name="getutcfullyear-method-date-javascript"></a>getUTCFullYear Metodu (Tarih) (JavaScript)
Evrensel Eşgüdümlü saate (UTC) kullanarak yılı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getUTCFullYear()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yıl dört basamaklı bir sayı olarak döndürür. Yılları iki basamak olarak belirtilen `Date` Oluşturucusu veya `setFullYear` "5/14/12", bu nedenle verilen yirminci yüzyılda olduğu varsayılır `getUTCFullYear` "1912" döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel saat kullanarak yıl almak için `getFullYear` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `getUTCFullYear` yöntemi.  
  
```JavaScript  
var date = new Date("1/9/36");  
document.write(date.getUTCFullYear());  
  
// Output: 1936  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getFullYear yöntemi (tarih)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [setFullYear yöntemi (tarih)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear yöntemi (tarih)](../../javascript/reference/setutcfullyear-method-date-javascript.md)