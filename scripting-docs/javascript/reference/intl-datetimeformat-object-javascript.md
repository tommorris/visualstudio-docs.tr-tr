---
title: INTL.datetimeformat nesnesi (JavaScript) | Microsoft Docs
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
- DateTimeFormat
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: cc555ac2-f31c-4239-a612-b84c08e3a37f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c50d6d7d939ebe05ce3ff9b434111413803ea40
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792122"
---
# <a name="intldatetimeformat-object-javascript"></a>Intl.DateTimeFormat Nesnesi (JavaScript)
Yerel ayarlara özgü tarih ve saat biçimlendirmesi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
dateTimeFormatObj = new Intl.DateTimeFormat([locales][, options])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dateTimeFormatObj`  
 Gerekli. Değişken adı atamak için `DateTimeFormat` için nesne.  
  
 `locales`  
 İsteğe bağlı. Bir veya daha fazla dil veya yerel ayar etiketlerini içeren bir yerel dizeler dizisi. Birden fazla yerel ayar dizesi eklerseniz, bunları böylece ilk giriş tercih edilen yerel öncelik sırasına göre azalan sırada listeleyin. Bu parametresini atlarsanız, varsayılan yerel ayar JavaScript çalışma zamanı kullanılır. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 `options`  
 İsteğe bağlı. Tarih ve saat için biçimlendirme seçeneklerini belirten bir veya daha fazla özellikleri içeren bir nesne. Ayrıntılar için Açıklamalar bölümüne bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 `locales` Parametresi için uygun olmalıdır [BCP 47](http://tools.ietf.org/html/rfc5646) dilini veya yerel ayarını etiketleri "en-US" ve "zh-CN" gibi. Etiket dil, bölge, ülke ve değişken içerebilir. Dil etiketleri örnekleri için bkz: [ek A](http://tools.ietf.org/html/rfc5646#appendix-A) BCP 47. İçin `DateTimeFormat`, eklediğiniz **-u** birini veya her ikisini aşağıdaki Unicode uzantıları dahil etmek için yerel ayar dizesindeki alt etiket:  
  
-   -bir numaralandırma sistemi uzantısı belirtmek için nu: *dil*-*bölge*-u-b -*numberingsystem*  
  
     Burada *numberingsystem* şunlardan biri olabilir: Arap, arabext, bali, beng, deva, fullwide, gujr, Ustası, hanidec, khmr, knda, laoo, latn, yanlış, mylm, mong, mymr, orya, tamldec, telu, Tay dili, tibt.  
  
-   -bir takvim belirtmeniz ca: *dil*-*bölge*-u-ca -*Takvim*  
  
     Burada *Takvim* şunlardan biri olabilir: Budist, Çince, gregory İslam, islamicc, Japonca.  
  
 `options` Parametresi, aşağıdaki özellikler içerebilir:  
  
|Özellik|Açıklama|Olası değerler|Varsayılan değer|  
|--------------|-----------------|---------------------|-------------------|  
|`localeMatcher`|Kullanılacak yerel ayar eşleştirme algoritması belirtir.|"" en uygun"araması"|"en iyi sığacak şekilde"|  
|`formatMatcher`|Kullanılacak biçim eşleştirme algoritması belirtir.|"temel", "en uygun"|"en iyi sığacak şekilde"|  
|`hour12`|12 saat biçiminde saat için kullanılıp kullanılmayacağını belirtir.|`true`(için 12 saat biçimi), `false` (için 24 saat biçiminde)||  
|`timeZone`|Saat dilimi belirtir. En azından "UTC" her zaman desteklenir.|"UTC" gibi bir saat dilimi değeri.|"UTC"|  
|`weekday`|Haftanın günü biçimlendirme belirtir.|","kısa"daraltmak" "uzun".|Tanımlanmamış|  
|`era`|Dönem biçimlendirme belirtir.|"uzun", "kısa" daraltmak""|Tanımlanmamış|  
|`year`|Yılın biçimlendirme belirtir.|"2 basamaklı", "sayısal"|tanımlanmamış veya "sayısal"|  
|`month`|Ayın biçimlendirme belirtir.|"2-basamaklı", "sayısal", "dar", ","uzun"kısa"|tanımlanmamış veya "sayısal"|  
|`day`|Günün biçimlendirme belirtir.|"2 basamaklı", "sayısal"|tanımlanmamış veya "sayısal"|  
|`hour`|Saat biçimlendirme belirtir.|"2 basamaklı", "sayısal"|Tanımlanmamış|  
|`minute`|Dakikasını biçimlendirme belirtir.|"2 basamaklı", "sayısal"|Tanımlanmamış|  
|`second`|İkinci biçimlendirme belirtir.|"2 basamaklı", "sayısal"|Tanımlanmamış|  
|`timeZoneName`|Saat dilimini biçimlendirme belirtir. Bu özellik şu anda desteklenmiyor.|","uzun"kısa".|Bu özellik şu anda desteklenmiyor.|  
  
 İçin varsayılan değerler `weekday`, `era`, `year`, `month`, `day`, `hour`, `minute`, ve `second` olan `undefined`. Bu özellikleri ayarlamazsanız "sayısal" biçimlendirme için kullanılan `year`, `month`, ve `day`.  
  
 Her yerel ayar, en azından aşağıdaki biçimlerden desteklemesi gerekir:  
  
-   Haftanın günü, yıl, ay, gün, saat, dakika, saniye  
  
-   Haftanın günü, yıl, ay, gün  
  
-   Yıl, ay, gün  
  
-   Yıl, ay  
  
-   ay, gün  
  
-   saat, dakika, saniye  
  
-   saat, dakika  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `DateTimeFormat` nesnesi.  
  
|||  
|-|-|  
|Özellik|Açıklama|  
|[Oluşturucusu](../../javascript/reference/constructor-property-intl-datetimeformat.md)|Bir tarih/saat biçimlendirici nesnesi oluşturur işlevi belirtir.|  
|[biçimi](../../javascript/reference/format-property-intl-datetimeformat.md)|Tarih/saat biçimlendirici ayarlarını kullanarak yerel ayarlara özgü tarih biçimleri bir işlev döndürür.|  
|[prototip](../../javascript/reference/prototype-property-intl-datetimeformat.md)|Prototip başvuru için bir tarih/saat biçimlendirici döndürür.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `DateTimeFormat` nesnesi.  
  
|||  
|-|-|  
|Yöntem|Açıklama|  
|[resolvedOptions](../../javascript/reference/resolvedoptions-method-intl-datetimeformat.md)|Özellikleri ve tarih biçimlendirici nesnenin değerlerini içeren bir nesne döndürür.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir date nesnesi geçirme sonucunu gösterir `DateTimeFormat` farklı yerel ayarlara kullanma.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
if (console && console.log) {  
    console.log(new Intl.DateTimeFormat("en-US").format(date));  
    // Returns ‎2‎/‎1‎/‎2013  
    console.log(new Intl.DateTimeFormat("ja-JP").format(date));  
    // Returns ‎2013‎年‎2‎月‎1‎日  
    console.log(new Intl.DateTimeFormat("ar-SA", options).format(date));  
    // Returns ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
    console.log(new Intl.DateTimeFormat("hi-IN", options).format(date));  
    // Returns ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir `DateTimeFormat` Arapça (Suudi Arabistan) yerel ayar, İslam takvim ve sistem numaralandırma Latin kullanarak uzun biçiminde geçerli haftanın gününü belirtir nesnesi.  
  
```JavaScript  
var dtf = new Intl.DateTimeFormat(["ar-SA-u-ca-islamic-nu-latn"], {  
    weekday: "long",  
    year: "numeric",  
    day: "numeric",  
    month: "long"  
});   
  
If (console && console.log) {  
    console.log(dtf.format(new Date()));  
    // Returns ‏الجمعة‏, ‏19‏ ‏رمضان‏, ‏1434  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleString (tarih)](../../javascript/reference/tolocalestring-date.md)   
 [toLocaleDateString yöntemi (tarih)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)   
 [toLocaleTimeString yöntemi (tarih)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)   
 [INTL.collator nesnesi](../../javascript/reference/intl-collator-object-javascript.md)   
 [INTL.numberformat nesnesi](../../javascript/reference/intl-numberformat-object-javascript.md)