---
title: "GetObject işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- GetObject
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetObject function
ms.assetid: 62efcdbc-8b86-491d-9000-ef38aa9942a9
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d8bad127a0f260395a1ec19f44ff2d495006024
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getobject-function-javascript"></a>GetObject İşlevi (JavaScript)
Bir dosyadan bir Otomasyon nesnesi için bir başvuru döndürür.  
  
> [!NOTE]
>  Bu işlev, Internet Explorer 9 (standartları modu) veya sonraki bir sürümde desteklenmiyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
GetObject([pathname] [, class])  
```  
  
## <a name="parameters"></a>Parametreler  
 `pathname`  
 İsteğe bağlı. Tam yol ve almak için nesneyi içeren dosyanın adı. Varsa `pathname` atlanırsa, `class` gereklidir.  
  
 `class`  
 İsteğe bağlı. Nesne sınıfı.  
  
 `class` Bağımsız değişkeni sözdizimini kullanan `appname.objectype` ve bu bölümden oluşur:  
  
 `appname`  
 Gerekli. Nesne sağlama uygulamanın adı.  
  
 `objectype`  
 Gerekli. Türü veya nesne sınıfı oluşturmak için.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetObject` İşlevi desteklenmez [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)] veya sonraki bir sürümü.  
  
 Kullanım `GetObject` bir dosyadan bir Otomasyon nesnesi erişmek için işlevi. Ata tarafından döndürülen nesne `GetObject` nesne değişkeni için. Örneğin:  
  
```JavaScript  
var CADObject;  
CADObject = GetObject("C:\\CAD\\SCHEMA.CAD");  
```  
  
 Bu kod, ne zaman yürütülür, belirtilen ile ilişkili uygulamayı `pathname` başlatıldığında, ve belirtilen dosya nesnesinde etkinleştirilir. Varsa `pathname` sıfır uzunlukta bir dize (""), `GetObject` belirtilen türe ait yeni bir nesne örneği döndürür. Varsa `pathname` bağımsız değişken atlanırsa, `GetObject` belirtilen türdeki şu anda etkin bir nesne döndürür. Belirtilen türde bir nesne varsa, bir hata oluşur.  
  
 Bazı uygulamalar, dosyanın bir kısmını etkinleştirmek olanak tanır. Bunu yapmak için dosya adının sonuna bir ünlem işareti (!) ekleyin ve etkinleştirmek istediğiniz dosyanın kısmını tanımlayan bir dize ile izleyin. Bu dize oluşturma hakkında daha fazla bilgi için nesneyi oluşturan uygulama belgelerine bakın.  
  
 Örneğin, bir çizim uygulamasında bir dosyada depolanan bir çizim için birden çok katman olabilir. Bir katman adında bir çizim içinde etkinleştirmek için aşağıdaki kodu kullanabilirsiniz `SCHEMA.CAD`:  
  
```JavaScript  
var LayerObject = GetObject("C:\\CAD\\SCHEMA.CAD!Layer3");  
```  
  
 Nesnenin sınıfı belirtmezseniz, Otomasyon başlatmak için hangi uygulama ve etkinleştirmek için hangi nesne, sağladığınız dosya adına göre belirler. Bazı dosyalar ancak, birden fazla nesne sınıfının destekleyebilir. Örneğin, bir çizim üç farklı türde nesne destekleyebilir: uygulama nesnesi, bir çizim nesnesi ve tümü aynı dosyasının bir parçası olan bir araç çubuğu nesnesi. Etkinleştirmek istediğiniz bir dosyadaki hangi nesne belirtmek için isteğe bağlı kullanın `class` bağımsız değişkeni. Örneğin:  
  
```JavaScript  
var MyObject;  
MyObject = GetObject("C:\\DRAWINGS\\SAMPLE.DRW", "FIGMENT.DRAWING");  
```  
  
 Önceki örnekte `FIGMENT` çizim uygulama adıdır ve `DRAWING` desteklediği nesne türlerinden biridir. Bir nesne etkinleştirildikten sonra tanımladığınız nesne değişkeni kullanarak kod içinde başvuru. Önceki örnekte, özellikleri ve yöntemleri nesne değişkeni kullanarak yeni nesnenin erişim `MyObject`. Örneğin:  
  
```JavaScript  
MyObject.Line(9, 90);  
MyObject.InsertText(9, 100, "Hello, world.");  
MyObject.SaveAs("C:\\DRAWINGS\\SAMPLE.DRW");  
```  
  
> [!NOTE]
>  Kullanım `GetObject` işlev geçerli bir nesne örneği yok ya da sahip nesne oluşturmak istiyorsanız, bir dosya zaten yüklü. Geçerli örneği yok ve kullanmaya nesne istemiyorsanız, bir dosyayı yükledi, kullanın `ActiveXObject` nesnesi.  
  
 Bir nesne kendisine Tek Örnekli nesnesi olarak kaydedildiyse, yalnızca bir nesne örneği, nasıl olsun birçok kez oluşturulur `ActiveXObject` yürütülür. Tek Örnekli nesnesiyle `GetObject` her zaman sıfır uzunlukta bir dize ile çağrıldığında aynı örneğini döndürür ("") sözdizimi ve onu bir hataya neden olur, `pathname` bağımsız değişkeni atlanmış.  
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları ve Internet Explorer 8 standartları. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveXObject nesnesi](../../javascript/reference/activexobject-object-javascript.md)