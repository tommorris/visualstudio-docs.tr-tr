---
title: Tarih nesnesi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Date
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, determining
ms.assetid: ce2202bb-7ec9-4f5a-bf48-3a04feff283e
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb5d53f3bddfeb3a3ed1ab36e2b4be822964eba5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="date-object-javascript"></a>Tarih Nesnesi (JavaScript)
Temel depolama ve tarihler ve saatler alınmasını sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      dateObj = new Date()  
dateObj = new Date(dateVal)  
dateObj = new Date(year, month, date[, hours[, minutes[, seconds[,ms]]]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `dateObj`  
 Gerekli. Değişken adına `Date` nesne atanır.  
  
 `dateVal`  
 Gerekli. Sayısal bir değer varsa, `dateVal` gece 1 Ocak 1970'ten ve belirtilen tarih arasında Evrensel Eşgüdümlü saate milisaniye sayısını temsil eder. Bir dize ise, `dateVal` yer alan kurallara uygun ayrıştırılır [tarih ve saat dizelerini](../../javascript/date-and-time-strings-javascript.md). `dateVal` Bazı ActiveX nesnelerden döndürülen bağımsız değişkeni VT_DATE değer de olabilir.  
  
 `year`  
 Gerekli. Tam yıl için 1976 (ve değil 76).  
  
 `month`  
 Gerekli. 0 ve 11 (Ocak-Aralık) arasında bir tamsayı olarak ay.  
  
 `date`  
 Gerekli. 1 ile 31 arasında bir tamsayı olarak tarih.  
  
 `hours`  
 İsteğe bağlı. Sağlanması gereken `minutes` sağlanır. Saati belirten bir tamsayı 0 ile 23 (11 pm gece yarısı).  
  
 dakika  
 İsteğe bağlı. Sağlanması gereken `seconds` sağlanır. Dakika cinsinden belirten bir tamsayı 0 ile 59.  
  
 `seconds`  
 İsteğe bağlı. Sağlanması gereken `milliseconds` sağlanır. Saniye belirten bir tamsayı 0 ile 59.  
  
 `ms`  
 İsteğe bağlı. Milisaniye olarak belirten bir tamsayı 0 ila 999 arasında.  
  
## <a name="remarks"></a>Açıklamalar  
 A `Date` nesne için bir süre içinde bir milisaniye içinde belirli bir anlık gösteren bir sayı içerir. Bağımsız değişken değeri kendi aralığından daha büyük ya negatif bir sayı ise, diğer depolanan değerleri uygun şekilde değiştirilmiştir. Örneğin, 150 saniye belirtirseniz [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] bu sayıyı iki dakika ile 30 saniye yeniden tanımlamaktadır.  
  
 Sayı ise `NaN`, nesne belirli bir anlık süreyi temsil etmiyor. Hiçbir parametre geçirirseniz `Date` nesne, geçerli saat (UTC) başlatılır. Kullanabilmeniz için önce nesne için bir değer verilmesi gerekir.  
  
 ' De temsil tarih aralığına göre bir `Date` yaklaşık 285,616 yıl 1 Ocak 1970'ten her iki tarafında bir nesnedir.  
  
 Bkz: [hesaplama tarihler ve saatler (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md) nasıl kullanılacağı hakkında daha fazla bilgi için `Date` nesne ve ilgili yöntemleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Date` nesnesi.  
  
```JavaScript  
var dateString = "Today's date is: ";  
  
var newDate = new Date();  
  
// Get the month, day, and year.  
dateString += (newDate.getMonth() + 1) + "/";  
dateString += newDate.getDate() + "/";  
dateString += newDate.getFullYear();  
  
document.write(dateString);  
  
// Output: Today's date is: <date>  
```  
  
## <a name="requirements"></a>Gereksinimler  
 `Date object` Sunulmuştur [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)]. Aşağıdaki listelerin bazı üyeleri daha sonraki sürümlerde eklendi. Daha fazla bilgi için bkz: [sürüm bilgilerini](../../javascript/reference/javascript-version-information.md) veya tek tek üyeleri belgelerine.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `Date Object`.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[constructor özelliği](../../javascript/reference/constructor-property-date.md)|Bir nesneyi oluşturan işlevi belirtir.|  
|[prototype özelliği](../../javascript/reference/prototype-property-date.md)|Bir nesne sınıfı için prototipe bir başvuru döndürür.|  
  
## <a name="functions"></a>İşlevler  
 Aşağıdaki tabloda işlevlerini listeler `Date Object`.  
  
|İşlevler|Açıklama|  
|---------------|-----------------|  
|[Date.Now işlevi](../../javascript/reference/date-now-function-javascript.md)|1 Ocak 1970 arasındaki milisaniye sayısını döndürür ve geçerli tarih ve saat.|  
|[Date.Parse işlevi](../../javascript/reference/date-parse-function-javascript.md)|Tarih içeren bir dize ayrıştırır ve bu tarih ve gece, 1 Ocak 1970'ten arasındaki milisaniye sayısını döndürür.|  
|[Date.UTC işlevi](../../javascript/reference/date-utc-function-javascript.md)|Gece yarısından, 1 Ocak 1970'ten arasındaki milisaniye sayısını döndürür (veya GMT) Evrensel Eşgüdümlü saate (UTC) ve sağlanan tarih.|  
  
<a name="js56jsobjdatemeth"></a>   
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Date Object`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[getDate yöntemi](../../javascript/reference/getdate-method-date-javascript.md)|Yerel saat kullanarak gün ay değeri döndürür.|  
|[getDay yöntemi](../../javascript/reference/getday-method-date-javascript.md)|Yerel saat kullanarak haftanın günü değeri döndürür.|  
|[getFullYear yöntemi](../../javascript/reference/getfullyear-method-date-javascript.md)|Yerel saat kullanarak yıl değerini döndürür.|  
|[getHours yöntemi](../../javascript/reference/gethours-method-date-javascript.md)|Yerel saat kullanarak saat değeri döndürür.|  
|[getMilliseconds yöntemi](../../javascript/reference/getmilliseconds-method-date-javascript.md)|Yerel saat kullanarak milisaniye değeri döndürür.|  
|[getMinutes yöntemi](../../javascript/reference/getminutes-method-date-javascript.md)|Yerel saat kullanarak dakika değerini döndürür.|  
|[getMonth yöntemi](../../javascript/reference/getmonth-method-date-javascript.md)|Yerel saat kullanarak ay değeri döndürür.|  
|[getSeconds yöntemi](../../javascript/reference/getseconds-method-date-javascript.md)|Yerel saat kullanarak saniye değerini döndürür.|  
|[getTime yöntemi](../../javascript/reference/gettime-method-date-javascript.md)|Süre değeri döndürür bir `Date` nesnesi olarak gece 1 Ocak 1970'ten itibaren milisaniye sayısı.|  
|[getTimezoneOffset yöntemi](../../javascript/reference/gettimezoneoffset-method-date-javascript.md)|Dakika cinsinden zaman ana bilgisayarda ve Evrensel Eşgüdümlü saate (UTC) arasındaki farkı döndürür.|  
|[getUTCDate yöntemi](../../javascript/reference/getutcdate-method-date-javascript.md)|UTC kullanılarak gün ay değeri döndürür.|  
|[getUTCDay yöntemi](../../javascript/reference/getutcday-method-date-javascript.md)|UTC kullanılarak haftanın günü değeri döndürür.|  
|[getUTCFullYear yöntemi](../../javascript/reference/getutcfullyear-method-date-javascript.md)|UTC ile yıl değerini döndürür.|  
|[getUTCHours yöntemi](../../javascript/reference/getutchours-method-date-javascript.md)|UTC kullanılarak saat değeri döndürür.|  
|[getUTCMilliseconds yöntemi](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)|UTC kullanılarak milisaniye değeri döndürür.|  
|[getUTCMinutes yöntemi](../../javascript/reference/getutcminutes-method-date-javascript.md)|UTC kullanarak dakika değerini döndürür.|  
|[getUTCMonth yöntemi](../../javascript/reference/getutcmonth-method-date-javascript.md)|UTC kullanılarak ay değeri döndürür.|  
|[getUTCSeconds yöntemi](../../javascript/reference/getutcseconds-method-date-javascript.md)|Saniye UTC kullanılarak değeri döndürür.|  
|[getVarDate yöntemi](../../javascript/reference/getvardate-method-date-javascript.md)|VT_DATE değeri döndüren bir `Date` nesnesi.|  
|[getYear yöntemi](../../javascript/reference/getyear-method-date-javascript.md)|Yıl değerini döndürür.|  
|[hasOwnProperty yöntemi](../../javascript/reference/hasownproperty-method-object-javascript.md)|Bir nesnenin belirtilen adda bir özelliği olup olmadığını belirten bir Boolean değer döndürür.|  
|[isPrototypeOf yöntemi](../../javascript/reference/isprototypeof-method-object-javascript.md)|Bir nesnenin başka bir nesnenin prototip zincirinde mevcut olup olmadığını belirten bir Boolean değer döndürür.|  
|[Propertyısenumerable yöntemi](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Belirtilen bir özelliğin bir nesnenin parçası olup olmadığını ve numaralandırılabilir olup olmadığını belirten bir Boolean değer döndürür.|  
|[setDate yöntemi](../../javascript/reference/setdate-method-date-javascript.md)|Yerel saat kullanarak ayın sayısal günü ayarlar.|  
|[setFullYear yöntemi](../../javascript/reference/setfullyear-method-date-javascript.md)|Yerel saat kullanarak yıl değerini ayarlar.|  
|[setHours yöntemi](../../javascript/reference/sethours-method-date-javascript.md)|Yerel saat kullanarak saat değerini ayarlar.|  
|[setMilliseconds yöntemi](../../javascript/reference/setmilliseconds-method-date-javascript.md)|Yerel saat kullanarak milisaniye değerini ayarlar.|  
|[setMinutes yöntemi](../../javascript/reference/setminutes-method-date-javascript.md)|Yerel saat kullanarak dakika değerini ayarlar.|  
|[setMonth yöntemi](../../javascript/reference/setmonth-method-date-javascript.md)|Yerel saat kullanarak ay değeri ayarlar.|  
|[setSeconds yöntemi](../../javascript/reference/setseconds-method-date-javascript.md)|Saniye değeri yerel saat kullanarak ayarlar.|  
|[setTime yöntemi](../../javascript/reference/settime-method-date-javascript.md)|Tarih ve saat değeri ayarlar `Date` nesnesi.|  
|[setUTCDate yöntemi](../../javascript/reference/setutcdate-method-date-javascript.md)|Sayısal ayın UTC kullanarak ayarlar.|  
|[setUTCFullYear yöntemi](../../javascript/reference/setutcfullyear-method-date-javascript.md)|UTC ile yıl değerini ayarlar.|  
|[setUTCHours yöntemi](../../javascript/reference/setutchours-method-date-javascript.md)|UTC ile saat değerini ayarlar.|  
|[setUTCMilliseconds yöntemi](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)|UTC ile milisaniye değerini ayarlar.|  
|[setUTCMinutes yöntemi](../../javascript/reference/setutcminutes-method-date-javascript.md)|UTC ile dakika değerini ayarlar.|  
|[setUTCMonth yöntemi](../../javascript/reference/setutcmonth-method-date-javascript.md)|UTC ile ay değeri ayarlar.|  
|[setUTCSeconds yöntemi](../../javascript/reference/setutcseconds-method-date-javascript.md)|Saniye UTC kullanarak değerini ayarlar.|  
|[setYear yöntemi](../../javascript/reference/setyear-method-date-javascript.md)|Yerel saat kullanarak yıl değerini ayarlar.|  
|[toDateString yöntemi](../../javascript/reference/todatestring-method-date-javascript.md)|Bir tarih olarak bir string değeri döndürür.|  
|[toGMTString yöntemi](../../javascript/reference/togmtstring-method-date-javascript.md)|(GMT) Greenwich saati kullanarak bir dizeye dönüştürülür tarihi döndürür.|  
|[Toısostring yöntemi](../../javascript/reference/toisostring-method-date-javascript.md)|ISO biçiminde bir dize değeri olarak bir tarihi döndürür.|  
|[toJSON yöntemi](../../javascript/reference/tojson-method-date-javascript.md)|JSON seri hale getirme önce bir nesne türü verileri dönüştürmek için kullanılır.|  
|[toLocaleDateString yöntemi](../../javascript/reference/tolocaledatestring-method-date-javascript.md)|Ana bilgisayar ortamı geçerli ayara uygun bir tarih olarak bir dize değeri döndürür.|  
|[toLocaleString yöntemi](../../javascript/reference/tolocalestring-date.md)|Geçerli yerel kullanarak bir dizeye dönüştürülür bir nesne döndürür.|  
|[toLocaleTimeString yöntemi](../../javascript/reference/tolocaletimestring-method-date-javascript.md)|Ana bilgisayar ortamı geçerli ayara uygun zaman bir dize değeri olarak döndürür.|  
|[toString yöntemi](../../javascript/reference/tostring-method-date.md)|Bir nesnenin dize gösterimini döndürür.|  
|[toTimeString yöntemi](../../javascript/reference/totimestring-method-date-javascript.md)|Zaman bir dize değeri olarak döndürür.|  
|[toUTCString yöntemi](../../javascript/reference/toutcstring-method-date-javascript.md)|UTC kullanılarak bir dizeye dönüştürülür tarihi döndürür.|  
|[valueOf yöntemi](../../javascript/reference/valueof-method-date.md)|Belirtilen nesne ilkel değerini döndürür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarihler ve saatleri hesaplama (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)   
 [Tarih ve saat dizeleri](../../javascript/date-and-time-strings-javascript.md)