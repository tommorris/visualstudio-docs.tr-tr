---
title: setMonth yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- setMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Month method
- setMonth method
ms.assetid: 4f5be295-d536-46c0-b3a4-ad06457efe82
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f2672abebd327af8b0da58d46ebc183b8159711
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791588"
---
# <a name="setmonth-method-date-javascript"></a>setMonth Yöntemi (Tarih) (JavaScript)
Ay değeri ayarlar `Date` yerel saat kullanarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj. setMonth(numMonth[, dateVal])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numMonth`  
 Gerekli. Bir sayısal değer aya eşit. Ocak değeri 0'dır ve diğer ay değerlerini art arda izleyin.  
  
 `dateVal`  
 İsteğe bağlı. Ayın gününü temsil eden bir sayısal değer. Bu değer sağlanmazsa, çağrısından değer `getDate` yöntemi kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Evrensel Eşgüdümlü saate (UTC) kullanarak ay değeri ayarlamak için kullanın `setUTCMonth` yöntemi.  
  
 Varsa değerini `numMonth` 11 büyük (Ocak olan ay 0) veya negatif bir sayı saklı yıl uygun şekilde değiştirilir. Örneğin, saklı tarih "5 Oca 1996" ise ve **setMonth(14)** olduğu adlı, "Mar 5 1997 için." Tarihi değiştirilir  
  
 **SetFullYear** yöntemi, yıl, ay ve ayın günü ayarlamak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `setMonth` yöntemi.  
  
```JavaScript  
date = new Date('1/1/1990');  
date.setMonth(14);  
document.write(date);  
  
// Output: Fri Mar 1 00:00:00 PST 1991  
// Note that the time zone corresponds to the time zone on the local computer.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getMonth yöntemi (tarih)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [getUTCMonth yöntemi (tarih)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setUTCMonth yöntemi (tarih)](../../javascript/reference/setutcmonth-method-date-javascript.md)