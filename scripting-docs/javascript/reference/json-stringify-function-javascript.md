---
title: "JSON.stringify işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- stringify method
ms.assetid: 0fafaf3b-c29b-46dc-b65b-ca223064a1d0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3539bb003ed20a3ff7586e42466bf7c47165b83f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsonstringify-function-javascript"></a>JSON.stringify İşlevi (JavaScript)
Dönüştüren bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] bir JavaScript nesne gösterimi (JSON) dize değeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
JSON.stringify(  
value [, replacer] [, space])  
```  
  
## <a name="parameters"></a>Parametreler  
 `value`  
 Gerekli. A [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] değeri, genellikle bir nesne ya da dizi, dönüştürülecek.  
  
 `replacer`  
 İsteğe bağlı. Sonuçları dönüştüren bir işlev veya dizi.  
  
 Varsa `replacer` bir işlevi olduğunu `JSON.stringify` anahtarı ve değeri her üyesinin geçirme işlevi çağırır. Özgün değerin yerine dönüş değeri kullanılır. İşlev döndürürse `undefined`, üye dışlandı. Kök nesnenin anahtarı boş bir dizedir: "".  
  
 Varsa `replacer` dizideki dönüştürülmesi anahtar yalnızca üyeleriyle bir dizidir. Üyelerin dönüştürülme sırası dizideki anahtarların sırasıyla aynıdır. `replacer` Dizi göz ardı edilir zaman `value` bağımsız değişken değil de bir dizi.  
  
 `space`  
 İsteğe bağlı. Daha kolay okunmasını sağlamak için dönüş değeri JSON metnine girintileme, beyaz boşluk ve satır sonu karakterleri ekler.  
  
 Varsa `space` olan atlanırsa, dönüş değeri metin hiçbir ek boşluk oluşturulur.  
  
 Varsa `space` bir sayı, boşluk her düzeyde belirtilen sayıda dönüş değeri metin girintili. Varsa `space` olan 10'dan büyük, girintili 10 alanları metindir.  
  
 Varsa `space` boş dize '\t' gibi her düzeyde dizedeki karakter ile dönüş değeri metin girintili olur.  
  
 Varsa `space` 10 karakterden daha uzun bir dize ilk 10 karakter kullanılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 JSON metnini içeren bir dize.  
  
## <a name="exceptions"></a>Özel Durumlar  
  
|Özel Durum|Koşul|  
|---------------|---------------|  
|[Geçersiz değiştirici bağımsız değişken](../../javascript/misc/invalid-replacer-argument.md)|`replacer` Bağımsız değişkeni bir işlevi veya bir dizi değil.|  
|[Desteklenmeyen değer bağımsız değişkeninde döngüsel başvuru](../../javascript/misc/circular-reference-in-value-argument-not-supported.md)|`value` Bağımsız değişkeni döngüsel başvuru içeriyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `value` sahip bir `toJSON` yöntemi, `JSON.stringify` işlevi yöntemin dönüş değerini kullanır. Varsa dönüş değerini `toJSON` yöntemi `undefined`, üye dönüştürülmez. Bu, bir nesnenin kendi JSON temsilini belirlemesini sağlar.  
  
 JSON temsili gibi olmayan değerleri `undefined`, dönüştürülmeyecek. Nesnelerde, bunlar bırakılır. Dizilerde, null ile değiştirilir.  
  
 Dize değerleri tırnak işaretiyle başlar ve biter. Ters eğik çizgi kullanılarak atlanması gereken karakterler hariç, tüm Unicode karakterleri tırnak işareti içine alınabilir. Aşağıdaki karakterlerin başına bir ters eğik çizgi eklenmelidir:  
  
-   Tırnak işareti (")  
  
-   Ters eğik çizgi (\\)  
  
-   Geri al (b)  
  
-   Form besleme (f)  
  
-   Yeni satır (n)  
  
-   Satır başı (r)  
  
-   Yatay sekme (t)  
  
-   Dört onaltılı basamak (uhhhh)  
  
## <a name="order-of-execution"></a>Yürütme Sırası  
 Seri hale getirme işlemi sırasında bir `toJSON` yöntemi var. `value` bağımsız değişkeni, `JSON.stringify` önce çağırır `toJSON` yöntemi. Yoksa, özgün değer kullanılır. Sonraki, eğer bir `replacer` bağımsız değişkeni sağlanır, değeri (özgün değeri veya `toJSON` dönüş değeri) return-değeri ile değiştirilir `replacer` bağımsız değişkeni. Son olarak, isteğe bağlı alan değeri boşluk eklenir `space` son JSON metnini oluşturmak için bağımsız değişken.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `JSON.stringify` dönüştürmek için `contact` nesne JSON metni. `memberfilter` Dizi böylelikle yalnızca tanımlı `surname` ve `phone` üyeleri dönüştürülür. `firstname` Üye atlanmış.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Array();  
memberfilter[0] = "surname";  
memberfilter[1] = "phone";  
var jsonText = JSON.stringify(contact, memberfilter, "\t");  
document.write(jsonText);  
// Output:   
// { "surname": "Aaberg", "phone": [ "555-0100", "555-0120" ] }  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte `JSON.stringify` bir diziye sahip. `replaceToUpper` İşlevi dizideki her dize büyük harfe dönüştürür.  
  
```JavaScript  
var continents = new Array();  
continents[0] = "Europe";  
continents[1] = "Asia";  
continents[2] = "Australia";  
continents[3] = "Antarctica";  
continents[4] = "North America";  
continents[5] = "South America";  
continents[6] = "Africa";  
  
var jsonText = JSON.stringify(continents, replaceToUpper);  
  
function replaceToUpper(key, value) {  
    return value.toString().toUpperCase();  
}  
  
//Output:  
// "EUROPE,ASIA,AUSTRALIA,ANTARCTICA,NORTH AMERICA,SOUTH AMERICA,AFRICA"  
  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte `toJSON` dize değerleri büyük harfe dönüştürülecek yöntemi.  
  
```JavaScript  
var contact = new Object();   
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
contact.toJSON = function(key)  
 {  
    var replacement = new Object();  
    for (var val in this)  
    {  
        if (typeof (this[val]) === 'string')  
            replacement[val] = this[val].toUpperCase();  
        else  
            replacement[val] = this[val]  
    }  
    return replacement;  
};  
  
var jsonText = JSON.stringify(contact);  
document.write(jsonText);  
  
// Output:  
{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}  
  
'{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}'  
*/  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JSON.parse işlevi](../../javascript/reference/json-parse-function-javascript.md)   
 [toJSON yöntemi (tarih)](../../javascript/reference/tojson-method-date-javascript.md)   
 [Akış okuyucu örnek uygulama (Windows mağazası)](http://code.msdn.microsoft.com/Feed-reader-sample-99d68cf8)