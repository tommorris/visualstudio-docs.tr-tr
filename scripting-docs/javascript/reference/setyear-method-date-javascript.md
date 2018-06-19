---
title: setYear yöntemi (tarih) (JavaScript) | Microsoft Docs
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
- setYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Year method
- setYear method
ms.assetid: 36431050-e0ec-45ee-830d-0d7c20e207ea
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5a9318de4a9420e0518dcd7f00a51c7161a8f92c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791594"
---
# <a name="setyear-method-date-javascript"></a>setYear Yöntemi (Tarih) (JavaScript)
Yıl değerini ayarlar `Date` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.setYear(numYear)   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Tüm `Date` nesnesi.  
  
 `numYear`  
 Gerekli. Yıldır 1900 ile 1999 yıl 1900 eksi eşit bir sayısal değer budur. Bu aralığın dışında tarihler için 4 basamaklı sayısal bir değer budur.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem artık kullanılmıyor ve için geriye dönük uyumluluk yalnızca korunur. Kullanım `setFullYear` yöntemi yerine.  
  
 Yıl değerini ayarlamak için bir `Date` 1997, nesnesine çağrı **setYear(97)**. Yılın 2010 ayarlamak için arama **setYear(2010)**. Son olarak, bir yılın 0-99 aralığında yıl ayarlamak için kullanın `setFullYear` yöntemi.  
  
> [!NOTE]
>  İçin [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] sürüm 1.0, `setYear` tarafından sağlanan yıl değerini 1900 eklenmesi sonucu olan bir değer kullanır `numYear`yıl değerinin ne olursa olsun. Örneğin, bir yıl için 1899 ayarlamak için `numYear` -1'dir ve 2000 yılı ayarlamak için `numYear` 100'dür.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getFullYear yöntemi (tarih)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear yöntemi (tarih)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [getYear yöntemi (tarih)](../../javascript/reference/getyear-method-date-javascript.md)   
 [setFullYear yöntemi (tarih)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear yöntemi (tarih)](../../javascript/reference/setutcfullyear-method-date-javascript.md)