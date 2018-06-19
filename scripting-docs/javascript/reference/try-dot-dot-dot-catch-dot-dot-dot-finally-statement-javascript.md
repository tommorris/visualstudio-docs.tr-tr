---
title: try... catch... finally deyimi (JavaScript) | Microsoft Docs
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
- try_JavaScriptKeyword
- finally_JavaScriptKeyword
- catch_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- try-catch exception handling, finally block
- try-catch exception handling, about try-catch exception handling
- try-catch exception handling, catch block
- try-catch exception handling
ms.assetid: b7a0a54e-dfaa-4e41-bf25-bcaa43e601fb
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b05f15e593aeb7cb921f6237fad30b589cfdfe66
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792047"
---
# <a name="trycatchfinally-statement-javascript"></a>try...catch...finally Deyimi (JavaScript)
Bir kodda oluşturulan hatanın başka bir blok içinde işlenmesini sağlayacak şekilde kod blokları ayarlar. İçinde oluşturulan hataları `try` blok yakalanan içinde `catch` bloğu. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
try {  
    tryStatements  
}  
catch(exception){  
    catchStatements  
}  
finally {  
    finallyStatements  
}  
```  
  
## <a name="parameters"></a>Parametreler  
 `tryStatements`  
 Gerekli. Bir hatanın oluşabileceği deyimler.  
  
 `exception`  
 Gerekli. Herhangi bir değişken adı. Başlangıç değeri `exception` atılmış hata değeri.  
  
 `catchStatements`  
 İsteğe bağlı. İlişkili içinde gerçekleşen hataları işlemek için deyimleri `tryStatements`.  
  
 `finallyStatements`  
 İsteğe bağlı. Tüm hatalar işlendikten sonra koşulsuz olarak yürütülecek deyimler.  
  
## <a name="remarks"></a>Açıklamalar  
 `try...catch...finally` Deyimi bazılarını veya tümünü belirli bir kod bloğu içinde hala kod çalıştırılırken oluşabilir hataları işlemek için bir yol sağlar. İşlenen değil, bir hata oluşursa [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] normal hata iletisi sağlar.  
  
 `try` Blok hataya yol açabilirsiniz kodunu içerir ancak `catch` bloğu bazı veya tüm hataları işleyen kodu içerir. Bir hata oluşması halinde `try` bloğu, program denetim iletilir `catch` bloğu. Değeri `exception` oluştu hata değeri `try` bloğu. Herhangi bir hata oluşursa, kodda `catch` blok hiçbir zaman yürütülür.  
  
 Kullanarak hata sonraki düzeye kadar geçirebilirsiniz `throw` hata yeniden throw deyimi.  
  
 Tüm ifadeler sonra `try` blok yürütülen ve hata işleme tamamlandı `catch` engelleyin, deyimleri `finally` blok yürütüldüğünde, bir hata yürütüldü olup olmadığına bakılmaksızın. Kodda `finally` blok işlenmemiş bir hata oluşmadığı sürece çalıştırmak için garanti (örneğin, bir çalışma zamanı hatası içinde **catch** blok).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek neden olan bir `ReferenceError` oluşturulmasına özel durumu ve hata ve kendi ileti adını görüntüler.  
  
```JavaScript  
try {  
    addalert("bad call");  
}  
catch(e) {  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF);  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
  
// Output:  
Error Message: 'addalert' is undefined  
Error Code: 5009  
Error Name: ReferenceError  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek hataları gibi yürütülmesi yeniden throw gösterilmektedir iç içe geçmiş `try...catch` engeller. Hata oluşur zaman iç içe gelen `try` bloğu için iç içe geçen `catch` yeniden oluşturur blok. İç içe `finally` bloğu dış önce çalışır `catch` bloğu hata işler ve dış sonunda `finally` engelleme çalıştırır.  
  
```JavaScript  
try {  
    document.write("Outer try running...<br/>");  
  
    try {  
        document.write("Nested try running...<br/>");  
        throw new Error(301, "an error");  
    }  
    catch (e) {  
        document.write ("Nested catch caught " + e.message + "<br/>");  
        throw e;  
    }  
    finally {  
        document.write ("Nested finally is running...<br/>");  
    }  
}  
catch (e) {  
    document.write ("Outer catch caught " + e.message + "<br/>");  
}  
finally {  
    document.write ("Outer finally running");  
}  
  
// Output:  
// Outer try running...  
// Nested try running...  
// Nested catch caught error from nested try  
// Nested finally is running...  
// Outer catch caught error from nested try  
// Outer finally running  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
> [!NOTE]
>  Internet Explorer 8 standartları modu ile başlayan **catch** bloğu için gerekli olduğu artık `finally` çalıştırmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [throw deyimi](../../javascript/reference/throw-statement-javascript.md)   
 [Kod delisi olun Yapılandırma Sihirbazı örnek uygulaması](http://code.msdn.microsoft.com/Script-Junkie-Configuration-543ece24)