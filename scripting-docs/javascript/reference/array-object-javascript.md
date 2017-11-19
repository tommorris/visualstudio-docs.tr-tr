---
title: Dizi nesnesi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Array
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Array object
- constructor property
ms.assetid: 08e5f552-0797-4b48-8164-609582fc18c9
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a48d0ab5bac9d532e8fe8e356f4ea4df9e377b02
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="array-object-javascript"></a>Dizi Nesnesi (JavaScript)
Herhangi bir veri türünden dizilerin oluşturulmasına destek sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
arrayObj = new Array()  
arrayObj = new Array([size])  
arrayObj = new Array([element0[, element1[, ...[, elementN]]]])  
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Değişken adına `Array` nesne atanır.  
  
 `size`  
 İsteğe bağlı. Dizinin boyutu. Diziler sıfır tabanlı olarak oluşturulan öğeleri sıfıra dizinlerden sahip `size` -1.  
  
 `element0,...,elementN`  
 İsteğe bağlı. Diziye yerleştirilecek öğeler. Bu bir dizi oluşturur  *n*  + 1 öğeleri ve `length` ,  *n*  + 1. Bu söz dizimini kullanarak, birden çok öğe sağlamalısınız.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dizi oluşturulduktan sonra dizinin öğelerine [ ] işaretiyle tek tek erişebilirsiniz. İçindeki diziler Not [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] sıfır tabanlıdır.  
  
```JavaScript  
var my_array = new Array();  
for (i = 0; i < 10; i++) {  
    my_array[i] = i;  
}  
x = my_array[4];  
document.write(x);  
  
// Output: 4  
```  
  
 İşaretsiz bir 32 bit tamsayı geçirebilirsiniz `Array` Oluşturucusu dizinin boyutunu belirtin. Değer negatif ise ya da tamsayı değil ise, bir çalışma zamanı hatası oluşur. Eğer aşağıdaki kodu çalıştırırsanız, Konsolda bu hatayı görürsünüz.  
  
```JavaScript  
var arr = new Array(10);  
document.write(arr.length);  
  
// Output: 10  
  
// Don't do this  
var arr = new Array(-1);  
arr = new Array(1.50);   
```  
  
 Tek bir değer için aktarılırsa `Array` oluşturucusu ve değil bir sayı `length` özelliğini 1 olarak ayarlayın ve tek, geçilen bağımsız değişken yalnızca öğesinin değeri olur.  
  
```npl  
var arr = new Array("one");  
document.write(arr.length);  
document.write("<br/>");  
document.write(arr[0]);  
  
// Output:  
1  
one  
  
```  
  
 JavaScript dizileri seyrek dizilerdir, yani bir dizideki her öğe veri içermeyebilir. JavaScript'te, dizi içinde yalnızca veri içeren öğeler mevcuttur. Bu, dizi tarafından kullanılan bellek miktarını azaltır.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 Aşağıdaki listelerin bazı üyeleri daha sonraki sürümlerde eklendi. Daha fazla bilgi için bkz: [sürüm bilgilerini](../../javascript/reference/javascript-version-information.md) veya tek tek üyeleri belgelerine.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `Array` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[constructor özelliği](../../javascript/reference/constructor-property-array.md)|Bir diziyi oluşturan işlevi belirtir.|  
|[length özelliği (dizi)](../../javascript/reference/length-property-array-javascript.md)|Bir dizide tanımlı en yüksek öğeden bir daha fazla bir tamsayı değeri döndürür.|  
|[prototype özelliği](../../javascript/reference/prototype-property-array.md)|Bir dizi için prototipe bir başvuru döndürür.|  
  
## <a name="functions"></a>İşlevler  
 Aşağıdaki tabloda, işlevleri açıklanmaktadır `Array` nesnesi.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[Array.From işlevi](../../javascript/reference/array-from-function-array-javascript.md)|Bir dizi bir dizi benzeri veya iterable nesnesinden döndürür.|  
|[Array.isArray işlevi](../../javascript/reference/array-isarray-function-javascript.md)|Bir nesnenin bir dizi olup olmadığını belirten bir Boolean değeri döndürür.|  
|[Array.of işlevi](../../javascript/reference/array-of-function-array-javascript.md)|Geçirilen bağımsız değişkenlerden bir dizi döndürür.|  
  
