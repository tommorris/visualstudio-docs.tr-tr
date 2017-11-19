---
title: "İç nesneler (JavaScript) | Microsoft Docs"
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
- built-in objects [JavaScript]
- intrinsic objects [JavaScript]
ms.assetid: 6520c634-a7d1-4a05-8c1b-2e79f449d2e4
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 242b572c2818f9968e6d5fc51e1272e3004c0f05
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="intrinsic-objects-javascript"></a>İç Nesneler (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]İç (veya "yerleşik") nesneleri sağlar. Bunlar `Array`, `Boolean`, `Date`, `Error`, `Function`, **Global**, **JSON**, **matematik**,  **Sayı**, `Object`, `RegExp`, ve `String` nesneleri. İç nesneler yöntemleri, İşlevler, özellikler ve içinde ayrıntılı olarak açıklanmıştır sabitleri ilişkilendirdiğiniz [dil başvurusu](../javascript/reference/javascript-reference.md).  
  
## <a name="array-object"></a>Array Nesnesi  
 Bir dizinin alt simgeler, bir nesne özellikleri olarak düşünülebilir ve kendi sayısal dizini adlandırılır. Bir diziye eklenen adlandırılmış özellikleri numarasına göre sıralanamıyor unutmayın; Bunlar, dizi öğeleri ayrıdır.  
  
 Yeni bir dizi oluşturmak için kullanın **yeni** işleci ve **Array()** [Oluşturucusu](../javascript/reference/constructor-property-object-javascript.md), aşağıdaki örnekte olduğu gibi.  
  
```JavaScript  
var theMonths = new Array(12);  
theMonths[0] = "Jan";  
theMonths[1] = "Feb";  
theMonths[2] = "Mar";  
theMonths[3] = "Apr";  
theMonths[4] = "May";  
theMonths[5] = "Jun";  
theMonths[6] = "Jul";  
theMonths[7] = "Aug";  
theMonths[8] = "Sep";  
theMonths[9] = "Oct";  
theMonths[10] = "Nov";  
theMonths[11] = "Dec";  
```  
  
 Kullanarak bir dizinin oluşturduğunuzda `Array` anahtar sözcüğü, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] içeren bir **uzunluğu** girdi sayısı kayıtları özelliği. Bir sayı belirtmezseniz uzunluğu 0 olarak ayarlayın ve dizi hiçbir girişlerine sahip değil. Bir sayıyı belirtirseniz, uzunluğu bu sayıya ayarlanır. Birden fazla parametre belirtirseniz, parametreleri girişleri dizisi olarak kullanılır. Ayrıca, parametrelerin sayısı önceki örneğe eşdeğerdir aşağıdaki örnekteki gibi uzunluğu özelliğine atanır.  
  
```JavaScript  
var theMonths = new Array("Jan", "Feb", "Mar", "Apr", "May", "Jun",   
"Jul", "Aug", "Sep", "Oct", "Nov", "Dec");  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]otomatik olarak değerini değiştirir **uzunluğu** ile oluşturulmuş bir dizi öğeleri eklediğinizde `Array` anahtar sözcüğü. Dizi içermese de [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] length özelliği her zaman bir dizi en büyük dizinde büyük olacak şekilde her zaman değil 1, 0'da başlar.  
  
## <a name="string-object"></a>Dize Nesnesi  
 İçinde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], nesneleri değilmiş gibi dizeleri (ve sayılar) davranabilirsiniz. [Nesne dize](../javascript/reference/string-object-javascript.md) dizelerinizi ile kullanabileceğiniz bazı yerleşik yöntemlerine sahiptir. Bunlardan biri [substring yöntemi](../javascript/reference/substring-method-string-javascript.md), dize bölümünü döndürür. İki sayı kendi bağımsız değişken alır.  
  
```JavaScript  
var aString = "0123456789";  
  
// This code sets aChunk to "456".  
var aChunk = aString.substring(4, 7);  
  
// This code sets anotherChunk to "456", using  
// the lower value index as the starting index.  
var anotherChunk = aString.substring(7, 4);  
  
