---
title: INTL.numberformat nesnesi (JavaScript) | Microsoft Docs
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
- NumberFormat
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 820bc90f-f1e7-457a-b90d-487dfc3a736d
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0dcb02dbe0d7a7eef88750c440a4fbcdde3ea7ee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791549"
---
# <a name="intlnumberformat-object-javascript"></a>Intl.NumberFormat Nesnesi (JavaScript)
Yerel ayarlara özgü sayı biçimlendirmesini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
numberFormatObj = new Intl.NumberFormat([locales][, options])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `numberFormatObj`  
 Gerekli. Değişken adı atamak için `NumberFormat` için nesne.  
  
 `locales`  
 İsteğe bağlı. Bir veya daha fazla dil veya yerel ayar etiketlerini içeren bir yerel dizeler dizisi. Birden fazla yerel ayar dizesi eklerseniz, bunları böylece ilk giriş tercih edilen yerel öncelik sırasına göre azalan sırada listeleyin. Bu parametresini atlarsanız, varsayılan yerel ayar JavaScript çalışma zamanı kullanılır. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 `options`  
 İsteğe bağlı. Sayı biçimlendirme seçeneklerini belirten bir veya daha fazla özellikleri içeren bir nesne. Ayrıntılar için Açıklamalar bölümüne bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 `locales` Parametresi için uygun olmalıdır [BCP 47](http://tools.ietf.org/html/rfc5646) dilini veya yerel ayarını etiketleri "en-US" ve "zh-CN" gibi. Etiket dil, bölge, ülke ve değişken içerebilir. Dil etiketleri örnekleri için bkz: [ek A](http://tools.ietf.org/html/rfc5646#appendix-A) BCP 47. İçin `NumberFormat`, eklediğiniz **-u** alt etiket ve ardından bir numaralandırma sistemi uzantısı belirtmek için-nu:  
  
 "*dil*-*bölge*-u-b -*numberingsystem*"  
  
 Burada *numberingsystem* şunlardan biri olabilir: Arap, arabext, bali, beng, deva, fullwide, gujr, Ustası, hanidec, khmr, knda, laoo, latn, yanlış, mylm, mong, mymr, orya, tamldec, telu, Tay dili, tibt.  
  
 `options` Parametresi, aşağıdaki özellikler içerebilir:  
  
|Özellik|Açıklama|Olası değerler|Varsayılan değer|  
|--------------|-----------------|---------------------|-------------------|  
|`localeMatcher`|Kullanılacak yerel ayar eşleştirme algoritması belirtir.|"" en uygun"araması"|"en iyi sığacak şekilde"|  
|`style`|Numara biçimi stilini belirtir.|"ondalık", "yüzdesi", "para"|"ondalık"|  
|`currency`|ISO 4217 para birimi değeri alfabetik kod belirtir. Varsa `style` ayarlanır "para birimi" Bu değer gereklidir.|ISO bkz [para birimi ve fon kod listesi](http://www.currency-iso.org/en/home/tables/table-a1.html).|Tanımlanmamış|  
|`currencyDisplay`|Para biriminin ISO 4217 alfabetik para birimi kodu, yerelleştirilmiş para birimi simgesini ya da bir yerelleştirilmiş para birimi ad görüntülenip görüntülenmeyeceğini belirtir. Bu değer yalnızca kullanılır `style` "para" ayarlanır.|"code", "simgesi", "name"|"simgesi"|  
|`useGrouping`|Gruplandırma ayırıcı kullanılması gerekip gerekmediğini belirtir.|TRUE, false|`true`.|  
|`minimumIntegerDigits`|Kullanılacak tam sayı basamak sayısı alt sınırını belirtir.|1 ile 21.|21|  
|`minimumFractionDigits`|biçimindeki telefon numarasıdır. Kullanılacak kesirli basamak sayısı alt sınırını belirtir.|0 ila 20.|0|  
|`maximumFractionDigits`|Kullanılacak kesir basamakları en fazla sayısını belirtir.|Bu değer değişebilir `minimumFractionDigits` 20.|20.|  
|`minimumSignificantDigits`|Gösterilecek kesirli basamak sayısı alt sınırını belirtir.|Bu değer 1'den 21 ila arasında değişebilir.|1.|  
|`maximumSignificantDigits`|Kesir basamakları gösterilecek en fazla sayısını belirtir.|Bu değer değişebilir `minimumSignificantDigits` 21 için.|21|  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `NumberFormat` nesnesi.  
  
|||  
|-|-|  
|Özellik|Açıklama|  
|[Oluşturucusu](../../javascript/reference/constructor-property-intl-numberformat.md)|Sayı bir biçimlendirici oluşturur işlevi belirtir.|  
|[biçimi](../../javascript/reference/format-property-intl-numberformat.md)|Sayı biçimlendirici ayarları kullanarak bir sayıyı biçimlendirir bir işlev döndürür.|  
|[prototip](../../javascript/reference/prototype-property-intl-numberformat.md)|Prototip başvuru numarası bir biçimlendirici döndürür.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `NumberFormat` nesnesi.  
  
|||  
|-|-|  
|Yöntem|Açıklama|  
|[resolvedOptions](../../javascript/reference/resolvedoptions-method-intl-numberformat.md)|Özellikleri ve sayı biçimlendirici nesnenin değerlerini içeren bir nesne döndürür.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir `NumberFormat` nesnesi ile belirtilen biçimlendirme seçenekleri en-US yerel için.  
  
```JavaScript  
var nf = new Intl.NumberFormat(["en-US"], {  
    style: "currency",  
    currency: "CNY",  
    currencyDisplay: "symbol",  
    maximumFractionDigit: 1  
});  
  
if (console && console.log) {  
    console.log(nf.format(100)); // Returns ¥100.00  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler birkaç farklı yerel ayarlara ve seçenekleri kullanarak sonucu gösterir.  
  
```JavaScript  
var number = 123456789;  
var options1 = { style: "percent" };  
var options2 = { style: "currency", currency: "INR" };  
  
if (console && console.log) {  
    console.log(new Intl.NumberFormat("en-US").format(number));  
    // Returns 123,456,789  
    console.log(new Intl.NumberFormat("ja-JP").format(number));  
    // Returns 123,456,789  
    console.log(new Intl.NumberFormat("ar-SA", options1).format(number));  
    // Returns ١٢,٣٤٥,٦٧٨,٩٠٠ %  
    console.log(new Intl.NumberFormat("hi-IN", options2).format(number));  
    // Returns ₹ 12,34,56,789.00  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [toLocaleString (sayı)](../../javascript/reference/tolocalestring-number.md)   
 [INTL.collator nesnesi](../../javascript/reference/intl-collator-object-javascript.md)   
 [INTL.datetimeformat nesnesi](../../javascript/reference/intl-datetimeformat-object-javascript.md)