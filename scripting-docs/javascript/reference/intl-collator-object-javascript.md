---
title: INTL.collator nesnesi (JavaScript) | Microsoft Docs
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
- Collator
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: acbb9461-f956-4b5b-ae5f-6a47815ae15c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9a41507face20285124257be95197ef5ea53ef6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="intlcollator-object-javascript"></a>Intl.Collator Nesnesi (JavaScript)
Yerel ayarlara özgü dize karşılaştırmaları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
collatorObj = new Intl.Collator([locales][, options])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `collatorObj`  
 Gerekli. Değişken adı atamak için `Collator` için nesne.  
  
 `locales`  
 İsteğe bağlı. Bir veya daha fazla dil veya yerel ayar etiketlerini içeren bir yerel dizeler dizisi. Birden fazla yerel ayar dizesi eklerseniz, bunları böylece ilk giriş tercih edilen yerel öncelik sırasına göre azalan sırada listeleyin. Bu parametresini atlarsanız, varsayılan yerel ayar JavaScript çalışma zamanı kullanılır. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 `options`  
 İsteğe bağlı. Karşılaştırma seçenekleri belirten bir veya daha fazla özellikleri içeren bir nesne. Ayrıntılar için Açıklamalar bölümüne bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 `locales` Parametresi için uygun olmalıdır [BCP 47](http://tools.ietf.org/html/rfc5646) dilini veya yerel ayarını etiketleri "en-US" ve "atanır-zh-CN" gibi. Etiket dil, bölge, ülke ve değişken içerebilir. Dillerin bir listesi için bkz: [IANA dil alt etiket kayıt defteri](http://go.microsoft.com/fwlink/p/?linkid=227303). Dil etiketleri örnekleri için bkz: [ek A](http://tools.ietf.org/html/rfc5646#appendix-A) BCP 47. İçin `Collator`, bir veya daha fazla aşağıdaki Unicode uzantılarını belirtmek için yerel ayar dizesinde -u uzantısı içerebilir:  
  
-   -değişken harmanlamaları (yerel ayarlara özgü) belirtmek için ortak: "*dil*-*bölge*-u-ortak*değeri*".  
  
-   -sayısal bir karşılaştırma belirtin kn: "*dil*-*bölge*- u kn true &#124; false".  
  
-   -büyük veya küçük harf karakterler sıralamanız belirtmek için kf: "*dil*-*bölge*- u kf üst &#124; alt &#124; false"). Bu uzantı şu anda desteklenmiyor.  
  
 Sayısal bir karşılaştırma belirtmek için -kn uzantısı yerel ayar dizesinde ayarlayabilir veya kullanmak `numeric` özelliğinde `options` parametresi. Kullanıyorsanız, `numeric` özelliği, -kn değeri uygulanmayacağı.  
  
 `options` Parametresi, aşağıdaki özellikler içerebilir:  
  
-   `localeMatcher`. Kullanılacak yerel ayar eşleştirme algoritması belirtir. Olası değerler şunlardır: "Ara" ve "en uygun". "En iyi sığacak şekilde" varsayılan değerdir.  
  
-   `usage`. Karşılaştırma amacı sıralama veya arama olup olmadığını belirtir. Olası değerler şunlardır: "sıralama" ve "Ara". "Sıralama" varsayılan değerdir.  
  
-   `sensitivity`. Harmanlama'nın duyarlılığını belirtir. Olası değerler şunlardır: "temel", "Aksan", "Durum" ve "değişken". Varsayılan değer `undefined` şeklindedir.  
  
-   `ignorePunctuation`. Noktalama işaretleri Karşılaştırmada göz ardı olup olmadığını belirtir. Olası değerler şunlardır: "true" ve "false". Varsayılan değer `false` şeklindedir.  
  
-   `numeric`. Sayısal sıralama kullanılıp kullanılmayacağını belirtir. Olası değerler şunlardır: "true" ve "false". Varsayılan değer `false` şeklindedir.  
  
-   `caseFirst`. Şu anda desteklenmiyor.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `Collator` nesnesi.  
  
|||  
|-|-|  
|Özellik|Açıklama|  
|[Karşılaştırma](../../javascript/reference/compare-property-intl-collator.md)|İki dizeyi harmanlama'nın sıralama kullanarak karşılaştıran bir işlev döndürür.|  
|[Oluşturucusu](../../javascript/reference/constructor-property-intl-collator.md)|Bir harmanlama oluşturur işlevi belirtir.|  
|[prototip](../../javascript/reference/prototype-property-intl-collator.md)|Prototip başvuru için bir harmanlama döndürür.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Collator` nesnesi.  
  
|||  
|-|-|  
|Yöntem|Açıklama|  
|[resolvedOptions](../../javascript/reference/resolvedoptions-method-intl-collator.md)|Özellikleri ve harmanlama değerleri içeren bir nesne döndürür.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir `Collator` nesne ve bir karşılaştırma gerçekleştirir.  
  
```JavaScript  
var co = new Intl.Collator(["de-DE"]);  
co.compare("a", "b"); // Returns -1  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Collator` bir dizi sıralamak için nesneleri. Bu örnek, yerel ayarlara özgü farklılıkları gösterir.  
  
```JavaScript  
var co1 = new Intl.Collator(["de-DE-u-co-phonebk"]);  
var co2 = new Intl.Collator(["de-DE"]);  
var co3 = new Intl.Collator(["en-US"]);  
  
var arr = ["ä", "ad", "af", "a"];  
  
if (console && console.log) {  
    console.log(arr.sort(co1.compare));  // Returns a,ad,ä,af  
    console.log(arr.sort(co2.compare));  // Returns a,ä,ad,af  
    console.log(arr.sort(co3.compare));  // Returns a,ä,ad,af  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanan bir `Collator` bir dize aramak için nesne ve karşılaştırma seçeneklerini belirtir.  
  
```JavaScript  
// String to search  
var arr = ["ä", "ad", "af", "a"];  
// String searched for  
var s = "af";  
  
var co = new Intl.Collator("de-DE", { usage: "search" });  
var matches = arr.filter(function (i) {  
    return co.compare(i, s) === 0;  
});  
  
if (console && console.log) {  
    console.log(matches);  // Returns af  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [localeCompare yöntemi (dize)](../../javascript/reference/localecompare-method-string-javascript.md)   
 [INTL.datetimeformat nesnesi](../../javascript/reference/intl-datetimeformat-object-javascript.md)   
 [INTL.numberformat nesnesi](../../javascript/reference/intl-numberformat-object-javascript.md)