// This code sets the firstLetter variable to "J"  
// by using the array in the preceding array creation example.  
firstLetter = theMonths[5].substring(0,1);  
```  
  
 Başka bir özelliği `String` nesne **uzunluğu** özelliği. Bu özelliği (0 için boş bir dize) dizedeki karakter sayısını içerir. Bu sayısal değer ve hesaplamalarda doğrudan kullanılabilir.  
  
```JavaScript  
var howLong = "Hello World".length  // Sets the howLong variable to 11.  
```  
  
## <a name="math-object"></a>Matematik Nesnesi  
 **Matematik** nesnesi bir dizi önceden tanımlanmış sabitleri ve işlevleri sahiptir. Sabitler belirli numaralarıdır. Bu belirli sayılardan birini PI (yaklaşık... 3.14159) değeri. Bu **Math.PI** sabit, aşağıdaki örnekte gösterilen.  
  
```JavaScript  
var radius = 5;  
var circleArea = Math.PI * radius * radius;  
```  
  
 Yerleşik işlevlerinden biri **matematik** nesnesidir üs yöntemi veya `Math.pow`, belirtilen güç sayıya başlatır. Aşağıdaki örnek, bir küre hacmini hesaplamak için pi hem üs kullanır.  
  
```JavaScript  
var volume = (4/3)*(Math.PI*Math.pow(radius,3));  
```  
  
## <a name="date-object"></a>Tarih Nesnesi  
 `Date` Nesne, geçerli sistem tarihi almak ve tarihleri arasındaki farkları hesaplamak için rasgele tarih ve saat, temsil etmek için kullanılabilir. Çeşitli özellikleri ve yöntemleri, tüm önceden tanımlanmış sahiptir. Genel olarak, `Date` nesnesi, haftanın günü; ay, gün ve yıl; sağlar ve saat, saat, dakika ve saniye. Bu bilgiler Greenwich saati (UTC veya "Evrensel Eşgüdümlü World zaman standart tarafından verilen sinyallere başvuran zaman," tercih edilen terim değil) olan 00:00:00.000 GMT olan 1 Ocak 1970 tarihinden itibaren milisaniye sayısını temel alır. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]yaklaşık 250,000 m.ö. aralığındadır tarihleri işleyebilir 255,000 M.S.  
  
 Yeni `Date` nesne, kullanın **yeni** aşağıdaki örnekte gösterildiği gibi işleci.  
  
```JavaScript  
var toDay = new Date();    
var thisYear = toDay.getFullYear();  
var thisMonth = theMonths[toDay.getMonth()];  
var thisDay = thisMonth  + " " + toDay.getDate() + ", " + thisYear;  
```  
  
## <a name="number-object"></a>Sayı Nesnesi  
 Özel sayısal sabitleri yanı sıra (`PI`, örneğin) içinde kullanılabilir **matematik** nesnesi, diğer sabitleri kullanılabilir [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] aracılığıyla **numarası** nesne.  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|Number.MAX_VALUE|En büyük olası numarası, 1, 79E + 308 hakkında; olumlu veya olumsuz olabilir. (Değeri sistemden diğerine biraz farklıdır.)|  
|Number.MIN_VALUE|En küçük olası numarası, yaklaşık 5.00E-324; olumlu veya olumsuz olabilir. (Değeri sistemden diğerine biraz farklıdır.)|  
|Number.NaN|Özel sayısal değer, "sayı değil."|  
|Number.posıtıve_ınfınıty|Herhangi bir pozitif değer en büyük pozitif sayı (Number.MAX_VALUE) büyük otomatik olarak bu değer dönüştürülür; sonsuz temsil.|  
|Number.negatıve_ınfınıty|Daha büyük negatif sayı negatif herhangi bir değer (-Number.MAX_VALUE) otomatik olarak bu değer için; dönüştürülür -sonsuz temsil.|  
  
 **Number.NaN** "olmayan bir sayı." tanımlanan özel bir sabit değer Bir sayı döndürür olarak ayrıştırılamıyor bir dize ayrıştırma girişimi **Number.NaN**. `NaN`herhangi bir sayıya ve kendisine eşit olmayan karşılaştırır. Sınamak için bir `NaN` neden, karşılaştırma değil **Number.NaN**; kullanın **isNaN()** yerine işlev.  
  
## <a name="json-object"></a>JSON Nesnesi  
 JSON, JavaScript dil nesne değişmez değer gösterimi alt kümesinde dayalı basit veri değişim biçimidir.  
  
 JSON nesnesi, JSON metin biçimi gelen ve giden dönüştürmek için iki işlev sağlar. [JSON.stringify](../javascript/reference/json-stringify-function-javascript.md) işlevi, JSON metne nesneler ve diziler serileştirir. [JSON.parse](../javascript/reference/json-parse-function-javascript.md) işlevi XML'deki bellek içi nesneleri oluşturmak için JSON metni serileştirir. Daha fazla bilgi için bkz: [JavaScript ve .NET JavaScript nesne gösterimi (JSON) için giriş](http://go.microsoft.com/fwlink/?LinkId=124098).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript nesneleri](../javascript/reference/javascript-objects.md)