---
title: "getTimezoneOffset yöntemi (tarih) (JavaScript) | Microsoft Docs"
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
- getTimeZoneOffset
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getTimezoneOffset method
- time zones [Visual Studio]
ms.assetid: 58ee22b0-4688-45bd-a337-cc23119b09ce
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e49a3c8b7060e6097300f8aaf99b2ef869833018
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="gettimezoneoffset-method-date-javascript"></a>getTimezoneOffset Metodu (Tarih) (JavaScript)
Dakika cinsinden yerel bilgisayardaki saat ve Evrensel Eşgüdümlü saate (UTC) arasındaki farkı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getTimezoneOffset()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bilgisayarda saat arasında dakika sayısını döndürür (istemci makine veya bu yöntem bir sunucu betik, sunucu makinesi çağrılırsa) ve UTC. Geçerli bilgisayarın yerel saati UTC (örn., Japonya) öncesinde geçerli bilgisayarın yerel saati UTC (örn., Pasifik Yaz Saati) ve negatif arkasında ise pozitif. Bir istemci, Los Angeles tarafından bir sunucu New York şehrinde 1 Aralık kurulur varsa `getTimezoneOffset` istemci veya 300 sunucuda yürütülürse yürütülürse 480 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `getTimezoneOffset` yöntemi.  
  
```JavaScript  
var date =  new Date();  
var minutes = date.getTimezoneOffset();  
  
if (minutes < 0)  
    document.write(minutes / 60 + " hours after UTC");  
else  
    document.write(minutes / 60 + " hours before UTC");  
  
// Output (for example, where local time is PST):   
7 hours before UTC  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getTime yöntemi (tarih)](../../javascript/reference/gettime-method-date-javascript.md)