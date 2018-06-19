---
title: JavaScript kodu yazma | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.htmldesigner.html
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- code, JavaScript syntax
- comments, JavaScript code
- JavaScript code
ms.assetid: dde28266-0d0f-4460-a819-f931cf0911ad
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e50bc25f818724b59d9adda51f97d76ae14de2b4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792200"
---
# <a name="writing-javascript-code"></a>JavaScript Kodu Yazma
Gibi birçok diğer programlama dilleri, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] deyime deyimleri ve açıklamaların ilgili kümesi oluşan blokları düzenlenmiştir. Deyimi içinde değişkenleri, dizeler, sayılar ve ifadeler kullanabilirsiniz.  
  
## <a name="statements"></a>Deyimler  
 A [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] program deyimleri koleksiyonudur. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]deyimleri ifadeleri tam bir görevi gerçekleştirmek şekilde birleştirin.  
  
 Bir deyimi bir veya daha fazla ifadeler, anahtar sözcükleri veya işleçleri (simge) oluşur. Genellikle, bir ifade iki veya daha fazla satır yazılabilir olsa da bir deyim tek bir satıra yazılır. Ayrıca, noktalı virgülle ayırarak iki veya daha fazla deyimleri, aynı satırda'e yazılabilir. Genel olarak, her yeni satır yeni bir sistem başlar. Deyimleri açıkça sonlandırmak için iyi bir fikirdir. Olan noktalı virgül (;), bunu [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] deyimi sonlandırma karakter.  
  
 İki örnekleri şunlardır [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] deyimleri. Sonra tümcelerin / / karakterler *açıklamaları*, programı açıklayıcı açıklamalar şunlardır.  
  
```JavaScript  
var aBird = "Robin"; // Assign the text "Robin" to the variable aBird.  
var today = new Date(); // Assign today's date to the variable today.  
```  
  
 Bir grup [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] kaşlı ayraç ({}) çevrelenmiş deyimleri adlı bir *blok*. Blok gruplanmış ifadeler genellikle tek bir deyimde işlenebilir. Bu blokları kullanabileceğiniz anlamına gelir çoğunda yerleştirir [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] tek bir deyimde bekliyor. İstisnalarla dahil başlıklarını **için** ve `while` döngüler. Tek deyimleri bloğu içinde noktalı end, ancak blok dikkat edin.  
  
 Genellikle, bloklar işlevler ve koşulları kullanılır. C++ ve bazı diğer diller aksine dikkat [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] yoksa yeni bir kapsam olması için bir blok dikkate almaz; yalnızca yeni kapsam oluşturma işlevleri.  
  
 Aşağıdaki örnekte, `else` yan tümcesi kaşlı ayraç çevrelenen iki deyimlerinin bir blok içerir. Blok tek bir deyimde kabul edilir. Ayrıca, kaşlı ayraç çevrelenen deyimleri bloğunun işlevi oluşur. İşlevi aşağıda deyimleri bloğunun dışında ve bu nedenle işlev tanımının bir parçası değil.  
  
```JavaScript  
function inchestometers(inches)  
   {  
   if (inches < 0)  
      return -1;  
   else  
      {  
      var meters = inches / 39.37;  
      return meters;  
      }  
   }  
  
var inches = 12;  
var meters = inchestometers(inches);  
document.write("the value in meters is " + meters);  
```  
  
## <a name="comments"></a>Açıklamalar  
 Tek satırlı [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] açıklama eğik çifti ile başlar (/ /). Tek satırlı yorum bir örneği burada verilmiştir.  
  
```JavaScript  
var aGoodIdea = "Comment your code thoroughly."; // This is a single-line comment.  
```  
  
 Çok satırlı [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] açıklama başlayan bir eğik çizgi ve yıldız işareti (/\*) ve geriye doğru ile sona erer (\*/).  
  