<a name="js56jsobjarraymeth"></a>   
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Array` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[concat yöntemi (dizi)](../../javascript/reference/concat-method-array-javascript.md)|İki dizinin birleşimi olan yeni bir dizi döndürür.|  
|[Entries yöntemi](../../javascript/reference/entries-method-array-javascript.md)|Dizi anahtar/değer çiftleri içeren bir yineleyici döndürür.|  
|[every yöntemi](../../javascript/reference/every-method-array-javascript.md)|Tanımlanan geri çağırma işlevi döndürüp döndürmediğini denetler `true` dizisindeki tüm öğeler için.|  
|[fill yöntemi](../../javascript/reference/fill-method-array-javascript.md)|Belirli bir değerle bir dizi doldurur.|  
|[filter yöntemi](../../javascript/reference/filter-method-array-javascript.md)|Bir dizinin her öğesi tanımlanmış geri çağırma işlevini çağırır ve geri çağırma işlevi döndüğü değerleri bir dizi döndürür `true`.|  
|[findIndex yöntemi](../../javascript/reference/findindex-method-array-javascript.md)|Sınama geri çağırma fonksiyonu içinde belirtilen ölçütleri karşılar ilk dizi öğesi için bir dizin değeri döndürür.|  
|[forEach yöntemi](../../javascript/reference/foreach-method-array-javascript.md)|Bir dizideki her öğe için tanımlı geri çağırma işlevini çağırır.|  
|[hasOwnProperty yöntemi](../../javascript/reference/hasownproperty-method-object-javascript.md)|Bir nesnenin belirtilen adda bir özelliği olup olmadığını belirten bir Boolean değer döndürür.|  
|[indexOf yöntemi (dizi)](../../javascript/reference/indexof-method-array-javascript.md)|Bir dizi içinde bir değerin ilk geçtiği dizini döndürür.|  
|[isPrototypeOf yöntemi](../../javascript/reference/isprototypeof-method-object-javascript.md)|Bir nesnenin başka bir nesnenin prototip zincirinde mevcut olup olmadığını belirten bir Boolean değer döndürür.|  
|[join yöntemi](../../javascript/reference/join-method-array-javascript.md)|Döndürür bir `String` birlikte birleştirilmiş bir dizi tüm öğelerinden oluşan nesne.|  
|[keys yöntemi](../../javascript/reference/keys-method-array-javascript.md)|Dizinin dizin değerleri içeren bir yineleyici döndürür.|  
|[lastIndexOf yöntemi (dizi)](../../javascript/reference/lastindexof-method-array-javascript.md)|Bir dizi içinde bir belirtilen değerin son geçtiği dizini döndürür.|  
|[map yöntemi](../../javascript/reference/map-method-array-javascript.md)|Bir dizideki her öğe için tanımlı geri çağırma işlevini çağırır ve sonuçları içeren bir dize döndürür.|  
|[pop yöntemi](../../javascript/reference/pop-method-array-javascript.md)|Bir diziden son öğeyi kaldırır ve döndürür.|  
|[Propertyısenumerable yöntemi](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Belirtilen bir özelliğin bir nesnenin parçası olup olmadığını ve numaralandırılabilir olup olmadığını belirten bir Boolean değer döndürür.|  
|[push yöntemi](../../javascript/reference/push-method-array-javascript.md)|Bir diziye yeni öğeler ekler ve dizinin yeni uzunluğunu döndürür.|  
|[reduce yöntemi](../../javascript/reference/reduce-method-array-javascript.md)|Bir dizideki tüm öğelerde tanımlı bir geri çağrı işlevini çağırıp tek bir sonuç biriktirir. Geri çağrı işlevinin dönüş değeri biriken sonuçtur ve geri çağrı işlevine yapılan sonraki çağrıda bir bağımsız değişken olarak sağlanır.|  
|[reduceRight yöntemi](../../javascript/reference/reduceright-method-array-javascript.md)|Bir dizideki tüm öğelerde tanımlı bir geri çağrı işlevini çağırıp tek bir sonuç biriktirir, ancak bunu azalan sırada gerçekleştirir. Geri çağrı işlevinin dönüş değeri biriken sonuçtur ve geri çağrı işlevine yapılan sonraki çağrıda bir bağımsız değişken olarak sağlanır.|  
|[reverse yöntemi](../../javascript/reference/reverse-method-javascript.md)|Döndürür bir `Array` öğeleri nesnesiyle tersine.|  
|[shift yöntemi](../../javascript/reference/shift-method-array-javascript.md)|Bir diziden ilk öğeyi kaldırır ve döndürür.|  
|[slice yöntemi (dizi)](../../javascript/reference/slice-method-array-javascript.md)|Dizinin bir bölümünü döndürür.|  
|[Some yöntemi](../../javascript/reference/some-method-array-javascript.md)|Tanımlanan geri çağırma işlevi döndürüp döndürmediğini denetler `true` dizi herhangi bir öğe için.|  
|[sort yöntemi](../../javascript/reference/sort-method-array-javascript.md)|Döndürür bir `Array` sıralanmış öğelerle nesnesi.|  
|[splice yöntemi](../../javascript/reference/splice-method-array-javascript.md)|Bir diziden öğeleri kaldırır, ve gerekirse, yerlerine yeni öğeler ekleyerek silinen öğeleri döndürür.|  
|[toLocaleString yöntemi](../../javascript/reference/tolocalestring-method-object-javascript.md)|Geçerli yerel ayarı kullanarak bir dize döndürür.|  
|[toString yöntemi](../../javascript/reference/tostring-method-array.md)|Bir dizinin dize gösterimini döndürür.|  
|[unshift yöntemi](../../javascript/reference/unshift-method-array-javascript.md)|Bir dizinin başlangıcına yeni öğeler ekler.|  
|[valueOf yöntemi](../../javascript/reference/valueof-method-array.md)|Diziye bir başvuru alır.|  
|[values yöntemi](../../javascript/reference/values-method-array-javascript.md)|Dizi değerleri içeren bir yineleyici döndürür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaydırma, kaydırma ve yakınlaştırma örnek uygulaması](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)