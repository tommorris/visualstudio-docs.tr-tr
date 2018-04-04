---
title: Değişkenleri (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- coercion
- case sensitivity, JavaScript variable name
ms.assetid: 12a450e5-4818-4a09-9878-cd7c6cd2a248
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c1d09f634bd4901e4015766bf55f272926a0a31c
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="variables-javascript"></a>Değişkenler (JavaScript)
İçinde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], bir değişken "Hello ifadesini" veya 5 gibi bir değer içeriyor. Değişkeni kullandığınızda, verileri temsil eder, örneğin başvurmak `NumberOfDaysLeft = EndDate - TodaysDate`.  
  
 Değişkenleri depolamak, almak ve kodunuzda görülen değerleri değiştirmek için kullanın. Değişkenlerinizi kodunuzu ne yapacağını anlamak için diğer kişileri kolaylaştırmak için anlamlı adlar verin deneyin.  
  
## <a name="declaring-variables"></a>Değişkenleri bildirme  
 Bir değişken, komut dosyasında görünen ilk kez kendi bildirimidir. Daha sonra komut dosyanıza başvurduğu için değişkenin ilk Bahsetme, bellekte, ayarlar. Kullanmadan önce değişkenleri bildirmeniz gerekir. Kullanarak bunu `var` anahtar sözcüğü.  
  
```JavaScript  
// A single declaration.  
var count;    
// Multiple declarations with a single var keyword.  
var count, amount, level;      
// Variable declaration and initialization in one statement.  
var count = 0, amount = 100;   
```  
  
 Değişken başlatmazsanız `var` deyimi, otomatik olarak sürdüğünü değerine `undefined`.  
  
## <a name="naming-variables"></a>Adlandırma değişkenleri  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] büyük küçük harfe duyarlı bir dildir. Bir değişken adı gibi buna **Sayacım** değişken adından farklı **Sayacım**. Değişken adlarının herhangi bir uzunlukta olabilir. Yasal değişken adları oluşturmak için kurallar aşağıdaki gibidir:  
  
-   İlk karakteri bir ASCII harf (büyük veya küçük harf), Unicode değişken adlandırma kuralları veya kısa çizgi (_) karakteri ile uyumlu bir harf olmalıdır. Bir sayı ilk karakter olarak kullanılan unutmayın.  
  
-   Sonraki karakterler harf, rakam veya alt çizgi (_) olmalıdır.  
  
-   Değişken adı olmamalıdır bir [ayrılmış sözcük](../javascript/reference/javascript-reserved-words.md).  
  
 Geçerli değişken adları bazı örnekleri şunlardır:  
  
```  
_pagecount   
Part9   
Number_Items   
```  
  
 Geçersiz değişken adları bazı örnekleri şunlardır:  
  
```JavaScript  
// Cannot begin with a number.   
99Balloons     
// The ampersand (&) character is not a valid character for variable names.   
Alpha&Beta   
```  
  
 Ne zaman, bir değişken bildirme ve bunu başlatmak istiyor, ancak istemiyorsanız herhangi bir değer verin, değer atamak `null`. Aşağıda bir örnek vardır.  
  
```JavaScript  
var bestAge = null;  
var muchTooOld = 3 * bestAge; // muchTooOld has the value 0.  
```  
  
 Bir değişkene bir değer atamadan bildirirseniz değerine sahip `undefined`. Aşağıda bir örnek vardır.  
  
```JavaScript  
var currentCount;  
// finalCount has the value NaN because currentCount is undefined.  
var finalCount = 1 * currentCount;   
```  
  
 `null` Değer 0, numarası gibi davranır ancak `undefined` özel değer gibi davranır `NaN` (sayı değil). Karşılaştırırsanız bir `null` değeri ve bir `undefined` değeri, bunlar eşit.  
  
 Bir değişken kullanmadan bildirebilir `var` anahtar sözcüğü bildirimi ve bir değere atayın. Bu örtük bir bildirimidir.  
  
```JavaScript  
// The variable noStringAtAll is declared implicitly.  
noStringAtAll = "";   
```  
  
 Hiçbir zaman bildirilmiş bir değişken kullanamazsınız.  
  
```JavaScript  
// Error. Length and width do not yet exist.  
var area = length * width;   
```  
  
## <a name="coercion"></a>Zorlama  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] C++ gibi güçlü şekilde yazılan diller aksine gevşek yazılmış bir dil değil. Bu, JavaScript değişkenleri önceden belirlenmiş bir tür olduğu anlamına gelir. Bunun yerine, bir değişkenin değerini türünü türüdür. Bu davranış, farklı bir tür değilmiş gibi bir değer kabul olanak sağlar.  
  
 İçinde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], bir özel duruma neden olmadan farklı türlerde değerler üzerinde işlemler gerçekleştirebilirsiniz. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] Yorumlayıcı örtük olarak dönüştürür, veya *olacak şekilde zorlar*, verileri biri, diğer türleri, sonra işlemi gerçekleştirir. Dize, sayı ve Boole değerleri zorlama için kurallar şunlardır:  
  
-   Sayı, bir sayı ve bir dize eklerseniz, bir dizeye yüklenen.  
  
-   Bir Boole değeri ve bir dize eklerseniz, Boole değeri dizeye yüklenen.  
  
-   Bir sayı ve bir Boole değeri eklerseniz, Boolean bir sayıya yüklenen.  
  
 Aşağıdaki örnekte, bir dize dize sonuçlarında bir sayı eklenir.  
  
```JavaScript  
var x = 2000;  
var y = "Hello";  
// The number is coerced to a string.  
x = x + y;  
document.write(x);   
  
// Output:  
// 2000Hello  
```  
  
 Dizeleri karşılaştırma amaçları için eşdeğer sayılara otomatik olarak dönüştürülür. Açıkça bir dizeyi bir tamsayıya dönüştürmek için kullanmak [parseInt işlevi](../javascript/reference/parseint-function-javascript.md). Açıkça bir dizeyi sayıya dönüştürme için kullanmak [parseFloat işlevi](../javascript/reference/parsefloat-function-javascript.md).