```JavaScript  
/*  
This is a multiline comment that explains the preceding code statement.  
  
The statement assigns a value to the aGoodIdea variable. The value,   
which is contained between the quote marks, is called a literal. A   
literal explicitly and directly contains information; it does not   
refer to the information indirectly. The quote marks are not part   
of the literal.  
*/  
```  
  
> [!NOTE]
>  İçinde başka bir çok satırlı açıklaması ekleme çalışırsanız [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] beklenmeyen bir biçimde ortaya çıkan çok satırlı açıklaması yorumlar. * / Katıştırılmış sonunu işaretler çok satırlı açıklaması tüm çok satırlı açıklaması ucu olarak yorumlanır. Katıştırılmış çok satırlı açıklaması izleyen metni çıkışı açıklanır değil Bu anlamına gelir; Bunun yerine, onu olarak yorumlanacak [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] kod ve sözdizimi hataları oluşturur.  
  
 Tüm yorumlarınızı tek satırlı yorumlar taşı olarak yazma önerilir. Bu, kodunun büyük kesimleri ile çok satırlı yorum daha sonra açıklama olanak sağlar.  
  
```JavaScript  
// This is another multiline comment, written as a series of single-line comments.  
// After the statement is executed, you can refer to the content of the   
// aGoodIdea variable by using its name.  
var extendedIdea = aGoodIdea + " You never know when you'll have to figure out what it does.";  
```  
  
## <a name="assignments-and-equality"></a>Atamalar ve eşitlik  
 Eşittir (=) kullanılan [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] deyimleri değişkenlere değerler atayın: atama işleç değil. Sol işleneni = işleç olarak her zaman bir Lvalue. Lvalues örnekleri şunlardır:  
  
-   değişkenleri  
  
-   Dizi öğeleri  
  
-   Nesne Özellikleri.  
  
 Sağ işleneni, = işleç olarak her zaman bir Rvalue. Rvalues herhangi bir türde bir ifadenin değerini de dahil olmak üzere, rasgele bir değer olabilir. Bir örneği burada verilmiştir bir [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] atama ifadesi.  
  
```JavaScript  
var anInteger = 3;  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] Derleyici yorumlar Bu deyimde anlamı: "3 değişkenine değer atamak için **anInteger**," veya "**anInteger** 3 değerini alır."  
  
 Arasındaki farkı anladığınızdan emin olun = işleci (ataması) ve == işleci (eşitlik). İki değerin eşit olup olmadığını öğrenmek için karşılaştırmak istediğiniz zaman, iki eşittir işareti (==) kullanın. Bu ayrıntılı olarak ele alınmıştır [denetleme Program akış](../javascript/controlling-program-flow-javascript.md).  
  
## <a name="expressions"></a>İfadeler  
 A [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] ifade değeri herhangi biri geçerli olabilir [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] tür - bir sayı, bir dize, bir nesne ve benzeri. Değişmez değerler basit ifadelerini. Bazı örnekler şunlardır [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] sabit ifadeler.  
  
```JavaScript  
3.9                       // numeric literal  
"Hello!"                  // string literal  
false                     // boolean literal  
null                      // literal null value  
{x:1, y:2}                // Object literal  
[1,2,3]                   // Array literal  
function(x){return x*x;}  // function literal  
```  
  
 Daha karmaşık ifadeler değişkenleri, işlev çağrılarını ve diğer ifadeleri içerebilir. İşleçleri kullanarak karmaşık ifadeler oluşturmak için ifadeler birleştirebilirsiniz. İşleçler örnekleri şunlardır: `+` (toplama), `-` (çıkarma), `*` (çarpma) ve `/` (bölme).  
  
 Bazı örnekler şunlardır [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] karmaşık ifadeler.  
  
```JavaScript  
var anExpression = 3 * (4 / 5) + 6;  
var aSecondExpression = Math.PI * radius * radius;  
var aThirdExpression = aSecondExpression + "%" + anExpression;  
var aFourthExpression = "(" + aSecondExpression + ") % (" + anExpression + ")";  
```