---
title: toLocaleString (tarih) | Microsoft Docs
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
ms.assetid: 3472d7bd-b255-4804-8407-c4a1e419a5a3
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6dc7b1f38f7e57d1c10f7197bb73b13b3545380
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791927"
---
# <a name="tolocalestring-date"></a>toLocaleString (Tarih)
Geçerli veya belirtilen yerel ayar kullanarak bir dizeye dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dateObj.toLocaleString([locales][, options])   
```  
  
#### <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. `Date` Dönüştürülecek nesne.  
  
 `locales`  
 İsteğe bağlı. Bir veya daha fazla dil veya yerel ayar etiketlerini içeren bir yerel dizeler dizisi. Birden fazla yerel ayar dizesi eklerseniz, bunları böylece ilk giriş tercih edilen yerel öncelik sırasına göre azalan sırada listeleyin. Bu parametresini atlarsanız, varsayılan yerel ayar JavaScript çalışma zamanı kullanılır.  
  
 `options`  
 İsteğe bağlı. Karşılaştırma seçenekleri belirten bir veya daha fazla özellikleri içeren bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Internet Explorer 11 başlangıç `toLocaleString` kullanan `Intl.DateTimeFormat` için destek ekleyen dahili yapma karşılaştırmaları için `locales` ve `options` parametreleri. Bu parametreler hakkında daha fazla bilgi için bkz: [INTL.datetimeformat](../../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
> [!IMPORTANT]
>  `locales` Ve `options` parametreleri tüm belge modları ve tarayıcı sürümlerinde desteklenmez. Daha fazla bilgi için gereksinimleri bölümüne bakın.  
  
 Kullandığınızda `toLocaleString` Internet Explorer 10 standartları belge modunda, önceki belge modları ve quirks modu:  
  
-   Döndürdüğü bir `String` geçerli yerel uzun varsayılan biçimde yazılmış tarihi içeren nesne.  
  
-   1601 1999 M.S. arasındaki tarihleri, tarih göre kullanıcının Denetim Masası bölgesel ayarları biçimlendirilir.  
  
> [!NOTE]
>  Atlarsanız `locales` parametresi, kullanım `toLocaleString` yalnızca bir kullanıcıya; sonuçları görüntülemek için döndürülen sonuç makineye özgü olduğundan hiçbir zaman, bir komut dosyası içindeki değerleri hesaplamak için kullanın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `toLocaleString` yöntemi.  
  
```JavaScript  
function toLocaleStrDemo(){     
   var d, s;                      //Declare variables.  
   d = new Date();                //Create Date object.  
   s = "Current setting is ";  
   s += d.toLocaleString();       //Convert to current locale.  
   return(s);                     //Return converted date  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `toLocaleString` belirtilen yerel ayar ve karşılaştırma seçenekleriyle yöntemi.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleString("en-US"));  
document.write(date.toLocaleString("ja-JP"));  
document.write(date.toLocaleString("ar-SA", options));  
document.write(date.toLocaleString("hi-IN", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013‎ ‎6‎:‎00‎:‎00‎ ‎AM  
// ‎2013‎年‎2‎月‎1‎日‎ ‎6‎:‎00‎:‎00  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 `locales`ve `options` Parametreler:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleDateString yöntemi (tarih)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)