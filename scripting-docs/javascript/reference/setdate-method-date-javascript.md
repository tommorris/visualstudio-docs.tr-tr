---
title: setDate yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- setDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- setDate method
- dates, setting
ms.assetid: a84b9b01-a6d0-489f-8a13-e7af9e9630b2
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8d74340287b3a7348419d302f79775eb610c6983
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791603"
---
# <a name="setdate-method-date-javascript"></a>setDate Yöntemi (Tarih) (JavaScript)
Sayısal gün ay değerini ayarlar `Date` yerel saat kullanarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setDate(numDate)   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numDate`  
 Gerekli. Ayın gününü eşit sayısal değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Evrensel Eşgüdümlü saate (UTC) kullanarak gün ay değeri ayarlamak için kullanın `setUTCDate` yöntemi.  
  
 Varsa değerini `numDate` gün ay üzerinden tarih dökümünü bir sonraki ay ve/veya yıl sayısını değerinden daha büyük. Örneğin, saklı tarih 5 Ocak 1996 ise ve `setDate(32)` çağrılır, 1 Şubat 1996 tarih yapılan değişiklikler. Varsa `numDate` negatif bir sayı, tarih dökümünü bir önceki ay ve/veya yıl dön. Örneğin, saklı tarih 5 Ocak 1996 ise ve `setDate(-32)` çağrılır, 29 Kasım 1995 tarih yapılan değişiklikler.  
  
 [SetFullYear yöntemi (tarih)](../../javascript/reference/setfullyear-method-date-javascript.md) yıl, ay ve ayın günü ayarlamak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `setDate` yöntemi.  
  
```JavaScript  
var date = new Date("12/15/1990");  
date.setDate(30);  
document.write(date);  
  
// Output (for the PST time zone): Sun Dec 30 00:00:00 PST 1990  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getDate yöntemi (tarih)](../../javascript/reference/getdate-method-date-javascript.md)   
 [setFullYear yöntemi (tarih)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setMonth yöntemi (tarih)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCDate yöntemi (tarih)](../../javascript/reference/setutcdate-method-date-javascript.md)