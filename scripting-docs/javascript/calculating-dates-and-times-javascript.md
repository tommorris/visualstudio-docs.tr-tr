---
title: Tarihler ve saatleri hesaplama (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- date and time arithmetic [JavaScript]
- JavaScript, date and time
- date comparison [JavaScript]
- date and time calculations [JavaScript]
ms.assetid: ea976f78-d934-479b-9056-880390d8bddd
caps.latest.revision: "34"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 18b4ff307c8f2c48a37ed9ca50e7c5f1ff693ece
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="calculating-dates-and-times-javascript"></a>Tarihler ve Saatleri Hesaplama (JavaScript)
Kullanabileceğiniz [tarih nesnesi](../javascript/reference/date-object-javascript.md) tarihleri karşılaştırma ve geçen süre hesaplama gibi ortak takvimden ve saati görevleri gerçekleştirmek için.  
  
## <a name="setting-a-date-to-the-current-date"></a>Tarihi Geçerli Tarihe Ayarlama  
 Bir örneğini oluştururken [tarih nesnesi](../javascript/reference/date-object-javascript.md) bir tarih belirtmeden geçerli tarih ve saat yıl, ay, gün, saat, dakika, saniye ve milisaniye dahil olmak üzere, temsil eden bir değer döndürür. Ardından, okumak veya bu tarih ve saat değiştirin.  
  
 Aşağıdaki örnek, herhangi bir parametre kullanmadan bir tarih örneği ve biçimde görüntülemek gösterilmiştir *aa-gg-yy*.  
  
```JavaScript  
var dt = new Date();  
  
// Display the month, day, and year. getMonth() returns a 0-based number.  
var month = dt.getMonth()+1;  
var day = dt.getDate();  
var year = dt.getFullYear();  
document.write(month + '-' + day + '-' + year);  
  
// Output: current month, day, year  
```  
  
## <a name="setting-a-specific-date"></a>Belirli Bir Tarihi Ayarlama  
 Bir tarih dizesi oluşturucusuna geçirerek, belirli bir tarih ayarlayabilirsiniz.  
  
```JavaScript  
var dt = new Date('8/24/2009');  
document.write(dt);  
  
// Output: Mon Aug 24 00:00:00 PDT 2009  
  
```  
  
> [!IMPORTANT]
>  Tarih dizesinde görüntülenen saat dilimi, yerel makine üzerinde ayarlanan saat dilimini karşılık gelir.  
>   
>  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]parametre olarak kullandığınız dizesinin biçimi hakkında esnektir. Örneğin, "8-24-2009", "24 Ağustos 2009", veya "24 Ağu 2009" girebilirsiniz.  
  
 Ayrıca, bir süre belirtebilirsiniz. Aşağıdaki örnek, bir tarih ve saat ISO biçiminde belirtmek için bir yol gösterir. "Z" UTC saati gösterir.  
  
```JavaScript  
var dt = new Date('2010-06-09T15:20:00Z');  
document.write(dt);  
document.write("<br />");  
document.write(dt.toISOString());  
  
// Output:  
// Wed Jun 09 2010 08:20:00 GMT-0700 (Pacific Daylight Time)  
// 2010-06-09T15:20:00.000Z  
```  
  
 ISO gibi tarih biçimleri hakkında daha fazla bilgi için bkz: [tarih ve saat dizelerini](../javascript/date-and-time-strings-javascript.md).  
  
 Aşağıdaki örnek, bir saat belirtmek üzere diğer yolları gösterir.  
  
```JavaScript  
var dtA = new Date('8/24/2009 14:52:10');  
  
// The parameters are year, month, day, hours, minutes, seconds.  
var dtB = new Date(2009, 7, 24, 14, 52, 10);  
document.write(dtA);  
document.write("<br/>");  
document.write(dtB);  
  
// Output:  
// Mon Aug 24 14:52:10 PDT 2009  
// Mon Aug 24 14:52:10 PDT 2009  
  
```  
  
## <a name="adding-and-subtracting-days-months-and-years"></a>Gün, Ay ve Yıl Ekleme ve Çıkarma  
 GetX ve setX yöntemlerini kullanabilirsiniz `Date` nesne belirli tarih ve saatleri ayarlayın.  
  
 Aşağıdaki örnek, önceki gün için bir tarih nasıl ayarlayabileceğiniz gösterir. Gerekirse, ay ve yıl değerleri de değiştiğine dikkat edin.  
  
