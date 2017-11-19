---
title: "toLocaleDateString yöntemi (tarih) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toLocaleDateString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toLocaleDateString method
ms.assetid: 0b83715c-8ced-4bd7-8940-a8007d002d10
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6b4b019ad329a73bec13766932fbcadfa2ed133
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="tolocaledatestring-method-date-javascript"></a>toLocaleDateString Yöntemi (Tarih) (JavaScript)
Bir tarih olarak ana bilgisayar ortamı geçerli yerel ya da belirtilen yerel ayar için uygun olan bir string değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.toLocaleDateString( [locales][, options])   
```  
  
#### <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. A `Date` nesnesi.  
  
 `locales`  
 İsteğe bağlı. Bir veya daha fazla dil veya yerel ayar etiketlerini içeren bir yerel dizeler dizisi. Birden fazla yerel ayar dizesi eklerseniz, bunları böylece ilk giriş tercih edilen yerel öncelik sırasına göre azalan sırada listeleyin. Bu parametresini atlarsanız, varsayılan yerel ayar JavaScript çalışma zamanı kullanılır.  
  
 `options`  
 İsteğe bağlı. Karşılaştırma seçenekleri belirten bir veya daha fazla özellikleri içeren bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Internet Explorer 11 başlangıç `toLocaleDateString` kullanan `Intl.DateTimeFormat` için destek ekler tarih dahili olarak biçimlendirmek için `locales` ve `options` parametreleri. Bu parametreler hakkında daha fazla bilgi için bkz: [INTL.datetimeformat](../../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
> [!IMPORTANT]
>  `locales` Ve `options` parametreleri tüm belge modları ve tarayıcı sürümlerinde desteklenmez. Daha fazla bilgi için gereksinimleri bölümüne bakın.  
  
 Kullandığınızda `toLocaleDateString` Internet Explorer 10 standartları belge modunda, önceki belge modları ve quirks modu:  
  
-   Geçerli saat diliminde tarih içeren bir dize değeri döndürür.  
  
-   Ana bilgisayar ortamı geçerli yerel ayar varsayılan biçiminde döndürülen tarihidir.  
  
 Atlarsanız `locales` parametresi, bu yöntemin dönüş değeri olamaz dayanıyordu üzerine komut, çünkü bilgisayardan diğerine farklılık gösterir. Bu senaryoda, yalnızca görüntülenen biçimli metin - bir hesaplama bir parçası olarak hiçbir zaman yöntemini kullanın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `toLocaleDateString` belirtilen yerel ayar ve karşılaştırma seçenekleriyle yöntemi.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleDateString("en-US"));  
document.write(date.toLocaleDateString("ja-JP"));  
document.write(date.toLocaleDateString("ar-SA", options));  
document.write(date.toLocaleDateString("hi-IN", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013‎   
// ‎2013‎年‎2‎月‎1‎日‎  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales`ve `options` Parametreler:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toDateString yöntemi (tarih)](../../javascript/reference/todatestring-method-date-javascript.md)   
 [toLocaleTimeString yöntemi (tarih)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)