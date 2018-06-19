---
title: getFullYear yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- getFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, returning year
- Date object
- getFullYear method
ms.assetid: f9ec1262-02e9-4791-90b5-48f33b1dc4bc
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 211d6c86435e39eb75b9b1ce3415738541ca07db
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790535"
---
# <a name="getfullyear-method-date-javascript"></a>getFullYear Metodu (Tarih) (JavaScript)
Yerel saat kullanarak yıl alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getFullYear()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dört basamaklı bir sayı olarak yıl. Örneğin, 1976 yıl 1976 döndürülür. Yılları iki basamak olarak belirtilen `Date` Oluşturucusu veya `setFullYear` "5/14/12", bu nedenle verilen yirminci yüzyılda olduğu varsayılır `getFullYear` "1912" döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Evrensel Eşgüdümlü saate (UTC) kullanarak yılı almak için `getUTCFullYear` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **getFullYear** yöntemi.  
  
```JavaScript  
var date = new Date("1/1/01");  
document.write(date.getFullYear());  
  
// Output: 1901  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getUTCFullYear yöntemi (tarih)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear yöntemi (tarih)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear yöntemi (tarih)](../../javascript/reference/setutcfullyear-method-date-javascript.md)