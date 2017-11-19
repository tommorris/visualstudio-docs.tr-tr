---
title: "İşlevler (JavaScript) | Microsoft Docs"
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
helpviewer_keywords: intrinsic JavaScript functions
ms.assetid: e2a72b5a-3edd-43d8-95e8-91721b38c1c1
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd5626af6417b5f0010545874bd15c86b30a303a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="functions-javascript"></a>İşlevler (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]İşlevler eylemleri gerçekleştirmek; Ayrıca değerleri geri dönebilirsiniz. Bazen hesaplamalar veya karşılaştırmaları sonuçlarını bunlar. İşlevler "Genel yöntemler" da denir.  
  
 İşlevler bir ad altında çeşitli işlemleri birleştirin. Bu, kodunuzu kolaylaştırmak sağlar. Deyimleri bir dizi yazma, adlandırın ve sonra onu çağırma ve kendisine, gereken herhangi bir bilgi geçirme ayarlamak tüm yürütün.  
  
 İşlev adından sonra parantez içinde bilgileri kapsayan tarafından bir işleve bilgi geçirin. Bir işleve bilgi parçalarını değişkenler veya parametreler denir. Başkalarının bağımsız değişkenlerden biri veya daha fazla alırken bazı işlevler tüm bağımsız değişkenleri hiç kazanmaz. Bazı işlevler, bağımsız değişken sayısı nasıl işlevini kullanarak bağlıdır.  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]iki tür işlevleri destekler: dilinde yerleşik olanlar ve olanlar kendiniz oluşturun.  
  
## <a name="built-in-functions"></a>Yerleşik işlevler  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] Dili birkaç yerleşik işlevler içerir. Bazı başkalarının sayısal değerlere dizeleri dönüştürme sırasında ifadeleri ve özel karakterler işlemenize olanak tanır.  
  
 Bkz: [JavaScript yöntemleri](../javascript/reference/javascript-methods.md) bu yerleşik işlevler hakkında bilgi için.  
  
## <a name="creating-your-own-functions"></a>Kendi işlevler oluşturma  
 Kendi işlevleri oluşturabilir ve bunları gerektiğinde. Function deyimi ve bloğunu işlev tanımı oluşan [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] deyimleri.  
  
 **CheckTriplet** aşağıdaki örnekte işlev bağımsız değişkenleri olarak bir üçgen tarafının uzunlukları alır. Bunlardan üç sayıları (sağ üçgen hipotenüsü uzunluğu kare diğer iki kenarı uzunluklarının kareler toplamı eşit olan) bir Pisagor Üçlü oluşturan olup olmadığını kontrol ederek üçgen dik üçgen olup hesaplama . CheckTriplet işlevi gerçek testi yapmak için iki işlevleri birini çağırır.  
  
 Çok küçük bir sayı ("epsilon") kullanımını test kayan nokta sürümünde test değişken olarak dikkat edin. Uncertainties ve kayan nokta hesaplamalarında yuvarlama hataları nedeniyle, tüm üç değerden söz konusu tamsayılar olduğu bilinen sürece Pisagor Üçlü üç sayı olup olmadığını oluşturur, doğrudan bir test yapmak mümkün değil. Doğrudan test daha doğru olduğundan, bu örnekteki kod, uygun olan ve ise, onu kullanır, belirler.  
  
```JavaScript  
var epsilon = 0.00000000001; // Some very small number to test against.  
  
// The test function for integers.  
function integerCheck(a, b, c)   
{  
   // The test itself.  
   if ( (a*a) == ((b*b) + (c*c)) )     
      return true;  
  
   return false;  
} // End of the integer checking function.  
  
// The test function for floating-point numbers.  
function floatCheck(a, b, c)     
{  
   // Make the test number.  
   var delta = ((a*a) - ((b*b) + (c*c)))  
  
   // The test requires the absolute value  
   delta = Math.abs(delta);  
  
   // If the difference is less than epsilon, then it's pretty close.  
   if (delta < epsilon)     
      return true;  
  
   return false;  
} // End of the floating-poing check function.  
  
// The triplet checker.   
function checkTriplet(a, b, c)  
{   
   // Create a temporary variable for swapping values  
   var d = 0;   
  
   // First, move the longest side to position "a".  
  
   // Swap a and b if necessary  
   if (b > a)  
   {  
      d = a;  
      a = b;  
      b = d;  
   }  
  
   // Swap a and c if necessary  
   if (c > a)  
   {  
      d = a;  
      a = c;  
      c = d;  
   }  
  
   // Test all 3 values. Are they integers?  
   if (((a % 1) == 0) && ((b % 1) == 0) && ((c % 1) == 0))  
   {   
      // If so, use the precise check.  
      return integerCheck(a, b, c);   
   }  
   else  
   {  
      // If not, get as close as is reasonably possible.  
      return floatCheck(a, b, c);   
   }  
} // End of the triplet check function.  
  
// The next three statements assign sample values for testing purposes.  
var sideA = 5;  
var sideB = 5;  
var sideC = Math.sqrt(50.001);  
  
// Call the function. After the call, 'result' contains the result.  
var result = checkTriplet(sideA, sideB, sideC);  
```  
  
<a name="Arrow"></a>   
## <a name="arrow-functions"></a>Ok işlevleri  
 Ok işlev sözdizimi, `=>`, adsız bir işlev belirterek, bir toplu yöntem sağlar. Ok işlev sözdizimi şöyledir.  
  
