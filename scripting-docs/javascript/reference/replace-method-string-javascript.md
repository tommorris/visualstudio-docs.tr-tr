---
title: "replace yöntemi (dize) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: replace
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- replacing strings
- Replace method
ms.assetid: 5f0e4765-df4d-4887-bd09-efe5e58251bf
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82894a5d7f92c8231a6ba3a1948369fb2c819a6d
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="replace-method-string-javascript"></a>replace Yöntemi (Dize) (JavaScript)
Normal bir ifade veya arama dizesini kullanarak bir dize içinde metnin yerine geçer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringObj.replace(rgExp, replaceText)  
```  
  
## <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. `String` Nesne veya değiştirme işlemini gerçekleştirmek, değişmez dize değeri. Bu dize tarafından değiştirilmez **Değiştir** yöntemi. Bunun yerine, bu yöntemin dönüş değeri yeni konacak öğe tarafından üretilen dizedir.  
  
 `rgExp`  
 Gerekli. Örneği bir **normal ifade** normal ifade deseni ve geçerli bayrakları içeren nesne. Aynı zamanda olabilir bir `String` nesne veya normal ifadeyi temsil eden dize sabit değeri. Varsa `rgExp` bir örneği değil bir **normal ifade** nesne, bir dizeye dönüştürülür ve tam bir arama sonuçlarını yapılır; dize olağan bir ifadeyi dönüştürmek için hiçbir girişimde.  
  
 `replaceText`  
 Gerekli. A `String` nesne ya da her başarılı bir eşleşme değiştirmek için metni içeren dize `rgExp` içinde `stringObj`. İçinde [!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] veya sonraki sürümlerde, `replaceText` bağımsız değişkeni değiştirme metnini döndüren bir işlev de olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucu **Değiştir** yöntemdir bir kopyasını `stringObj` belirtilen değişiklik yapıldıktan sonra.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki eşleşme değişkenlerinden herhangi biri, en son eşleşmeyi ve içinden geldiği dizeyi tanımlamak için kullanılabilir. Eşleşen değişkenler, değişim dizesinin dinamik olarak belirlendiği metin değiştirme işleminde kullanılabilir.  
  
|Karakterler|Açıklama|  
|----------------|-------------|  
|**$$**|`$`([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] veya üzeri)|  
|**$&**|Bu bölümü belirtir `stringObj` eşleşen tüm düzeni. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] veya üzeri)|  
|`$``|Bu bölümü belirtir `stringObj` tarafından açıklanan eşleşme önündeki  **$&** . ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] veya üzeri)|  
|`$'`|Bu bölümü belirtir `stringObj` tarafından açıklanan eşleşme izleyen  **$&** . ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] veya üzeri)|  
|`$`  ***n***| *n* Th yakalanan submatch, burada  *n*  1 ile 9 arasında tek bir ondalık basamak değil. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] veya üzeri)|  
|`$`  ***nn***| *nn* Th yakalanan submatch, burada  *nn*  01 ile 99 arasında iki basamaklı bir ondalık sayı. ([!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] veya üzeri)|  
  
 Varsa `replaceText` her eşleşen substring işlevi şununla adlı bir işlev aranır *m* + 3 tane bağımsız değişkene nerede *m* sol parantez içinde yakalama sayısıdır `rgExp`. İlk bağımsız değişken, eşleşen alt dizedir. Sonraki *m* bağımsız değişkenler tüm arama sonuçlandı yakalar. Bağımsız değişken *m* + 2 içinde uzaklık `stringObj` eşleşme oluştuğu ve bağımsız değişkeni *m* + 3 `stringObj`. Sonuç, eşleşen her alt dizenin karşılık gelen işlev dönüş değeriyle değiştirilmesi sonucu elde edilen dize değeridir.  
  
 **Değiştir** yöntemi güncelleştirmeleri genel özelliklerini `RegExp` nesnesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **Değiştir** tüm örneklerini "" "a." ile değiştirir yöntemi  
  
```JavaScript  
var s = "the batter hit the ball with the bat";  
  
// Replace "the" with "a".  
var re = /the/g;  
var result = s.replace(re, "a");  
document.write(result);  
// Output: a batter hit a ball with a bat  
```  
  
 Ayrıca, **Değiştir** yöntemi ayrıca düzeninde alt ifadelerin değiştirin. Aşağıdaki örnek, dizedeki her sözcük çiftini değiştirir.  
  
```JavaScript  
  
var s = "The quick brown fox jumped over the lazy dog.";  
var re = /(\S+)(\s+)(\S+)/g;  
// Exchange each pair of words.  
var result = s.replace(re, "$3$2$1");  
document.write(result);  
  
// Output:  quick The fox brown over jumped lazy the dog.  
```  
  
 İçinde çalıştığı aşağıdaki örnekte, [!INCLUDE[jsv55textspecific](../../javascript/reference/includes/jsv55textspecific-md.md)] ve daha sonra değiştirme metnini döndüren bir işlev kullanmayı gösterir. Sonuna "F" gelen bir sayının herhangi bir örneğinde Celsius dönüştürmesi yapar.  
  
```JavaScript  
function f2c(s1) {  
    // Initialize pattern.  
    var test = /(\d+(\.\d*)?)F\b/g;  
  
    // Use a function for the replacement.  
    var s2 = s1.replace(test,  
      function($0,$1,$2)  
           {   
           return((($1-32) * 5/9) + "C");  
           }  
        )  
    return s2;  
}  
document.write(f2c("Water freezes at 32F and boils at 212F."));  
  
// Output: Water freezes at 0C and boils at 100C.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Exec yöntemi (normal ifade)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [match yöntemi (dize)](../../javascript/reference/match-method-string-javascript.md)   
 [RegExp nesnesi](../../javascript/reference/regexp-object-javascript.md)   
 [search yöntemi (dize)](../../javascript/reference/search-method-string-javascript.md)   
 [test yöntemi (normal ifade)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Normal ifade programlama (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)   
 [Değişim ve alt ifadelerin (JavaScript)](http://msdn.microsoft.com/en-us/c59dd3e8-7fee-493e-9123-065af1e651ae)   
 [Yeniden başvurular (JavaScript)](http://msdn.microsoft.com/en-us/5d8dbd5a-cd03-4548-850b-9d7bad2c839a)   
 [HTML5 örnek uygulaması sürükleyip](http://code.msdn.microsoft.com/Drag-and-drop-e2701a72)