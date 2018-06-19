---
title: Tarih ve saat dizeleri (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba0798c5-3574-4434-89f4-3d90be276001
caps.latest.revision: 47
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6218ba273b26243382d1e825b6da961d604917ab
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789284"
---
# <a name="date-and-time-strings-javascript"></a>Tarih ve Saat Dizeleri (JavaScript)
Çeşitli teknikler ve biçim JavaScript tarih ve saat dizeleri belirtmek için kullanabilirsiniz.  
  
## <a name="formatting-dates-using-intldatetimeformat"></a>INTL.datetimeformat kullanarak tarihleri biçimlendirme  
 Internet Explorer 11 desteği tanıtır [INTL.datetimeformat nesnesi](../javascript/reference/intl-datetimeformat-object-javascript.md), parçası olduğu [ECMAScript uluslararası API belirtimine](http://www.ecma-international.org/ecma-402/1.0/). Tarihleri biçimlendirmek için doğrudan bu nesneyi kullanabilirsiniz veya güncelleştirilmiş uygulanması kullanabilirsiniz [toLocaleDateString yöntemi (tarih)](../javascript/reference/tolocaledatestring-method-date-javascript.md) ve [toLocaleTimeString yöntemi (tarih)](../javascript/reference/tolocaletimestring-method-date-javascript.md). Bu yöntemleri [tarih nesnesi](../javascript/reference/date-object-javascript.md) kullanmak `Intl.DateTimeFormat` yeni isteğe bağlı parametreler yerel ve diğer biçimlendirme seçenekleri için dahili olarak desteklemek için.  
  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `toLocaleDateString` ve `toLocaleTimeString` biçimi tarihler ve saatler için. Bu yönteme geçirilen ilk parametre bir yerel ayar değeri olduğu gibi "en-us". İkinci parametre mevcut olduğunda, haftanın günü için uzun formu gibi biçimlendirme seçeneklerini belirtir.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = {  
    weekday: "long", year: "numeric", month: "short",  
    day: "numeric", hour: "2-digit", minute: "2-digit"  
};  
  
document.write(date.toLocaleDateString("en-US"));  
document.write(date.toLocaleTimeString("en-us", options));  
document.write(date.toLocaleDateString("ja-JP"));  
document.write(date.toLocaleTimeString("ja-JP", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013  
// ‎Friday‎, ‎Feb‎ ‎1‎, ‎2013‎ ‎06‎:‎00‎ ‎AM  
// ‎2013‎年‎2‎月‎1‎日‎  
// ‎2013‎年‎2‎月‎1‎日 ‎金曜日‎ ‎06‎:‎00  
```  
  
 Biçimlendirme seçeneklerini tam listesi için bkz: [INTL.datetimeformat nesnesi](../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
## <a name="formatting-dates"></a>Tarihleri Biçimlendirme  
 Internet Explorer 11 önce JavaScript tarihler ve saatler biçimlendirmek için belirli yöntemler sahip değil. Kendi tarih önceki tarayıcı sürümleri için biçimlendirme sağlamak için kullanın [getDay yöntemi (tarih)](../javascript/reference/getday-method-date-javascript.md), [getDate yöntemi (tarih)](../javascript/reference/getdate-method-date-javascript.md), [getMonth yöntemi (tarih)](../javascript/reference/getmonth-method-date-javascript.md)ve [getFullYear yöntemi (tarih)](../javascript/reference/getfullyear-method-date-javascript.md) yöntemleri. ( [GetYear yöntemi (tarih)](../javascript/reference/getyear-method-date-javascript.md) kullanımdan kalkmıştır ve kullanılmamalıdır.)  
  
```JavaScript  
var myDate = new Date("February 3, 2001");  
var myDate = new Date("February 3 2001");  
document.write((myDate.getMonth() + 1) + "-" + myDate.getDate() + "-" + myDate.getFullYear());  
document.write("<br/>");  
document.write((myDate.getMonth() + 1) + "/" + myDate.getDate() + "/" + myDate.getFullYear());  
  
//Output:  
// 2-3-2001  
// 2/3/2001  
```  
  
 Kendi saat kullanarak biçimlendirme sağlayabilir [getHours yöntemi (tarih)](../javascript/reference/gethours-method-date-javascript.md), [getMinutes yöntemi (tarih)](../javascript/reference/getminutes-method-date-javascript.md), [getSeconds yöntemi (tarih)](../javascript/reference/getseconds-method-date-javascript.md), ve [ getMilliseconds yöntemi (tarih)](../javascript/reference/getmilliseconds-method-date-javascript.md) yöntemleri.  
  
```JavaScript  
myDate = new Date();  
myDate.setHours(10, 30, 53, 400);  
  
document.write(myDate.getHours() + ":" + myDate.getMinutes() + ":" + myDate.getSeconds() +   
":" + myDate.getMilliseconds());  
  
// Output:   
// 10:30:53:400  
```  
  
## <a name="converting-strings-to-dates"></a>Tarihleri dizeleri dönüştürme  
 Dizeleri oluşturulacağını belirtebilirsiniz `Date` biriyle nesneleri `Date(dateStr)` veya ile `Date.parse(dateStr)`. JavaScript tarih dizeleri ayrıştırma için aşağıdaki kuralları kullanır:  
  
-   Önce bir tarih dizesi kullanarak XML'in dener [ISO tarih biçimi](#ISO).  
  
    > [!NOTE]
    >  JavaScript ISO 8601 Genişletilmiş biçimi basitleştirilmiş bir sürümünü kullanıyor.  
  
-   Tarih dizesi ISO biçiminde değilse, diğer kullanarak tarih ayrıştırmak JavaScript çalışır [diğer tarih biçimleri](#OtherDateFormats).  
  
<a name="ISO"></a>   
## <a name="iso-date-format"></a>ISO Tarih Biçimi  
 ISO 8601 Genişletilmiş biçimi basitleştirme ISO biçimidir. Biçimi aşağıdaki gibidir:  
  
 `YYYY-MM-DDTHH:mm:ss.sssZ`  
  
> [!IMPORTANT]
>  ISO tarih biçimi, Internet Explorer 8 standartları modu ve Quirks modunda desteklenmiyor.  
  
 Aşağıdaki tabloda bu biçim bölümünü açıklar.  
  
|Simgesi|Açıklama|Değerler|  
|------------|-----------------|------------|  
|`-`, `:`, `.`, `T`|Gerçekte dizedeki karakter. `T`bir süre başlangıcını belirtir.||  
|`YYYY`|Yıl. Genişletilmiş bir yıl 4 rakamlı yıl yerine kullanılabilir. Daha fazla bilgi için bkz: [genişletilmiş yıl](../javascript/date-and-time-strings-javascript.md#bkmk_extend) bu konuda daha sonra.||  
|`MM`|Ay|01-12|  
|`DD`|Ayın günü|01-31|  
|`HH`|Saatleri|00 ila 24|  
|`mm`|dakika|00-59|  
|`ss`|Saniye sayısı. Saniye ve milisaniye birer belirtilmezse isteğe bağlıdır.|00-59|  
|`sss`|milisaniye|00-999|  
|`Z`|Bu konumda değer aşağıdakilerden biri olabilir. Değer belirtilmezse, UTC saati kullanılır.<br /><br /> -   `Z`UTC saati gösterir.<br />-   `+hh:mm`Giriş saati UTC saat sonra belirtilen uzaklık olduğunu gösterir.<br />-   `-hh:mm`Bu giriş saati UTC zamanından önce belirtilen uzaklık mutlak değerini gösterir.||  
  
 Dize aşağıdaki biçimlerden olduğu gibi yalnızca tarih içerebilir: `YYYY`, `YYYY-MM`, `YYYY-MM-DD`.  
  
 ISO biçiminde saat dilimi adlarını desteklemez. Kullanabileceğiniz `Z` konumu UTC saati uzaklık belirtin. Bir değer içermiyorsa `Z` getirin, UTC saat kullanılır.  
  
 Gece yarısından 00:00 veya önceki gün 24:00 kullanarak belirtebilirsiniz. Aynı zamanda aşağıdaki iki dizeyi belirtin: 2010-05-25T00:00 ve 2010-05-24T24:00.  
  
 ISO biçiminde bir tarih dönmek için kullanabileceğiniz [Toısostring yöntemi (tarih)](../javascript/reference/toisostring-method-date-javascript.md).  
  
<a name="bkmk_extend"></a>   
### <a name="extended-years"></a>Genişletilmiş Yıllar  
 Bir *genişletilmiş yıl* 4 basamak yerine 6 rakam sahiptir ve artı veya eksi işareti öneki. Genişletilmiş bir yıl örneğidir `+002010`, eşdeğer olduğu `2010`. Genişletilmiş bir yıl 0 yıl önce veya sonra 9999 yılları temsil etmek için kullanabilirsiniz.  
  
 6 rakamlı kullanırsanız biçimi, artı veya eksi işareti mevcut olması gerekir. 4 basamaklı biçim kullandığınızda, oturum mevcut olması gerekir. Bu nedenle, `0000` ve `+000000` kabul edilir, ancak `000000` ve `-0001` hataya neden. Pozitif ve bu nedenle önekli bir artı işareti olan Genişletilmiş yıl 0 olarak kabul edilir.  
  
 [Toısostring yöntemi (tarih)](../javascript/reference/toisostring-method-date-javascript.md) her zaman 0 önce ve sonra 9999 yıllık uzatılmış yıl biçimini kullanır.  
  
> [!NOTE]
>  [!INCLUDE[jsv9](../javascript/includes/jsv9-md.md)]  
  
<a name="OtherDateFormats"></a>   
## <a name="other-date-formats"></a>Diğer Tarih Biçimleri  
 Bir tarih dizesi ISO biçiminde değilse [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] onu ayrıştırmak için aşağıdaki kuralları kullanır.  
  
 Kısa tarih  
  
-   Biçim gün/ay/yıl sipariş, örneğin "06/08/2010" izlemeniz gerekir.  
  
-   Ya da "/" veya "-" ayırıcı olarak kullanılabilir.  
  
 Uzun tarih  
  
-   Yıl, ay ve gün herhangi bir sırada olabilir. "8 Haziran 2010" "2010 Haziran 8" hem de geçerli olması.  
  
-   Yılın iki veya dört basamak olabilir. Yılı yalnızca iki basamak varsa, en az 70 olması gerekir.  
  
-   Ay ve gün adları en az iki karakter olmalıdır. Eşleşen soyadına benzersiz olmayan iki karakter adları çözümlenir. Örneğin, "Ju" Temmuz, değil Haziran belirtir.  
  
-   Sağlanan tarih geri kalanı ile tutarsız olması durumunda haftanın bir günü göz ardı edilir. Örneğin, Cuma doğru için haftanın günü tarihi olduğundan "Salı Kasım 9 1996", "Cuma Kasım 9 1996" çözümler.  
  
 Saatleri  
  
-   Saat, dakika ve saniyeleri virgüllerle ayrılır. Ancak, bazı bölümlerinin atlanabilir. Geçerli bir şunlardır: "10:", "10:11" ve "10: 11:12".  
  
-   PM belirtildiğinden ve en az 13 belirtilen saat ise, NaN döndürülür. Örneğin, "23:15 PM" NaN döndürür.  
  
 Genel  
  
-   NaN geçersiz bir tarih içeren bir dize döndürür. Örneğin, iki yıl veya iki ay içeren bir dize NaN döndürür.  
  
-   [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]Tüm standart saat dilimleri ve Evrensel Eşgüdümlü saate (UTC) ve (GMT) Greenwich saati destekler. (ISO biçiminde saat dilimlerini desteklemez.)  
  
-   Parantez içindeki metin yorum olarak kabul edilir. Parantez iç içe.  
  
-   Virgül ve boşluk sınırlayıcı olarak kabul edilir. Birden çok sınırlayıcıları izin verilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod farklı tarih ve saat dizelerini ayrıştırma sonuçlarını görüntüler.  
  
```  
document.writeln((new Date("2010")).toUTCString());   
  
document.writeln((new Date("2010-06")).toUTCString());  
  
document.writeln((new Date("2010-06-09")).toUTCString());  
  
 // Specifies Z, which indicates UTC time.  
document.writeln((new Date("2010-06-09T15:20:00Z")).toUTCString());  
  
 // Specifies -07:00 offset, which is equivalent to Pacific Daylight time.  
document.writeln((new Date("2010-06-09T15:20:00-07:00")).toGMTString());  
  
// Specifies a non-ISO Long date.  
document.writeln((new Date("June 9, 2010")).toUTCString());  
  
// Specifies a non-ISO Long date.  
document.writeln((new Date("2010 June 9")).toUTCString());  
  
// Specifies a non-ISO Short date and time.  
document.writeln((new Date("6/9/2010 3:20 pm")).toUTCString());  
  
// Output:  
// Fri, 1 Jan 2010 00:00:00 UTC  
// Tue, 1 Jun 2010 00:00:00 UTC  
// Wed, 9 Jun 2010 00:00:00 UTC  
// Wed, 9 Jun 2010 15:20:00 UTC  
// Wed, 9 Jun 2010 22:20:00 UTC  
// Wed, 9 Jun 2010 07:00:00 UTC  
// Wed, 9 Jun 2010 07:00:00 UTC  
// Wed, 9 Jun 2010 22:20:00 UTC  
```  
  
 Yerel saat belirtilmedikçe sonucu saat dilimi bağlı olarak değişir.  
  
> [!IMPORTANT]
>  ISO tarih biçimi, Internet Explorer 8 standartları modu ve Quirks modunda desteklenmiyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih nesnesi](../javascript/reference/date-object-javascript.md)   
 [Date.Parse işlevi](../javascript/reference/date-parse-function-javascript.md)