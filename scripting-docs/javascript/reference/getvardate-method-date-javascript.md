---
title: "getVarDate yöntemi (tarih) (JavaScript) | Microsoft Docs"
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
- getVarDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- getVarDate method
- dates, VT_DATE format
ms.assetid: 561238de-5c91-45a3-b839-a16910d3a1cf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d21394a5381653997a6b406537a6bde4f5266b97
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getvardate-method-date-javascript"></a>getVarDate Metodu (Tarih) (JavaScript)
VT_DATE arasında bir değer döndüren bir `Date` nesnesi.  
  
> [!WARNING]
>  Bu yöntem yalnızca Internet Explorer'da desteklenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.getVarDate()   
```  
  
#### <a name="parameters"></a>Parametreler  
 Gerekli `dateObj` başvurusu olan bir `Date` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 VT_DATE değeri döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `getVarDate` Yöntemi COM nesneleri, ActiveX nesneleri veya kabul edin ve dönüş tarih değerleri VT_DATE biçimi diğer nesneleri ile JavaScript kodu etkileşim kurduğunda kullanılır. Visual Basic ve Visual Basic Scripting Edition (VBScript) bu nesneleri içerir. Döndürülen değerin gerçek biçim bölgesel ayarlarına bağlıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları ve Internet Explorer 10 standartları. İçinde desteklenmez [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
 **Uygulandığı öğe**: [tarih nesnesi](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [getDate yöntemi (tarih)](../../javascript/reference/getdate-method-date-javascript.md)   
 [Date.Parse işlevi](../../javascript/reference/date-parse-function-javascript.md)