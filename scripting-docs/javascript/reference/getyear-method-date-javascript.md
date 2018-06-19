---
title: getYear yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- getYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, returning year
- GetYear method
ms.assetid: 0e23e832-acd4-49a9-a175-515d0094f172
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0e08fae8da1b102918de70650d09080a7ff7ebd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790634"
---
# <a name="getyear-method-date-javascript"></a>getYear Metodu (Tarih) (JavaScript)
Yılın alır bir `Date` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getYear()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yıl döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!IMPORTANT]
>  Bu yöntem artık kullanılmıyor ve yalnızca geriye dönük uyumluluk için sağlanır. Kullanım `getFullYear` yöntemi yerine.  
  
 İçinde [!INCLUDE[jsv1textspecific](../../javascript/reference/includes/jsv1textspecific-md.md)]ve ardından Internet Explorer sürümleri ile başlayan [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)], döndürülen 1900 eksi saklı yıl değerdir. Örneğin, 1899 yıl -1 döndürülür ve 2000 yılı 100 olarak döndürülür.  
  
 İçinde [!INCLUDE[jsv3textspecific](../../javascript/reference/includes/jsv3textspecific-md.md)] aracılığıyla [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)], bir yıl formülü bağlıdır. Bir yıl ile 1999 1900'ı için döndürülen değer 1900 eksi saklı yıl 2 basamaklı değerdir. Bu aralığın dışında tarihler için 4 rakamlı yıl döndürülür. Örneğin, 1996 96 döndürüldü, ancak 1825 ve 2025 olarak döndürülür.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getFullYear yöntemi (tarih)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear yöntemi (tarih)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear yöntemi (tarih)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear yöntemi (tarih)](../../javascript/reference/setutcfullyear-method-date-javascript.md)   
 [setYear yöntemi (tarih)](../../javascript/reference/setyear-method-date-javascript.md)