```JavaScript  
var myDate = new Date("1/1/1990");  
var dayOfMonth = myDate.getDate();  
myDate.setDate(dayOfMonth - 1);  
  
document.write(myDate);  
  
// Output: Sun Dec 31 00:00:00 PST 1989  
```  
  
 Aşağıdaki örnek, günde bir sonraki ayın ilk gününden çıkarılmasıyla, ayın son günü tarihini ayarlar.  
  
> [!TIP]
>  Yılın ay 0 (Ocak) ile 11 (aralık) numaralandırılır. Haftanın günleri (Pazar) 0 ile 6 (Cumartesi) numaralandırılır.  
  
```JavaScript  
var myDate = new Date("1/1/1990")  
myDate.setMonth(myDate.getMonth() + 1);  
  
myDate.setDate (myDate.getDate() - 1);  
  
document.write(myDate);  
  
// Output: Wed Jan 31 00:00:00 PST 1990  
  
```  
  
## <a name="working-with-days-of-the-week"></a>Haftanın Günleriyle Çalışma  
 [GetDay yöntemi](../javascript/reference/getday-method-date-javascript.md) 0 (Pazar) ve 6 (Cumartesi) arasında bir sayı olarak haftanın gününü alır. (Bu aynı değil [getDate yöntemi](../javascript/reference/getdate-method-date-javascript.md), 1 ile 31 arasında bir sayı olarak ayın günü alır).  
  
 Aşağıdaki örnek, Amerika Birleşik Devletleri'nde Kasım içinde dördüncü Perşembe Şükran tarihini ayarlar. Komut dosyası, geçerli yılın 1 Kasım bulur sonra ilk Perşembe bulur ve üç hafta ekler.  
  
```JavaScript  
var myDate = new Date();  
myDate.setHours(0, 0, 0, 0);  
  
myDate.setYear(2013);  
  
// Determine November 1.  
myDate.setDate(1);  
myDate.setMonth(10);  
  
// Find Thursday.  
var thursday = 4;  
while(myDate.getDay() != thursday) {  
    myDate.setDate(myDate.getDate() + 1);  
}  
  
// Add 3 weeks.  
myDate.setDate(myDate.getDate() + 21);  
  
document.write(myDate);  
  
// Output: Thu Nov 28 00:00:00 <time zone> 2013  
  
```  
  
## <a name="calculating-elapsed-time"></a>Geçen Süreyi Hesaplama  
 [GetTime yöntemi](../javascript/reference/gettime-method-date-javascript.md) 1 Ocak 1970'ten gece yarısından beri geçen milisaniye sayısını döndürür. Bu tarihten önce herhangi bir tarihi için negatif bir sayı döndürür.  
  
 Kullanabileceğiniz [getTime yöntemi](../javascript/reference/gettime-method-date-javascript.md) geçen süreyi hesaplamak için başlangıç ve bitiş saati ayarlamak için. Bu işlem birkaç saniye bekleyip gün gibi büyük birimleri gibi küçük birimler ölçmek üzere kullanılabilir.  
  
 Aşağıdaki örnekte geçen sürenin saniye cinsinden hesaplar. [GetTime yöntemi](../javascript/reference/gettime-method-date-javascript.md) sıfır tarihten bu yana milisaniye sayısını alır.  
  
```JavaScript  
var startTime = new Date('1/1/1990');  
var startMsec = startTime.getMilliseconds();  
startTime.setTime(5000000);  
var elapsed = (startTime.getTime() - startMsec) / 1000;   
document.write(elapsed);  
  
// Output: 5000  
  
```  
  
 Daha kolay yönetilebilir birimler ile çalışmak için sağladığı milisaniye bölebilirsiniz [getTime yöntemi](../javascript/reference/gettime-method-date-javascript.md) uygun bir sayı olarak. Örneğin, milisaniye gün içinde açmak için numarası 86,400,000 (60 saniye x 24 saat x 60 dakika x 1000 milisaniye) bölün.  
  
 Aşağıdaki örnek, belirtilen yılın ilk günü itibaren ne kadar süre gösterir. Bölme işlemleri, gün, saat, dakika ve saniye geçen süreyi hesaplamak için kullanır. Günışığından yararlanma saatine hesaplamaz.  
  
