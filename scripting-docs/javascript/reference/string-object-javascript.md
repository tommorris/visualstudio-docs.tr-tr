---
title: Dize nesnesi (JavaScript) | Microsoft Docs
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
- String_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- String object
- String object, overview
ms.assetid: 8063ecd5-5778-4e87-b985-b21420171914
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d58f567bb301b29324fee8ed75fc95fd1a4791ea
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792194"
---
# <a name="string-object-javascript"></a>Dize Nesnesi (JavaScript)
Metin dizelerinin düzenlenmesini ve biçimlendirmesini, ve dizeler içindeki alt dizelerin belirlenmesini ve konumlarının bulunmasını etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
newString = new String(["stringLiteral"])  
```  
  
## <a name="parameters"></a>Parametreler  
 `newString`  
 Gerekli. Değişken adına `String` nesne atanır.  
  
 `stringLiteral`  
 İsteğe bağlı. Herhangi bir Unicode karakter grubu.  
  
## <a name="remarks"></a>Açıklamalar  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]doğrudan yazamazsınız karakterler oluşturma dizelerde içerebilir kaçış sıraları sağlar. Örneğin, `\t` sekme karakteri belirtir. Daha fazla bilgi için bkz: [özel karakterleri](../../javascript/advanced/special-characters-javascript.md).  
  
## <a name="string-literals"></a>Dize Sabit Değerleri  
 A *dize sabit değeri* tek veya çift tırnak işaretleri içine sıfır veya daha fazla karakterdir. Bir birincil (Temel) veri türü bir dize sabit değeri `string`. A *dize nesnesi* kullanılarak oluşturulan [new işleci](../../javascript/reference/new-operator-decrementjavascript.md), ve bir veri türü `Object`.  
  
 Aşağıdaki örnekte bir değişmez dize veri türü aynı olmadığını gösteren bir `String` nesnesi.  
  
```JavaScript  
var strLit = "This is a string literal.";  
var strObj = new String("This is a string object.");  
  
document.write(typeof strLit);  
document.write("<br/>");  
document.write(typeof strObj);  
// Output:  
// string  
// object  
```  
  
## <a name="methods-for-string-literals"></a>Dize Sabit Değerleri için Yöntemler  
 Bir dize sabiti üzerinde bir yöntem çağırdığınızda, geçici olarak bir dize sarmalayıcı nesnesine dönüştürülür. Dize sabit değeri olarak yine de kabul `new` işleci oluşturmak için kullanılmış.  
  
 Aşağıdaki örnek uygular `toUpperCase` yöntemine bir değişmez dize değeri.  
  
```JavaScript  
var strLit = "This is a string literal.";  
  
var result1 = strLit.toUpperCase();  
  
var result2 = (new String(strLit)).toUpperCase();  
  
document.write(result1);  
document.write("<br/>");  
document.write(result2);  
// Output:   
// THIS IS A STRING LITERAL.  
// THIS IS A STRING LITERAL.  
```  
  
## <a name="accessing-an-individual-character"></a>Tek Bir Karaktere Erişme  
 Bir dizenin tek bir karakterine salt okunur bir dizi-dizinli özellik gibi erişebilirsiniz. Bu özellik sunulmuştur [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)]. Aşağıdaki örnek tek tek dize karakterlerine erişir.  
  
```JavaScript  
var str = "abcd";  
var result = str[2];  
document.write (result);  
// Output: c  
  
