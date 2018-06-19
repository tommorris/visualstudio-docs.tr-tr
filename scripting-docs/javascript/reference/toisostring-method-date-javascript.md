---
title: Toısostring yöntemi (tarih) (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- toISOString method [JavaScript]
ms.assetid: 58577d8f-3ae8-4887-8687-26233ea79ff6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31559e1bc44849573ec7dc903411ce98b0a4440d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791591"
---
# <a name="toisostring-method-date-javascript"></a>toISOString Yöntemi (Tarih) (JavaScript)
ISO biçiminde bir dize değeri olarak bir tarihi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
  
objDate.toISOString()  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tarih International Organization for Standardization (ISO) biçimini dize gösterimi.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `objDate` geçerli bir tarih içermiyor bir `RangeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 ISO 8601 biçiminde alma ISO biçimidir. Daha fazla bilgi için bkz: [tarih ve saat dizelerini](../../javascript/date-and-time-strings-javascript.md).  
  
 Saat dilimi her zaman çıkış soneki Z belirtilmiştir, UTC alınır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `toISOString` yöntemi.  
  
```JavaScript  
var dt = new Date("30 July 2010 15:05 UTC");  
document.write(dt.toISOString());  
document.write("<br />");  
document.write(dt.toUTCString());  
  
// Output:  
//  2010-07-30T15:05:00.000Z  
//  Fri, 30 Jul 2010 15:05:00 UTC  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih nesnesi](../../javascript/reference/date-object-javascript.md)   
 [Tarih ve saat dizeleri](../../javascript/date-and-time-strings-javascript.md)