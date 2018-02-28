---
title: "toLocaleTimeString yöntemi (tarih) (JavaScript) | Microsoft Docs"
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
- toLocaleTimeString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLocaleTimeString method
ms.assetid: 8ad75bf5-864c-4a2a-be90-220e87dce172
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77d8ee8fb6757b13da22a3cf3a59d28a105292cb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="tolocaletimestring-method-date-javascript"></a>toLocaleTimeString Yöntemi (Tarih) (JavaScript)
Ana bilgisayar ortamı geçerli yerel ya da belirtilen yerel ayar için uygun olan bir dize değeri olarak saati döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.toLocaleTimeString([locales][, options])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. A `Date` nesnesi.  
  
 `locales`  
 İsteğe bağlı. Bir veya daha fazla dil veya yerel ayar etiketlerini içeren bir yerel dizeler dizisi. Birden fazla yerel ayar dizesi eklerseniz, bunları böylece ilk giriş tercih edilen yerel öncelik sırasına göre azalan sırada listeleyin. Bu parametresini atlarsanız, varsayılan yerel ayar JavaScript çalışma zamanı kullanılır.  
  
 `options`  
 İsteğe bağlı. Karşılaştırma seçenekleri belirten bir veya daha fazla özellikleri içeren bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Internet Explorer 11 başlangıç `toLocaleTimeString` kullanan `Intl.DateTimeFormat` için destek ekler zaman dahili olarak biçimlendirmek için `locales` ve `options` parametreleri. Bu parametreler hakkında daha fazla bilgi için bkz: [INTL.datetimeformat](../../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
> [!IMPORTANT]
>  `locales` Ve `options` parametreleri tüm belge modları ve tarayıcı sürümlerinde desteklenmez. Daha fazla bilgi için gereksinimleri bölümüne bakın.  
  
 Kullandığınızda `toLocaleTimeString` Internet Explorer 10 standartları belge modunda, önceki belge modları ve quirks modu:  
  
-   Geçerli saat dilimi zamanında içeren bir dize değeri döndürür.  
  
-   Döndürülen zaman ana bilgisayar ortamı geçerli yerel ayar varsayılan biçimindedir.  
  
 Atlarsanız `locales` parametresi, bu yöntemin dönüş değeri olamaz dayanıyordu üzerine komut, çünkü bilgisayardan diğerine farklılık gösterir. Bu senaryoda, yalnızca görüntülenen biçimli metin - bir hesaplama bir parçası olarak hiçbir zaman yöntemini kullanın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `toLocaleTimeString` belirtilen yerel ayar ve karşılaştırma seçenekleriyle yöntemi.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleTimeString("en-US"));  
document.write(date.toLocaleTimeString("ja-JP"));  
document.write(date.toLocaleTimeString("ar-SA", options));  
document.write(date.toLocaleTimeString("hi-IN", options));  
  
// Output:  
// ‎‎6‎:‎00‎:‎00‎ ‎AM ‎   
// 6‎:‎00‎:‎00‎  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤ ٠٦‎:‎٠٠‎:‎٠٠‎ ‎ص  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013 06:00:00  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales`ve `options` Parametreler:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toTimeString yöntemi (tarih)](../../javascript/reference/totimestring-method-date-javascript.md)   
 [toLocaleDateString yöntemi (tarih)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)