var result = "the"[0];  
document.write(result);  
// Output: t  
```  
  
## <a name="requirements"></a>Gereksinimler  
 `String Object` Sunulmuştur [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)]. Aşağıdaki listelerin bazı üyeleri daha sonraki sürümlerde eklendi.  
  
<a name="js56jsobjstringprop"></a>   
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `String` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[constructor özelliği](../../javascript/reference/constructor-property-string.md)|Bir nesneyi oluşturan işlevi belirtir.|  
|[length özelliği (dize)](../../javascript/reference/length-property-string-javascript.md)|Uzunluğunu döndürür bir `String` nesnesi.|  
|[prototype özelliği](../../javascript/reference/prototype-property-string.md)|Bir nesne sınıfı için prototipe bir başvuru döndürür.|  
  
## <a name="functions"></a>İşlevler  
 Aşağıdaki tabloda işlevlerini listeler `String` nesnesi.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[String.fromCharCode işlevi](../../javascript/reference/string-fromcharcode-function-javascript.md)|Unicode karakter değerlerinden bir dize döndürür.|  
|[String.fromCodePoint işlevi](../../javascript/reference/string-fromcodepoint-function-javascript.md)|Bir Unicode UTF-16 kod noktasıyla ilişkili bir dize döndürür.|  
|[String.RAW işlevi](../../javascript/reference/string-raw-function-javascript.md)|Şablon dizesini ham dize biçiminde döndürür.|  
  
<a name="js56jsobjstringmeth"></a>   
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `String` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Bağlantı yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Metin etrafına NAME özniteliği olan bir HTML tutturucusu yerleştirir.|  
|[Big yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<büyük > metninin çevresindeki etiketler.|  
|[blink yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<BLINK > metninin çevresindeki etiketler.|  
|[Bold yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<B > metninin çevresindeki etiketler.|  
|[charAt yöntemi](../../javascript/reference/charat-method-string-javascript.md)|Belirtilen dizindeki karakteri döndürür.|  
|[charCodeAt yöntemi](../../javascript/reference/charcodeat-method-string-javascript.md)|Belirtilen karakterin Unicode kodlamasını döndürür.|  
|[codePointAt yöntemi](../../javascript/reference/codepointat-method-string-javascript.md)|Unicode UTF-16 karakter kod noktası döndürür.|  
|[concat yöntemi (dize)](../../javascript/reference/concat-method-string-javascript.md)|Sağlanan iki dizenin bitiştirilmiş halini içeren bir dize döndürür.|  
|[endsWith yöntemi](../../javascript/reference/endswith-method-string-javascript.md)|Bir dize veya SUBSTRING geçirilen dizesiyle biten olup olmadığını gösteren bir Boole değeri döndürür.|  
|[includes yöntemi](../../javascript/reference/includes-method-string-javascript.md)|Geçirilen dize dize nesnesinde yer alan olup olmadığını gösteren bir Boole değeri döndürür.|  
|[Fixed yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<TT > metninin çevresindeki etiketler.|  
|[fontcolor yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<yazı tipi > etiketleri metninin çevresindeki renk özniteliğine sahip.|  
|[FontSize yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<yazı tipi > metninin çevresindeki BOYUTU özniteliğiyle etiketler.|  
|[hasOwnProperty yöntemi](../../javascript/reference/hasownproperty-method-object-javascript.md)|Bir nesnenin belirtilen adda bir özelliği olup olmadığını belirten bir Boolean değer döndürür.|  
|[indexOf yöntemi (dize)](../../javascript/reference/indexof-method-string-javascript.md)|Bir alt dizenin bir dize içinde bulunduğu ilk karakter konumunu döndürür.|  
|[isPrototypeOf yöntemi](../../javascript/reference/isprototypeof-method-object-javascript.md)|Bir nesnenin başka bir nesnenin prototip zincirinde mevcut olup olmadığını belirten bir Boolean değer döndürür.|  
|[italics yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<t > metninin çevresindeki etiketler.|  
|[lastIndexOf yöntemi (dize)](../../javascript/reference/lastindexof-method-string-javascript.md)|Bir alt dizenin bir dize içinde son bulunduğu konumu döndürür.|  
|[Bağlantı yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Metin etrafına HREF özniteliği olan bir HTML tutturucusu yerleştirir.|  
|[localeCompare yöntemi](../../javascript/reference/localecompare-method-string-javascript.md)|Geçerli yerel ayarlarda iki dizenin eşdeğer olup olmadığını belirten bir değer döndürür.|  
|[match yöntemi](../../javascript/reference/match-method-string-javascript.md)|Sağlanan kullanarak bir dizeyi arar **normal ifade** nesne ve sonuçları bir dizisi olarak döndürür.|  
|[Yöntem normalleştirin](../../javascript/reference/normalize-method-string-javascript.md)|Belirtilen dize Unicode normalleştirme biçiminde döndürür.|  
|[Propertyısenumerable yöntemi](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Belirtilen bir özelliğin bir nesnenin parçası olup olmadığını ve numaralandırılabilir olup olmadığını belirten bir Boolean değer döndürür.|  
|[repeat yöntemi](../../javascript/reference/repeat-method-string-javascript.md)|Özgün dizeye eşit değerde olan yeni bir dize nesnesi belirtilen sayıda yinelenen döndürür.|  
|[replace yöntemi](../../javascript/reference/replace-method-string-javascript.md)|Bir dize içinde metin değiştirmek için bir normal ifade kullanır ve sonucu döndürür.|  
|[search yöntemi](../../javascript/reference/search-method-string-javascript.md)|Bir normal ifade aramasında ilk alt dize eşleşmesinin konumunu döndürür.|  
|[slice yöntemi (dize)](../../javascript/reference/slice-method-string-javascript.md)|Bir dizenin bir bölümünü döndürür.|  
|[küçük yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<küçük > metninin çevresindeki etiketler.|  
|[split yöntemi](../../javascript/reference/split-method-string-javascript.md)|Bir dize alt dizelere bölündüğünde oluşan dizelerin dizisini döndürür.|  
|[startsWith yöntemi](../../javascript/reference/startswith-method-string-javascript.md)|Bir dize veya SUBSTRING geçirilen dizesi ile başlayıp başlamadığını gösteren bir Boole değeri döndürür.|  
|[çizgiyi yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<ÜSTÜNÜ > metninin çevresindeki etiketler.|  
|[sub yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<SUB > metninin çevresindeki etiketler.|  
|[substr yöntemi](../../javascript/reference/substr-method-string-javascript.md)|Belirtilen konumdan başlayan ve belirtilen uzunluğa sahip bir alt dize döndürür.|  
|[substring yöntemi](../../javascript/reference/substring-method-string-javascript.md)|İçinde belirtilen bir konumdaki alt dizeyi döndürür bir `String` nesnesi.|  
|[sup yöntemi](../../javascript/reference/html-tag-methods-javascript.md)|Yerleştirir HTML \<SUP > metninin çevresindeki etiketler.|  
|[toLocaleLowerCase yöntemi](../../javascript/reference/tolocalelowercase-method-string-javascript.md)|Ortamın geçerli yerel ayarlarını göz önüne alarak tüm alfabetik karakterlerin küçük harfe dönüştürüldüğü bir dize döndürür.|  
|[toLocaleString yöntemi](../../javascript/reference/tolocalestring-method-object-javascript.md)|Geçerli yerel ayarları kullanarak dizeye dönüştürülmüş bir nesne döndürür.|  
|[toLocaleUpperCase yöntemi](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)|Ortamın geçerli yerel ayarlarını göz önüne alarak tüm alfabetik karakterlerin büyük harfe dönüştürüldüğü bir dize döndürür.|  
|[toLowerCase yöntemi](../../javascript/reference/tolowercase-method-javascript.md)|Tüm alfabetik karakterlerin küçük harfe dönüştürüldüğü bir dize döndürür.|  
|[toString yöntemi](../../javascript/reference/tostring-method-string-1.md)|Dizeyi döndürür.|  
|[toUpperCase yöntemi](../../javascript/reference/touppercase-method-string-javascript.md)|Tüm alfabetik karakterlerin büyük harfe dönüştürüldüğü bir dize döndürür.|  
|[trim yöntemi](../../javascript/reference/trim-method-string-javascript.md)|Tüm baş ve sondaki beyaz boşlukları ve satır sonlandırıcı karakterleri kaldırılmış bir dize döndürür.|  
|[valueOf yöntemi](../../javascript/reference/valueof-method-string.md)|Dizeyi döndürür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Kaydırma, kaydırma ve yakınlaştırma örnek uygulaması](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)