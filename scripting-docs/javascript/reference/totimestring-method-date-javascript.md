---
title: "toTimeString yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toTimeString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toTimeString method
ms.assetid: a4a8c0f2-55a9-4e84-94c3-f0a547fb04b5
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d9af1f688fee0c066158d8504e00f22af9b3a21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="totimestring-method-date-javascript"></a>toTimeString Yöntemi (Tarih) (JavaScript)
Zaman bir dize değeri olarak döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
objDate. toTimeString( )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `objDate` başvurusu olan bir `Date` nesnesi.  
  
 `toTimeString` Yöntemi geçerli saat dilimi zamanında içeren bir string değeri döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, zaman 2000 milisaniye 1 Ocak 1970 UTC gece yarısından sonra ayarlanır ve ardından onu yazılır.  
  
```JavaScript  
var aDate = new Date();  
     aDate.setTime(2000);  
     document.write(aDate.toTimeString());  
  
// Output depends on the time in the current time zone.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toDateString yöntemi (tarih)](../../javascript/reference/todatestring-method-date-javascript.md)   
 [toLocaleTimeString yöntemi (tarih)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)