```JavaScript  
([arg] [, arg]) => {  
    statements  
}  
```  
  
 İşleve bağımsız değişkenler tarafından parantez içine alınması, oku solundaki değerlerini belirtin. Tek bir bağımsız değişken işlevine parantez gerektirmez. Bağımsız değişken olarak geçirilen parantez gereklidir. İşlev tanımı oku sağındaki ya da bir deyim gibi olabilir `v + 1`, veya kaşlı ayraç ({}) içine deyimleri bloğu.  
  
> [!IMPORTANT]
>  Ok işlev sözdizimi yalnızca desteklenen [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)].  
  
 Kullanamazsınız `new` olan bir ok işlevi işleci.  
  
 Aşağıdaki kod örnekleri işlev tanımları ifadelerle ok işlevi kullanımını gösterir. İlk örnekte v içinde bağımsız değişken olarak ifade geçirilir. İkinci örnekte v ve i geçirilen bağımsız değişken olarak ifade.  
  
```  
var evens = [2, 4, 6, 8];  
  
// Using standard syntax.  
var odds = evens.map(function(v) { return v + 1; });  
  
// Using arrow function syntax.  
// Add one to each value to produce output.  
var odds = evens.map(v => v + 1);  
  
// The following line of code adds the index value to the passed  
// in value to produce output.  
// Note: the second argument to the callback function in the map   
// method is the index value (i).  
var nums = evens.map((v, i) => v + i);  
  
console.log(odds);  
console.log(nums);  
  
// Output:  
// [object Array] [3, 5, 7, 9]  
// [object Array] [2, 5, 8, 11]  
```  
  
 Aşağıdaki kod örneğinde deyimi blok ok işleviyle kullanımını göstermektedir.  
  
```JavaScript  
var fives = new Array();  
  
// Statement block, re-using nums array from previous example.  
// Note: The first argument to the callback function in forEach  
// is the value of the array element (v).  
nums.forEach(v => {  
  if (v % 5 === 0)  
    fives.push(v);  
});  
  
console.log(fives);  
  
// Output:  
// [object Array] [5]  
```  
  
 Standart İşlevler, ok işlevleri aynı sözcük paylaşmak `this` nesnesi gibi geçici çözümler gereksinimini ortadan kaldırmak için kullanılan çevresindeki kod olarak `var self = this;`.  
  
 Aşağıdaki örnek, değerini gösterir `this` nesnesi ok işlevi içinde aynıdır çevresindeki kod (hala başvurduğu `bob` değişkeni.  
  
```JavaScript  
var bob = {  
  _name: "Bob",  
  _friends: ["Pete", "Joe", "Larry"],  
  printFriends() {  
    this._friends.forEach(f =>  
      console.log(this._name + " knows " + f));  
  }  
}  
  
// Output:  
// Bob knows Pete  
// Bob knows Joe  
// Bob knows Larry  
```  
  
 Ok işlevleri de paylaşmak aynı sözcük `arguments` nesnesi çevresindeki kod olarak (olduğu gibi `this` nesnesi).  
  
<a name="Default"></a>   
## <a name="default-parameters"></a>varsayılan parametreleri  
 Bir başlangıç değeri atayarak bir işlevde parametre için varsayılan bir değer belirtebilirsiniz. Varsayılan değer, sabit bir değer veya ifade olabilir.  
  
> [!IMPORTANT]
>  Varsayılan parametreler yalnızca desteklenir [!INCLUDE[jsv12textExp](../javascript/includes/jsv12textexp-md.md)].  
  
 Aşağıdaki örnekte, y, varsayılan değer 10'dur ve z varsayılan değer 20'dir. Arayan farklı bir değer geçirir (veya tanımsız sürece) ikinci bağımsız değişkenle işlevi y değeri olarak 10 kullanın. Arayan farklı bir değer geçirir (veya tanımsız sürece) üçüncü bağımsız değişken olarak işlevi 20 z değeri olarak kullanın.  
  
```JavaScript  
var val = 20;  
  
function f(x, y=10, z=val) {  
  return x + y + z;  
}  
  
console.log(f(3));  
console.log(f(3, 3));  
console.log(f(3, 3, 3));  
  
// Output:  
// 33  
// 26  
// 9  
```  
  
<a name="Rest"></a>   
## <a name="rest-parameters"></a>REST parametreleri  
 Rest parametreler, forma işleci () tarafından belirtilen bir işlev çağrısı bir dizi ardışık bağımsız değişkenleri açmanızı sağlar.  
  
 REST parametreleri gereksinimini ortadan `arguments` nesnesi. REST parametreleri farklı `arguments` gibi çeşitli yollarla nesnesi:  
  
-   Rest parametresi gerçek dizi örneğidir ve bu nedenle bir dizisinde gerçekleştirilen işlemleri destekler.  
  
-   Bir rest parametresi içinde ayrı (adlandırılmış) bağımsız değişken olarak geçirilen değil yalnızca ardışık bağımsız değişkenlerini içerir (buna karşılık, `arguments` nesne işlevdeki geçirilen tüm değişkenleri içerir).  
  
> [!IMPORTANT]
>  REST parametreleri ve forma işleci desteklenir yalnızca [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)].  
  
 Aşağıdaki kod örneğinde "hello" ve doğru dizi değerler olarak geçirilen ve y parametresinde depolanır. Rest parametresi işlevinin son parametresi olmalıdır.  
  
```JavaScript  
function f(x, ...y) {  
  // y is an array.  
  return x * y.length;  
}  
  
console.log(f(3, "hello", true));  
  
// Output:  
// 6  
  
```  
  
 Forma işleci ek kullanımlar bkz [yayılan işleci](../javascript/reference/spread-operator-decrement-dot-dot-dot-javascript.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript dil başvurusu](../javascript/javascript-language-reference.md)