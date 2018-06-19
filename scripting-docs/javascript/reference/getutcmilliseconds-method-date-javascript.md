---
title: getUTCMilliseconds yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- getUTCMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- UTC times, returning
- getUTCMilliseconds method
ms.assetid: 7491d387-7b6a-40df-89e5-55c64795ef70
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3fb7cf202c8511bec00c10dc5b8c23bd198d8700
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790556"
---
# <a name="getutcmilliseconds-method-date-javascript"></a>getUTCMilliseconds Metodu (Tarih) (JavaScript)
Milisaniye olarak alır bir `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getUTCMilliseconds()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değişebilir bir milisaniyelik değeri 0-999 arasındaki döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel saatle milisaniye sayısını almak üzere kullanmak `getMilliseconds` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `getUTCMilliseconds` yöntemi.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getUTCMilliseconds());  
document.write("<br/>");  
  
date.setMilliseconds(34);  
document.writedate.getUTCMilliseconds());  
  
// Output:  
// 0   
// 34   
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getMilliseconds yöntemi (tarih)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [setMilliseconds yöntemi (tarih)](../../javascript/reference/setmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds yöntemi (tarih)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)