---
title: "JavaScript Konsolu komutları Visual Studio'da | Microsoft Docs"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript Console commands [UWP apps]
- JavaScript debugging, console [UWP apps]
- debugging JavaScript, console [UWP apps]
caps.latest.revision: "47"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- uwp
- cordova
ms.openlocfilehash: 1f2d6f356d4e886488f4b6558c6cfb92d7b9c974
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="javascript-console-commands-in-visual-studio"></a>Visual Studio'da JavaScript Konsolu komutları
  
 İleti gönderme ve Visual Studio JavaScript konsol penceresinde diğer görevleri gerçekleştirmek için komutlarını kullanabilirsiniz. Bu penceresinin nasıl kullanılacağını gösteren örnekler için bkz: [hızlı başlangıç: JavaScript hata ayıklama](../debugger/quickstart-debug-javascript-using-the-console.md). Bu konu başlığı altındaki bilgiler UWP uygulamalar ve Apache Cordova için Visual Studio Araçları kullanılarak oluşturulan uygulamalar için geçerlidir. Cordova uygulamalarda desteklenen Konsolu komutları hakkında daha fazla bilgi için bkz: [Debug Your App](https://taco.visualstudio.com/en-us/docs/debug-using-visual-studio/). Internet Explorer F12 araçları konsolunu kullanma hakkında daha fazla bilgi için bkz: [bu konuda](http://msdn.microsoft.com/library/ie/dn255006.aspx).  
  
 JavaScript Konsolu penceresi kapatıldığında, Visual Studio'da seçerek hatalarını ayıkladığınız sırada da açabilirsiniz **hata ayıklama** > **Windows** > **JavaScript Konsol**.  
  
> [!NOTE]
>  Pencerenin hata ayıklama oturumu sırasında kullanılabilir durumda değilse, hata ayıklayıcı türü olarak ayarlandığından emin olun **betik** projesi için hata ayıklama özellikleri.  
  
## <a name="console-object-commands"></a>Konsol nesne komutları  
 Bu tablo için söz dizimi görülmektedir `console` nesne komutları JavaScript konsol penceresinde kullanabilir veya konsola kodunuzdan iletileri göndermek için kullanabilirsiniz. Böylece bilgilendirici iletileri ve hata iletileri ayırt etmek istiyorsanız bu nesne forms sayısını sağlar.  
  
 Uzun komutu formu kullanabilirsiniz `window.console.[command]` konsol adlı yerel nesneleriyle olası Karışıklığı önlemek gerekiyorsa.  
  
> [!TIP]
>  Visual Studio'nun daha eski sürümleri tam komut kümesini desteklemez. IntelliSense konsol nesne üzerinde desteklenen komutlar hakkında hızlı bilgi almak için kullanın.  
  
|Komut|Açıklama|Örnek|  
|-------------|-----------------|-------------|  
|`assert(expression, message)`|Bir ileti gönderir `expression` değerlendiren **false**.|`console.assert((x == 1), "assert message: x != 1");`|  
|`clear()`|Komut dosyası hata iletileri de dahil olmak üzere konsol penceresinden iletileri temizler ve ayrıca konsol penceresinde görünür betik temizler. Giriş Konsolu komut isteminde girdiğiniz betik temizlemez.|`console.clear();`|  
|`count(title)`|Sayımı komutunu çağrıldı sayısı konsol penceresine gönderir. Her çağrı sayısı benzersiz isteğe bağlı olarak tanımlanır `title`.<br /><br /> Varolan bir girişi konsol penceresinde tarafından tanımlanan `title` parametre (varsa) ve sayısı komutu tarafından güncelleştirilir. Yeni bir giriş oluşturulmaz.|`console.count();`<br /><br /> `console.count("inner loop");`|  
|`debug(message)`|Gönderir `message` konsol penceresine.<br /><br /> Bu komut için console.log aynıdır.<br /><br /> Komutunu kullanarak geçirilen nesneler bir dize değerine dönüştürülür.|`console.debug("logging message");`|  
|`dir(object)`|Belirtilen nesne konsol penceresine gönderir ve bir nesne Görselleştirici görüntüler. Konsol penceresinde özelliklerini incelemek için görselleştiricisi kullanabilirsiniz.|`console.dir(obj);`|  
|`dirxml(object)`|Belirtilen XML düğümü gönderir `object` konsol penceresine ve bir XML düğümü ağaç olarak görüntüler.|`console.dirxaml(xmlNode);`|  
|`error(message)`|Gönderir `message` konsol penceresine. İleti metni kırmızı ve bir hata simgesiyle başında ' dir.<br /><br /> Komutunu kullanarak geçirilen nesneler bir dize değerine dönüştürülür.|`console.error("error message");`|  
|`group(title)`|Konsol penceresine gönderilen iletiler için bir gruplandırma başlar ve isteğe bağlı gönderen `title` Grup etiket olarak. Gruplar, iç içe konabilir ve ağaç görünümünde konsol penceresinde görünür.<br /><br /> Grup * komutları bileşen modeli kullanımda olduğunda gibi bazı senaryolarda konsol penceresi çıkışını görüntüleyin hale getirebilir.|`console.group("Level 2 Header");` <br /> `console.log("Level 2");` <br /> `console.group();` <br /> `console.log("Level 3");` <br /> `console.warn("More of level 3");` <br /> `console.groupEnd();` <br /> `console.log("Back to level 2");` <br /> `console.groupEnd();` <br /> `console.debug("Back to the outer level");`|  
|`groupCollapsed(title)`|Konsol penceresine gönderilen iletiler için bir gruplandırma başlar ve isteğe bağlı gönderen `title` Grup etiket olarak. Kullanılarak gönderilen grupları `groupCollapsed` bir daraltılmış varsayılan olarak görüntülenir. Gruplar, iç içe konabilir ve ağaç görünümünde konsol penceresinde görünür.|Kullanım aynıdır `group` komutu.<br /><br /> Örneğin bkz `group` komutu.|  
|`groupEnd()`|Geçerli grubu sona erer.<br /><br /> Gereksinimleri:<br /><br /> Visual Studio 2013|Örneğin bkz `group` komutu.|  
|`info(message)`|Gönderir `message` konsol penceresine. İleti bir bilgi simgesi başında vardır.|`console.info("info message");`<br /><br /> Daha fazla örnek için bkz: [console.log çıkış biçimlendirme](#ConsoleLog) bu konuda daha sonra.|  
|`log(message)`|Gönderir `message` konsol penceresine.<br /><br /> Bir nesne geçirirseniz, bu komutun söz konusu nesne konsol penceresine gönderir ve bir nesne Görselleştirici görüntüler. Konsol penceresinde özelliklerini incelemek için görselleştiricisi kullanabilirsiniz.|`console.log("logging message");`|  
|`msIsIndependentlyComposed(element)`|Web uygulamalarında kullanılır. JavaScript kullanarak UWP uygulamalarında desteklenmiyor.|Desteklenmez.|  
|`profile(reportName)`|Web uygulamalarında kullanılır. JavaScript kullanarak UWP uygulamalarında desteklenmiyor.|Desteklenmez.|  
|`profileEnd()`|Web uygulamalarında kullanılır. JavaScript kullanarak UWP uygulamalarında desteklenmiyor.|Desteklenmez.|  
|`select(element)`|Belirtilen HTML seçer `element` içinde [DOM Gezgini](../debugger/quickstart-debug-html-and-css.md).|console.select(element);|  
|`time (name)`|İsteğe bağlı olarak tanımlanan bir süreölçer başlatır `name` parametresi. İle kullanıldığında `console.timeEnd`, hesaplar arasında geçen sürenin `time` ve `timeEnd`ve (milisaniye olarak ölçülür) sonucu konsolunu kullanarak gönderir `name` öneki olarak dize. Uygulama kodunun performansını ölçmek için Araçları'nı etkinleştirmek için kullanılır.|`console.time("app start");  app.start();  console.timeEnd("app start");`|  
|`timeEnd(name)`|İsteğe bağlı olarak tanımlanan bir süreölçer durdurur `name` parametresi. Bkz: `time` konsol komutu.|`console.time("app start"); app.start(); console.timeEnd("app start");`|  
|`trace()`|Yığın izlemesi konsol penceresine gönderir. İzleme tam çağrı yığını dahildir ve dosya adı, satır numarası ve sütun numarası gibi bilgileri içerir.|`console.trace();`|  
|`warn(message)`|Gönderir `message` konsol penceresine başında bir uyarı simgesi.<br /><br /> Komutunu kullanarak geçirilen nesneler bir dize değerine dönüştürülür.|`console.warn("warning message");`|  
  
## <a name="miscellaneous-commands"></a>Çeşitli komutlar  
 Bu komutlar da (koddan kullanılamaz) JavaScript konsol penceresinde kullanılabilir.  
  
|Komut|Açıklama|Örnek|  
|-------------|-----------------|-------------|  
|`$0`, `$1`, `$2`, `$3`, `$4`|Belirtilen öğe konsol penceresine döndürür. `$0`DOM Gezgini'nde seçili öğeyi döndürür `$1` DOM Gezgini ve benzeri, dördüncü daha önce seçilen öğeyi kadar daha önce seçilen öğeyi döndürür.|$3|  
|`$(id)`|Kimliğine göre bir öğeyi döndürür Bu, için kısayol komuttur `document.getElementById(id)`, burada `id` öğesi kimliği temsil eden bir dize|`$("contenthost")`|  
|`$$(selector)`|CSS Seçici söz dizimini kullanarak belirtilen Seçici eşleşen öğeleri bir dizi döndürür. Bu, için kısayol komuttur `document.querySelectorAll()`.|`$$(".itemlist")`|  
|`cd()`<br /><br /> `cd(window)`|İfade değerlendirme bağlamının belirtilen çerçeve penceresi için sayfanın varsayılan en üst düzey penceresinden değiştirmenize olanak tanır. Çağırma `cd()` en üst düzey penceresine bağlam olmadan parametrelerini döndürür.|`cd();`<br /><br /> `cd(myframe);`|  
|`select(element)`|Belirtilen öğe seçer [DOM Gezgini](../debugger/quickstart-debug-html-and-css.md).|`select(document.getElementById("element"));`<br /><br /> `select($("element"));`<br /><br /> `select($1);`|  
|`dir(object)`|Belirtilen nesne için Görselleştirici döndürür. Konsol penceresinde özelliklerini incelemek için görselleştiricisi kullanabilirsiniz.|`dir(obj);`|  
  
## <a name="checking-whether-a-console-command-exists"></a>Bir konsol komutu var olup olmadığı denetleniyor  
 Belirli bir komut bunu kullanmayı denemeden önce mevcut olup olmadığını kontrol edebilirsiniz. Bu örnek varlığını denetler `console.log` komutu. Varsa `console.log` yoksa, kodu çağırır.  
  
```javascript  
if (console && console.log) {  
    console.log("msg");  
}  
  
```  
  
## <a name="examining-objects-in-the-javascript-console-window"></a>JavaScript Konsolu penceresinde, nesneler inceleniyor  
 JavaScript Konsolu penceresi kullandığınızda kapsamında olan herhangi bir nesne ile etkileşim kurabilirsiniz. Konsol penceresinde bir kapsam nesne incelemek için kullanın `console.log` , `console.dir`, ya da kodunuzdan diğer komutlar. Kodunuzda bir kesme noktası ayarlayarak kapsamda iken alternatif olarak, konsol penceresi nesnesinden etkileşim kurabilirsiniz (**kesme noktası** > **kesme noktası Ekle**).  
  
##  <a name="ConsoleLog"></a>Console.log çıktı biçimlendirmesi  
 Birden fazla bağımsız değişken geçirirseniz `console.log`, konsol bağımsız bir dizi olarak kabul eder ve çıktı birleştirme.  
  
```javascript  
var user = new Object();  
user.first = "Fred";  
user.last = "Smith";  
  
console.log(user.first, user.last);  
// Output:  
// Fred Smith  
  
```  
  
 `console.log`Ayrıca, çıktı biçimlendirmek için "printf" değiştirme desenleri destekler. Değiştirme desenleri ilk bağımsız değişkeninde kullanırsanız, ek bağımsız değişkenler kullanıldıkları sırayla belirtilen desenleri değiştirmek için kullanılır.  
  
 Aşağıdaki değiştirme desenleri desteklenir:  
  
-   %s - dize  
     %i - integer  
     %d - tamsayı  
     %f - float  
     %o - nesnesi  
     %b - ikili  
     %x - onaltılık  
     %e - exponent  
  
 Değiştirme desenleri kullanmanın bazı örnekler şunlardır `console.log`:  
  
```javascript  
var user = new Object();  
user.first = "Fred";  
user.last = "Smith";  
user.age = 10.01;  
console.log("Hi, %s %s!", user.first, user.last);  
console.log("%s is %i years old!", user.first, user.age);  
console.log("%s is %f years old!", user.first, user.age);  
  
// Output:  
// Hi, Fred Smith!  
// Fred is 10 years old!  
// Fred is 10.01 years old!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlı Başlangıç: JavaScript hata ayıklama](../debugger/quickstart-debug-javascript-using-the-console.md)   
 [Hızlı Başlangıç: HTML ve CSS hata ayıklama](../debugger/quickstart-debug-html-and-css.md)