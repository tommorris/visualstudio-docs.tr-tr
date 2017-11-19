---
title: "Program akışı (JavaScript) denetimi | Microsoft Docs"
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
- Boolean values, program flow
- continue statement
- break statement
- control flow, about control flow
ms.assetid: 4ef58c82-e5d6-4b09-9458-cf0aa3b39bf5
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20c256d26c6991067d7c25c0c835eda6e5e5aac6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="controlling-program-flow-javascript"></a>Program Akışı Denetimi (JavaScript)
Normalde, deyimlerinde bir [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] betik birbiri ardından, bunlar yazılmış sırayla çalıştırılır. Bu sıralı yürütme olarak adlandırılır ve program akışı varsayılan yönü.  
  
 Alternatif sıralı yürütme için komut dosyanızı başka bir kısmına program akışı aktarır. Diğer bir deyişle, sonraki deyim sırayla yürütülen yerine başka bir ifade yerine yürütülür.  
  
 Bir komut dosyası kullanışlı hale getirmek için bu aktarım denetiminin mantıksal bir şekilde yapılmalıdır. Program denetim aktarımını sonucunu olduğu gerçeği deyimi bir karar temel (bir Boole değeri döndüren **true** veya **false**). Bir ifade oluşturun, sonra sonucunu doğru olup olmadığını sınamak. Bunu başarmak program yapıları iki ana tür vardır.  
  
 İlk seçim yapısıdır. Programınız (gibi bir yol olarak çatalı), bir birleşim oluşturmayı program akışının alternatif kurslar belirtmek için kullanın. Dört seçimi yapıları bulunan [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].  
  
-   tek seçim yapısı (**varsa**),  
  
-   çift seçimi yapısı (**IF/başka**),  
  
-   Satır içi Üçlü işleci`?:`  
  
-   Çoklu seçim yapısı (`switch`).  
  
 İkinci program denetim yapısı yineleme yapısı türüdür. Bir eylem bazı koşul true kalırken yinelenmesi olduğunu belirtmek için kullanın. Denetim deyimi koşullarını (genellikle bazı belirli sayıda yineleme sonra) sağlandığında, Denetim yineleme yapısı ötesinde next deyimi geçirir. Dört yineleme yapıları bulunan [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].  
  
-   ifade döngü üstünde test (`while`),  
  
-   ifade döngü alt kısmındaki test (**yapmak / while**),  
  
