---
title: "Kopyalama, geçirme ve karşılaştırma (JavaScript) veri | Microsoft Docs"
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
- arrays [Visual Studio], passing values
- function parameters
- string comparison
- function parameters, about function parameters
- ByRef argument
- arrays [Visual Studio], setting data types
- arrays [Visual Studio], copying data
- ByVal argument
- string comparison, testing data
ms.assetid: fbccd877-7249-45d4-bd9f-6bcd8ba94a6b
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c3cf980ca1dfd0c0e09871b6de9756cb2a10364b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="copying-passing-and-comparing-data-javascript"></a>Veri Kopyalama, Geçirme ve Karşılaştırma (JavaScript)
İçinde [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)], verilerin nasıl işlendiğini kendi veri türüne bağlıdır.  
  
## <a name="by-value-vs-by-reference"></a>Tarafından değeri vs. Başvuruya göre  
 Sayılar ve Boole değerleri (**true** ve **false**) kopyalar, geçirilen ve karşılaştırıldığında *değeriyle*. Değere göre kopyaladığınızda veya geçirdiğinizde bilgisayar belleğinde bir yer ayırın ve özgün değeri buraya kopyalayın. Sonra özgün değeri değiştirirseniz, artık iki ayrı varlık olduğundan kopya değer etkilenmez (veya tam tersi).  
  
 Nesneleri, dizileri ve işlevleri kopyalar, geçirilen ve karşılaştırıldığında *başvuruya göre*. Başvuruya göre kopyaladığınızda veya geçirdiğinizde aslında özgün öğeye işaretçi oluşturmuş ve işaretçiyi kopyaymış gibi kullanmış olursunuz. Özgün değeri daha sonra değiştirirseniz, hem özgün, hem de kopya değeri değiştirmiş olursunuz (veya tam tersi). Gerçekte yalnız bir varlık vardır; "kopya" aslında bir kopya değil, sadece verilere başka bir başvurudur.  
  
 Başvuru ile karşılaştırıldığında, karşılaştırmanın başarılı olması için iki değişken tam olarak aynı varlığa başvurmalıdır. Örneğin, iki farklı **dizi** nesneleri her zaman karşılaştırmak eşit olmayan aynı öğeler içeriyorsa bile. Karşılaştırmanın başarılı olması için değişkenlerden biri diğerine bir başvuru olmalıdır. İki dizisi aynı öğeleri tutmak ise denetlemek için sonuçlarını karşılaştırın **toString()** yöntemi.  
  
 Son olarak, dizeler başvuruya göre kopyalanır ve geçirilir, fakat değere göre karşılaştırılır. İki varsa unutmayın **dize** nesneleri (ile oluşturulan **yeni** String("something")), başvuruya göre karşılaştırılır, ancak bir veya iki değer bir dize değeri ise değeriyle karşılaştırılır.  
  
> [!NOTE]
>  ASCII ve ANSI karakterler kümelerinin oluşturulma biçimi nedeniyle sıralı düzende büyük harfler küçük harflerden önce gelir. Örneğin, "Zoo" olarak karşılaştırır *daha az* daha "aardvark." Çağırabilirsiniz **toUpperCase()** veya **toLowerCase()** küçük harf olarak eşleşen gerçekleştirmek istiyorsanız, her iki dizelerde.  
  
## <a name="passing-parameters-to-functions"></a>Parametreleri İşlevlere Geçirme  
 Bir parametreyi değerine göre bir işleve geçirdiğinizde, bu parametrenin yalnızca işlev içinde bulunan ayrı bir kopyasını yaparsınız. Nesneler ve diziler başvuruya göre geçirilse de işlevin içinde yeni bir değer üzerine doğrudan yazarsanız, yeni değer işlev dışında yansıtılmaz. Sadece nesnelerin özelliklerine veya dizilerin öğelerine yapılan değişiklikler işlevin dışında görülebilir durumdadır.  
  
 Örneğin (Internet Explorer nesne modelini kullanarak):  
  
```JavaScript  
// This clobbers (over-writes) its parameter, so the change  
// is not reflected in the calling code.  
function Clobber(param)   
{  
    // clobber the parameter; this will not be seen in   
    // the calling code  
    param = new Object();  
    param.message = "This will not work";  
}  
  
// This modifies a property of the parameter, which  
// can be seen in the calling code.  
function Update(param)  
{  
    // Modify the property of the object; this will be seen  
    // in the calling code.  
    param.message = "I was changed";  
}  
  
// Create an object, and give it a property.  
var obj = new Object();  
obj.message = "This is the original";  
  
// Call Clobber, and print obj.message. Note that it hasn't changed.  
Clobber(obj);  
window.alert(obj.message); // Still displays "This is the original".  
  
// Call Update, and print obj.message. Note that is has changed.  
Update(obj);  
window.alert(obj.message); // Displays "I was changed".  
```  
  
## <a name="testing-data"></a>Veri Sınama  
 Değere göre sınamayı gerçekleştirirken birbirlerine eşit olup olmadığını görmek için iki farklı öğeyi karşılaştırırsınız. Bu karşılaştırma genellikle tek tek bayt temelinde gerçekleştirilir. Başvuruya göre test ettiğinizde, iki öğenin tek bir özgün öğeye işaretçi olup olmadığını denetlersiniz. Böyle bir durumda karşılaştırmada eşit olurlar; aksi halde, tam olarak aynı değerleri içerseler bile, tek tek bayt temelinde eşit olmazlar.  
  
 Dizeleri başvuruya göre kopyalama ve geçirme bellek kazandırır, fakat bir defa oluşturulduktan sonra dizeleri değiştiremeyeceğiniz için, değere göre karşılaştırmak mümkün hale gelir. Bu, biri diğerinden tamamen ayrı olarak üretilse bile, iki dizenin aynı içeriğe sahip olup olmadığını sınamanızı sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarihler ve saatleri hesaplama (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)