---
title: Normal ifade nesnesi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: RegularExpression_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Regular Expression object
- regular expressions, RegExp object
- RegExp object, overview
ms.assetid: 346aa83e-a045-47ea-acae-b42c7b121534
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df2d07e3b47e315ec804e5a7f20024dc2184eef0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="regular-expression-object-javascript"></a>Normal İfade Nesnesi (JavaScript)
Normal ifade deseni desen uygulamak nasıl belirlemek bayrakları birlikte içeren bir nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
re = /pattern/[flags]  
```  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
re = new RegExp("pattern"[,"flags"])   
```  
  
## <a name="parameters"></a>Parametreler  
 *RE*  
 Gerekli. Normal ifade deseni atandığı değişken adı.  
  
 *düzeni*  
 Gerekli. Kullanılacak normal ifade deseni. Sözdizimi 1 kullanırsanız, bir desen sınırlandırmak "/" karakter. Sözdizimi 2 kullanıyorsanız, düzeni tırnak işaretleri içine alın.  
  
 `flags`  
 İsteğe bağlı. Sözdizimi 2 kullanıyorsanız bayrağı tırnak işaretleri içine alın. Birleştirilebilir, kullanılabilir bayraklar şunlardır:  
  
-   g (tüm oluşumları için genel arama *düzeni*)  
  
-   t (servis talebi yoksay)  
  
-   m (çok satırlı arama)  
  
-   u (unicode) etkinleştirir EcmaScript 6 [Unicode özellikleri](../../javascript/advanced/special-characters-javascript.md). Yalnızca desteklenen [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)].  
  
-   y (Yapışkan eşleşme) eşleşir arar `lastIndex` normal ifadenin özelliği (ve sonraki dizinleri aramaz). Desteklenen [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)].  
  
## <a name="remarks"></a>Açıklamalar  
 **Normal ifade** nesne karıştırılmamalıdır genel ile `RegExp` nesnesi. Aynı ses olsa bile, farklı ve ayrıdır. Özelliklerini **normal ifade** nesne içeren yalnızca bir özellikle ilgili bilgilerin **normal ifade** örnek genel özelliklerini kaydedilirken `RegExp` nesnesi içerir Sürekli işlem gerçekleştiğinde gibi her eşleşme hakkında bilgi güncelleştirildi.  
  
 **Normal ifade** nesneler karakter birleşimleri için dizeleri arama yaparken kullanılan desenleri depolar. Sonra **normal ifade** nesnesi oluşturulur, ya da bir dize yönteme geçirilen ya da bir dize normal ifade yöntemlerden biri olarak geçirilir. Gerçekleştirilen en son arama hakkındaki bilgiler global depolanan `RegExp` nesnesi.  
  
 Arama dizesi önceden bildiğiniz durumlarda sözdizimi 1'i kullanın. Arama dizesi sık değişen veya bilinmeyen dizeler gibi kullanıcı girişten alınır Sözdizimi 2 kullanın.  
  
 *Düzeni* bağımsız değişkeni bir iç biçimi kullanmadan önce derlenir. Sözdizimi 1 için *düzeni* betik yüklendiği gibi derlenir. Sözdizimi 2 için *düzeni* yalnızca kullanılmadan önce derlenmiştir veya ne zaman **derleme** yöntemi çağrılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **normal ifade** (yeniden) bir normal ifade deseni ile ilişkili bayraklarının içeren bir nesne oluşturarak nesnesi. Bu durumda, elde edilen **normal ifade** nesnesi tarafından kullanılan sonra `match` yöntemi:  
  
```JavaScript  
var s = "through the pages of the book";  
  
// Create regular expression pattern.  
var re = new RegExp("the", "i");  
  
// Attempt match on search string.  
var r = s.match(re);     
  
// Return first occurrence of "the".  
if(console && console.log) {  
    console.log(r);  
}  
  
// Output:  
//   
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, birden çok örneğini aramak için normal ifade deseni güncelleştirir.  
  
```JavaScript  
// Create regular expression pattern using the i and g flags.  
var re = new RegExp("the", "ig");  
  
// Attempt match on search string.  
var r = s.match(re);     
  
// Return the two occurrences of "the".  
if(console && console.log) {  
    console.log(r.length);  
    console.log(r);  
}  
  
// Output:  
// 2  
// [object Array] ["the", "the"]  
```  
  
## <a name="example"></a>Örnek  
 Bir eşleşme başarılı olursa /y bayrağını kullanırken, güncelleştirmeleri `lastindex` son eşleşme sonra sonraki karakteri dizin. Eşleşme başarısız olursa, sıfırlar `lastindex` 0.  
  
 Aşağıdaki örnek, bir eşleşme /y bayrağını kullanarak belirli bir dizine arar ve `lastIndex` özelliği.  
  
```JavaScript  
// Create regular expression pattern using the i and y flags.  
var re = new RegExp("the", "iy");  
  
// Set the lastIndex property and attempt a match  
// at the specified index.  
re.lastIndex = 20;  
var r = s.match(re);     
  
// No matches returned.  
if(console && console.log) {  
    console.log(r);  
}  
// Reset the lastIndex property and attempt a match.  
re.lastIndex = 21;  
var r = s.match(re);  
  
// Return occurrence of "the" starting at index 21.  
if(console && console.log) {  
    console.log(r);  
}  
  
// Output:  
// null  
// [object Array] ["the"]  
```  
  
<a name="js56jsobjregexpressionprop"></a>   
## <a name="properties"></a>Özellikler  
 [Genel özellik](../../javascript/reference/global-property-regular-expression-javascript.md) &#124; [ignoreCase özelliği](../../javascript/reference/ignorecase-property-regular-expression-javascript.md) &#124; [multiline özelliği](../../javascript/reference/multiline-property-regular-expression-javascript.md) &#124; [source özelliği](../../javascript/reference/source-property-regular-expression-javascript.md)  
  
<a name="js56jsobjregexpressionmeth"></a>   
## <a name="methods"></a>Yöntemler  
 [compile yöntemi](../../javascript/reference/compile-method-regular-expression-javascript.md) &#124; [exec yöntemi](../../javascript/reference/exec-method-regular-expression-javascript.md) &#124; [test yöntemi](../../javascript/reference/test-method-regular-expression-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 U bayrağı desteklenir [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)].  
  
 Y bayrağı desteklenir [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)].  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RegExp nesnesi](../../javascript/reference/regexp-object-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)