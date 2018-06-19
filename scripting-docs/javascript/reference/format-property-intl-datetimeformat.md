---
title: format özelliği (INTL.datetimeformat) | Microsoft Docs
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
ms.assetid: 487930fe-a948-446f-902d-06bb0d7685d5
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e94fcd797a63944d0162dceadf773cf9b15f943
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790487"
---
# <a name="format-property-intldatetimeformat"></a>format Özelliği (Intl.DateTimeFormat)
Belirtilen tarih biçimlendirici ayarlarını kullanarak yerel ayarlara özgü tarih biçimleri bir işlev döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
dateTimeFormatObj.format  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dateTimeFormatObj`  
 Gerekli. Adını `DateTimeFormat` bir biçimlendirici kullanılacak nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen işlevi `format` özelliği alır tek bir bağımsız değişken `date`ve belirtilen seçenekleri kullanarak yerelleştirilmiş tarih temsil eden bir dize döndürür `DateTimeFormat` nesnesi. `date` Döndürülen işlevinin parametresi bir sayı, tarih dizesi olmalıdır veya bir `Date` nesnesi. Varsa `date` değil işlevini kullanıyor sağlanmış [Date.now](../../javascript/reference/date-now-function-javascript.md) varsayılan giriş değeri olarak.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanan bir `DateTimeFormat` Almanca tarihe "1 Ara 2007" yerelleştirme ve onu yeniden biçimlendirmek için nesne.  
  
```JavaScript  
var dtFormat = new Intl.DateTimeFormat(["de"], {  
    year: "numeric",  
    month: "long",  
    day: "2-digit",  
    hour: "numeric"  
});  
  
if (console && console.log) {  
    console.log(dtFormat.format(new Date("Dec 1, 2007")));  
    // Returns 01. Dezember 2007 00:00  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [INTL.datetimeformat nesnesi](../../javascript/reference/intl-datetimeformat-object-javascript.md)