-   Her bir nesnenin özelliklerinde çalışır (**için/**).  
  
-   Sayaç denetlenen yineleme (**için**).  
  
 İç içe geçmiş ve yığın seçimi ve Yineleme denetim yapıları oldukça karmaşık kodlar oluşturabilirsiniz.  
  
 Yapılandırılmış program akışı üçüncü biçimi, bu belgede ele alınmayan özel durum işleme tarafından sağlanır.  
  
## <a name="using-conditional-statements"></a>Koşullu deyimler kullanma  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]destekleyen **varsa** ve [if... else](../javascript/reference/if-dot-dot-dot-else-statement-javascript.md) koşullu deyimler. İçinde **varsa** bir koşul test, ifadeler ve ilgili test koşulunu [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] kodu yürütüldüğünde. İçinde `if...else` deyimi, farklı kod koşulu test başarısız olursa yürütüldü. En basit biçimi bir **varsa** deyimi yazılabilir, tek bir çizgi ancak çok satırlı **varsa** ve `if...else` deyimleri çok daha yaygın.  
  
 Aşağıdaki örnekler ile birlikte kullanabileceğiniz sözdizimleri göstermek **varsa** ve `if...else` deyimleri. İlk örnek Boolean test basit türünü gösterir. Varsa (ve yalnızca aşağıdaki durumlarda) parantezler arasında öğe değerlendiren (veya için yüklenen) **true**, deyimi veya deyimleri sonra bloğunu **varsa** yürütülür.  
  
```JavaScript  
function GetReaction(newShip, color, texture, dayOfWeek)  
{  
   // The test succeeds if the newShip Boolean value is true.  
   if (newShip)  
   {  
      return "Champagne Bottle";  
   }  
  
   // The test succeeds if both conditions are true.  
   if (color == "deep yellow" && texture == "large and small wrinkles")  
   {  
      return "Is it a crenshaw melon?";  
   }  
  
   // The test succeeds if either condition is true.  
   if ((dayOfWeek == "Saturday") || (dayOfWeek == "Sunday"))  
   {  
      return "I'm off to the beach!";  
   }  
   else  
   {  
      return "I'm going to work.";  
   }  
}  
  
var reaction = GetReaction(false, "deep yellow", "smooth", "Sunday");  
document.write(reaction);  
  
// Output: I'm off to the beach!  
```  
  
## <a name="conditional-operator"></a>Koşullu işleç  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]Ayrıca bir örtük koşullu biçimini destekler. Sınanacak koşulu sonra bir soru işareti kullanır (word yerine **varsa** koşul önce). Değilse iki alternatifleri, bir koşul karşılandığında kullanılacak ve diğeri de belirtir. İki nokta, bu alternatifleri ayırmanız gerekir.  
  
```JavaScript  
var AMorPM = (theHour >= 12) ? "PM" : "AM";  
```  
  
 Birlikte sınanacak birkaç durum varsa ve başarılı veya başarısız diğerlerinden daha büyük olasılıkla olduğunu biliyorsanız, hız, betik yürütme işlemi için ' kısa devre değerlendirmesi' adlı bir özelliği kullanabilirsiniz. Zaman [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] mantıksal bir ifadeyi hesaplar yalnızca bir sonuç almak için gerektiği kadar alt ifadelerin değerlendirir.  
  
 Örneğin, bir ve ifade gibi varsa ((x == 123) & & (y 6 ==)), [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] önce x 123 olup olmadığını denetler. Değilse, y 6 eşit olsa bile, tüm ifade true olamaz. Bu nedenle, test y için hiçbir zaman yapılmış ve [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] değeri döndürür **false**.  
  
 Benzer şekilde, yalnızca birkaç koşullardan biri olması gerekir, **true** (kullanarak &#124; &#124; işleci), herhangi bir koşul test geçirir hemen durdurur test etme. İşlev çağrıları yürütülmesi veya diğer karmaşık ifadeler sınanacak koşulları gerektiriyorsa, bu etkilidir. Bu, yazma veya ifadeleri, en büyük olasılıkla koşullar koymak aklınızda **true** ilk. Ne zaman, yazma ve ifadeler, en büyük olasılıkla koşullar koymak **false** ilk.  
  
 Bu şekilde komut dosyanızı tasarlama bir faydası ise **runsecond()** varsa aşağıdaki örnekte çalıştırılmayacak **runfirst()** 0 döndürür.  
  
```JavaScript  
if ((runfirst() == 0) || (runsecond() == 0)) {  
    // some code  
}  
```  
  
## <a name="using-loops"></a>Döngüleri kullanma  
 Bir deyim veya deyimleri bloğunu tekrar tekrar yürütmek için birkaç yolu vardır. Genel olarak, yinelenen yürütme adlı *döngü* veya *yineleme*. Yineleme yalnızca tek bir yürütme döngüsü ' dir. Genellikle döngü değiştirilen her zaman değer çalıştırıldığı bir değişken, bir test tarafından kontrol edilir. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]Döngüler dört türlerini destekler: [için](../javascript/reference/for-statement-javascript.md) döngüler, [for... içinde](../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) döngüler, [sırada](../javascript/reference/while-statement-javascript.md) döngüler, [do... while](../javascript/reference/do-dot-dot-dot-while-statement-javascript.md) döngüler.  
  
## <a name="using-for-loops"></a>Döngüler için kullanma  
 **İçin** deyimi bir sayaç değişkeni, bir test durumu ve sayaç güncelleştiren bir eylem belirtir. Her döngü tekrarında önce koşulu test edilir. Test başarılı olursa, döngü içinde kod yürütülür. Test başarısız olursa, döngü içinde kod yürütülmedi ve program hemen döngü aşağıdaki kodu ilk satırda devam eder. Döngü yürütüldükten sonra sonraki yinelemeye başlamadan önce sayaç değişkeni güncelleştirilir.  
  
 Döngü için hiçbir zaman koşul varsa, döngü hiçbir zaman yürütülür. Test durumu her zaman karşılanıyorsa, sonsuz bir döngüde sonuçlanır. Eski belirli durumlarda arzu olabilir, ancak ikinci nadiren, döngü koşullarında yazılırken bu nedenle dikkatli olun.  
  
```JavaScript  
// The update expression ("icount++" in the following examples)  
// is executed at the end of the loop, after the block of  
// statements that forms the body of the loop is executed, and  
// before the condition is tested.  
  
// Set a limit of 10 on the loop.  
var howFar = 10;  
  
// Create an array called sum with 10 members, 0 through 9.  
var sum = new Array(howFar);  
sum[0] = 0;  
  
// Iterate from 0 through 9.  
var theSum = 0;  
for(var icount = 0; icount < howFar; icount++)  
{  
   theSum += icount;  
   sum[icount] = theSum;  
}  
  
// This code is not executed at all, because icount is not greater than howFar.  
var newSum = 0;  
for(var icount = 0; icount > howFar; icount++)  
{  
   newSum += icount;  
}  
  
// This is an infinite loop.  
var sum = 0;  
for(var icount = 0; icount >= 0; icount++)  
{  
   sum += icount;  
}  
```  
  
## <a name="using-forin-loops"></a>Kullanarak for... döngüler içinde  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]tüm kullanıcı tanımlı özelliklerini atlama için özel türde bir döngü sağlayan bir [nesne](../javascript/objects-and-arrays-javascript.md), veya bir dizinin tüm öğeleri. Döngü sayacında bir `for...in` döngü sayı olmayan bir dize değil. Geçerli özellik adını veya geçerli dizinin öğenin dizini içerir.  
  
```JavaScript  
// Create an object with some properties  
var myObject = new Object();  
myObject.name = "James";  
myObject.age = "22";  
myObject.phone = "555 1234";  
  
// Enumerate (loop through)_all the properties in the object  
for (var prop in myObject)  
{  
    // This displays "The property 'name' is James", etc.  
    document.write("The property '" + prop + "' is " + myObject[prop]);  
    // New line.  
    document.write("<br />");    
}  
```  
  
 Ancak `for...in` döngüler Ara VBScript için 's benzer `For Each...Next` döngüler, bunlar değil aynı şekilde çalışır. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] **For... Döngüdeki** özelliklerini tekrarlanan [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] nesneleri. VBScript **For Each... Sonraki** döngü tekrarlanan bir koleksiyondaki öğelerin üzerinden. Koleksiyonlar üzerinden döngü [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], kullanmanız gereken [Numaralandırıcı nesnesi](../javascript/reference/enumerator-object-javascript.md) nesne veya varsa, `forEach` koleksiyon nesnesinin yöntemi. Internet Explorer'da olanlar gibi bazı nesneler hem VBScript desteklese **For Each... Sonraki** döngü ve [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] **for... içinde** döngü, çoğu nesneyi yapın.  
  
## <a name="using-while-loops"></a>While döngülerini kullanma  
 A `while` döngü benzer bir **için** döngü. Fark vardır, bir `while` döngü yerleşik sayaç değişkeni veya güncelleştirme ifade sahip değil. Bir deyim veya deyimleri bloğunu yinelenen yürütülmesi denetlemek istediğiniz, ancak daha fazla karmaşık bir "Bu kodu n kez çalıştır" daha basit kural, kullanmak bir `while` döngü. Aşağıdaki örnek, Internet Explorer nesne modeli kullanır ve bir `while` kullanıcı basit bir soru sormak için döngü.  
  
```JavaScript  
var x = 0;  
while ((x != 5) && (x != null))  
{  
    x = window.prompt("What is my favorite number?", x);  
}  
  
if (x == null)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```  
  
> [!NOTE]
>  Çünkü `while` döngüler açık yerleşik sayacı değişkeni sahip değil ve sonsuz döngüler diğer türleri döngü daha savunmasız. Burada veya ne zaman döngü koşulunu güncelleştirilir bulmak mutlaka kolay olduğundan, ayrıca, yazmak kolaydır bir `while` Döngü koşulu hiçbir zaman güncelleştirildiği içinde. Tasarlarken, bu nedenle, dikkatli olmalıdır `while` döngüler.  
  
 Yukarıda belirtildiği gibi yok ayrıca bir **do... while** içinde döngü [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] while benzer olan koşul döngü sonunda yerine başlangıç test bu yana her zaman en az bir kez çalıştırılacak garanti dışında döngü . Örneğin, yukarıdaki döngü olarak yeniden yazılı olabilir:  
  
```JavaScript  
var x = 0;  
do  
{  
    x = window.prompt("What is my favorite number?", x);  
} while ((x != 5) && (x != null));  
  
if (x == null)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```  
  
## <a name="using-break-and-continue-statements"></a>Bölme ve deyimleri devam kullanarak  
 İçinde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], [sonu](../javascript/reference/break-statement-javascript.md) deyimi bir döngü yürütmeyi durdurmak için kullanılan bazı koşul karşılandığında. (Unutmayın **sonu** da çıkmak için kullanılan bir `switch` blok). [Devam](../javascript/reference/continue-statement-javascript.md) deyimi, döngü ise sayaç değişkeni güncelleştirilirken kod bloğu kalan atlanıyor sonraki yinelemeye hemen atlamak için kullanılabilir bir **için** veya `for...in` döngü.  
  
 Aşağıdaki örnek kullanmak için önceki örnekte derlemeler **sonu** ve **devam** deyimleri döngü denetlemek için.  
  
```JavaScript  
var x = 0;  
do  
{  
    x = window.prompt("What is my favorite number?", x);  
  
    // Did the user cancel? If so, break out of the loop  
    if (x == null)  
        break;  
  
    // Did they enter a number?  
    // If so, no need to ask them to enter a number.  
    if (Number(x) == x)  
        continue;  
  
    // Ask user to only enter in numbers  
    window.alert("Please only enter in numbers!");  
  
} while (x != 5)  
  
if (x != 5)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```