```JavaScript  
// Set the unit values in milliseconds.  
var msecPerMinute = 1000 * 60;  
var msecPerHour = msecPerMinute * 60;  
var msecPerDay = msecPerHour * 24;  
  
// Set a date and get the milliseconds  
var date = new Date('6/15/1990');  
var dateMsec = date.getTime();  
  
// Set the date to January 1, at midnight, of the specified year.  
date.setMonth(0);  
date.setDate(1);  
date.setHours(0, 0, 0, 0);  
  
// Get the difference in milliseconds.  
var interval = dateMsec - date.getTime();  
  
// Calculate how many days the interval contains. Subtract that  
// many days from the interval to determine the remainder.  
var days = Math.floor(interval / msecPerDay );  
interval = interval - (days * msecPerDay );  
  
// Calculate the hours, minutes, and seconds.  
var hours = Math.floor(interval / msecPerHour );  
interval = interval - (hours * msecPerHour );  
  
var minutes = Math.floor(interval / msecPerMinute );  
interval = interval - (minutes * msecPerMinute );  
  
var seconds = Math.floor(interval / 1000 );  
  
// Display the result.  
document.write(days + " days, " + hours + " hours, " + minutes + " minutes, " + seconds + " seconds.");  
  
//Output: 164 days, 23 hours, 0 minutes, 0 seconds.  
```  
  
### <a name="determining-the-users-age"></a>Kullanıcının Yaşını Belirleme  
 Aşağıdaki örnek, kullanıcının Doğum günü alır ve kullanıcının yaş yıllarda hesaplar. Geçerli yıl Doğum year çıkarır ve doğum günü henüz geçerli yıl içinde gerçekleştirilmediyse 1 çıkarır.  
  
```JavaScript  
var birthday = new Date("8/1/1985");  
var today = new Date();  
var years = today.getFullYear() - birthday.getFullYear();  
  
// Reset birthday to the current year.  
birthday.setFullYear(today.getFullYear());  
  
// If the user's birthday has not occurred yet this year, subtract 1.  
if (today < birthday)  
{  
    years--;  
}  
document.write("You are " + years + " years old.");  
  
// Output: You are <number of years> years old.  
  
```  
  
## <a name="comparing-dates"></a>Tarih Karşılaştırma  
 Tarihleri karşılaştırmak zaman [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], göz önünde bulundurmanız gereken, `==` operatörü döndürür `true` yalnızca işlecinin iki tarafı da tarihler de aynı nesneye başvuruda bulunuyorsa. Bu nedenle, iki ayrı varsa `Date` aynı tarihe, küme nesneleri `date1 == date2` döndürür `false`. Ayrıca, bir `Date` yalnızca tarihi ve saati ile ayarlanmış nesnesi, bu tarih gece yarısına başlatılır. Böyle bir karşılaştırırsanız `Date` belirli bir süre olmadan ayarlamak `Date.now`, örneğin, farkında olmalıdır, ilk `Date` gece yarısına ayarlanmış ve `Date.now` değil.  
  
 Aşağıdaki örnek geçerli tarih aynı önce ya da belirli bir tarihten sonra olup olmadığını denetler. Geçerli tarihi ayarlamak için `todayAtMidn`, komut dosyası oluşturur bir `Date` nesne geçerli yıl, ay ve gün için.  
  
```JavaScript  
// Get the current date at midnight.  
var now = new Date();   
var todayAtMidn = new Date(now.getFullYear(), now.getMonth(), now.getDate());  
  
// Set specificDate to a specified date at midnight.  
var specificDate = new Date("9/21/2009");  
  
// Compare the two dates by comparing the millisecond  
// representations.  
if (todayAtMidn.getTime() == specificDate.getTime())  
{  
    document.write("Same");  
}  
else  
{  
    document.write("Different");  
}  
  
//Output: Different  
```  
  
 Önceki örnekte değiştirerek, biz sağlanan tarih belirli bir aralık içinde olup olmadığını denetleyebilirsiniz.  
  
```JavaScript  
// Get the current date at midnight.  
var now = new Date();  
var todayAtMidn = new Date(now.getFullYear(), now.getMonth(), now.getDate());  
  
// Set start/end dates to a specified date (ISO format).  
var startDate = new Date("2009-06-09T15:20:00Z");  
var endDate = new Date("2011-06-09T15:20:00Z");  
  
// Compare the two dates by comparing the millisecond  
// representations.  
if (todayAtMidn.getTime() > startDate.getTime() &&   
    todayAtMidn.getTime() < endDate.getTime()) {  
    document.write("Specified date is within this range.");  
}  
else {  
    document.write("Specified date is not in this range.");  
}  
  
// Output: Specified date is not in this range.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih nesnesi](../javascript/reference/date-object-javascript.md)