---
title: Betiklerinizin (JavaScript) sorunlarını giderme | Microsoft Docs
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
- automative type conversion
- troubleshooting scripts
ms.assetid: 0e0545d9-44e5-4179-befc-99a882c5c672
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e0193e6dc0996d5e2d0d3df7103c7705d29477
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789065"
---
# <a name="troubleshooting-your-scripts-javascript"></a>Betiklerinizin Sorunlarını Giderme (JavaScript)
Beklenmeyen durumları sahip herhangi bir programlama dili yerlerde vardır. Örneğin, `null` değeri [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] aynı şekilde davranır değil `Null` C veya C++ dillerde değeri.  
  
 Bazı yazarken içine çalışabilir sorun alanlarını [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyaları.  
  
## <a name="syntax-errors"></a>Sözdizimi hataları  
 Komut dosyaları yazdığınızda ayrıntı dikkat etmek önemlidir. Örneğin, dizeleri tırnak işaretleri içine alınmalıdır.  
  
## <a name="order-of-script-interpretation"></a>Komut dosyası yorumlama sırası  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]Yorumu parçası olduğundan, Web tarayıcınızın HTML işlem ayrıştırma. Bir komut dosyası içinde yerleştirirseniz \<HEAD > etiketi bir belgede herhangi bir kısmını önce yorumlanır \<gövde > etiketi. Oluşturulan nesneniz varsa \<gövde > etiketi, mevcut zaman \<HEAD > Ayrıştırılmakta olan ve komut dosyası tarafından değiştirilemiyor.  
  
> [!NOTE]
>  Bu davranış, Internet Explorer'a özeldir. (Diğer konaklarla olduğu gibi) ASP ve WSH farklı yürütme modelleri vardır.  
  
## <a name="automatic-type-coercion"></a>Otomatik türü zorlama  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]bir geniş yazılmış otomatik zorlama ile dilidir. Farklı türlerine sahip değeri eşit değilse olsa da, aşağıdaki örnekte ifadeler için değerlendirin **doğru**.  
  
```JavaScript  
"100" == 100;  
false == 0;  
```  
  
 Türü ve değeri aynı olduğunu denetlemek için katı eşitlik işleci (=) kullanın. Aşağıdaki iki false olarak değerlendirin:  
  
```JavaScript  
"100" === 100;  
false === 0;  
```  
  
## <a name="operator-precedence"></a>İşleç Önceliği  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md) bir işlem bir ifade değerlendirme sırasında zaman gerçekleştirilen belirler. Aşağıdaki örnekte çıkarma deyimde ilk görünse bile çarpma çıkarma önce gerçekleştirilir.  
  
```JavaScript  
theRadius = aPerimeterPoint - theCenterpoint * theCorrectionFactor;  
```  
  
## <a name="using-forin-loops-with-objects"></a>Kullanarak for... nesnelerle döngüler içinde  
 Sahip bir nesne özelliklerini üzerinden yineleme ne zaman bir [for... içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) döngü, tahmin etmek veya değiştiremezsiniz nesnesinin alanlarını döngü sayacı değişkene atanır sırayı denetleyebilirsiniz. Ayrıca, sipariş farklı dil uygulamalarında farklı olabilir.  
  
## <a name="with-keyword"></a>with anahtar sözcüğü  
 [İle](../../javascript/reference/with-statement-javascript.md) açıklamadır zaten belirtilen bir nesne var, ancak nesne için özellikler eklemek için kullanılamaz özelliklere erişmek için uygun. Yeni özellikleri bir nesne oluşturmak için özellikle nesneye başvurmalıdır.  
  
## <a name="this-keyword"></a>Bu anahtar sözcüğü  
 Hizmetini kullanıyor olsanız da `this` anahtar sözcüğü nesnesine başvurmak için bir nesne tanımı içinde kullanamaz `this` veya şu anda yürütülen başvurmak için benzer anahtar sözcükler, bu işlev bir nesne tanımı olmadığında işlev. İşlevi bir nesne bir yöntem olarak atanması varsa kullanabileceğiniz `this` anahtar sözcüğü nesneye başvurmak için işlev içinde.  
  
## <a name="writing-a-script-that-writes-a-script-in-internet-explorer"></a>Internet Explorer'da bir betik Yazar bir komut dosyası yazma  
 \< /SCRIPT > etiketi geçerli komut yorumlayıcı karşılaşırsa sonlandırır. Görüntülenecek "\</SCRIPT >" kendisi, bu en az iki dize olarak, örneğin, yeniden "\</SCR" ve "IPT >", hangi, ardından birlikte Yazar çıkışı deyimi içinde bir arada kullanabilirsiniz.  
  
## <a name="implicit-window-references-in-internet-explorer"></a>Internet Explorer'da örtük penceresi başvuruları  
 Aynı anda birden fazla penceresi açık olabilir çünkü her türlü örtük penceresi referans geçerli pencereyi işaret eder. Diğer windows için açık bir başvuru kullanmanız gerekir.