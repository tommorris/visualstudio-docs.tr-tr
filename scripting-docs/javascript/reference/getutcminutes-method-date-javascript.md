---
title: "getUTCMinutes yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- UTC times, returning
- getUTCMinutes method
ms.assetid: b6d92543-b285-4e46-8f47-bba36e53fabd
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe691d3b52d18340eeeff81a91c049a262277c54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcminutes-method-date-javascript"></a>getUTCMinutes Metodu (Tarih) (JavaScript)
Dakika cinsinden alır bir `Date` Evrensel Eşgüdümlü saate (UTC) kullanılarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getUTCMinutes()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 0 ile 59 arasında bir tamsayı döndürür. Sıfır bir dakikadan az bir saat sonra saattir döndürülür. Varsa bir `Date` nesnesi oluşturulduğu saat belirtmeden, varsayılan olarak UTC dakika değeri 0'dır. Ancak, diğer saat dilimindeki farklı olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Yerel saat kullanarak depolanan dakika sayısını almak üzere kullanmak `getMinutes` yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `getUTCMinutes` yöntemi.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getUTCMinutes());  
document.write("<br/>");  
  
date.setMinutes(5);  
document.write(date.getUTCMinutes());  
  
// Output:   
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getMinutes yöntemi (tarih)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [setMinutes yöntemi (tarih)](../../javascript/reference/setminutes-method-date-javascript.md)   
 [setUTCMinutes yöntemi (tarih)](../../javascript/reference/setutcminutes-method-date-javascript.md)