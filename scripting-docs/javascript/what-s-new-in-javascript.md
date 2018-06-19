---
title: "&#39; teki JavaScript'deki yenilikler | Microsoft Docs"
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
ms.assetid: 342b68ef-df93-48c4-81de-bdf6b6ce58d9
caps.latest.revision: 33
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 540d10958a7f2d406a6d70a633fc09a2cada8f41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792152"
---
# <a name="what39s-new-in-javascript"></a>&#39; teki JavaScript'deki yenilikler
Bu belge JavaScript içindeki her ikisinde de desteklenen yeni özellikleri listeler [kenar modu](http://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx), [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)]ve Windows Phone mağazası uygulamaları.  
  
 JavaScript öğeleri kenar modunda desteklenir, ancak de kullanım dışı öğrenmek için [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] uygulamaları bkz [sürüm bilgilerini](../javascript/reference/javascript-version-information.md).  
  
> [!IMPORTANT]
>  Nasıl oluşturulacağı hakkında bilgi için [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] ve Visual Studio JavaScript Düzenleyicisi'ni ve diğer özellikler hakkında bilgiler dahil olmak üzere JavaScript kullanarak Windows Phone mağazası uygulamaları görmek [Visual Studio 2013kullanarakgeliştirmeWindowsmağazasıuygulamaları](http://go.microsoft.com/fwlink/p/?LinkID=238263).  
  
## <a name="new-features-in-javascript"></a>JavaScript içindeki yeni özellikleri  
  
|Özellik|Açıklama|  
|-------------|-----------------|  
|Sınıflar|Yeni sözdizimini destekler bildirimi [sınıfları](../javascript/reference/class-statement-javascript.md).|  
|Öneriler|[Öneriler](../javascript/reference/promise-object-javascript.md) daha kolay ve temizleyici zaman uyumsuz kodlama izin verin. Promise Oluşturucular, bunların ile desteklenir `all` ve `race` yardımcı program yöntemleri.|  
|Yineleyiciler|Artık her ayrı bir özellik değeri için yürütülecek deyimleri ile özel yineleme kanca çağırma (diziler, dizi benzeri nesneleri ve yineleyiciler dahil) iterable nesneler üzerinde yineleyebilirsiniz. Daha fazla bilgi için bkz: [yineleyiciler ve oluşturucuları](../javascript/advanced/iterators-and-generators-javascript.md). **Not:** oluşturucuları henüz desteklenmiyor.|  
|Ok işlevleri|Ok işlevi (= >) için toplu değer sözdizimi sağlar `function` bir sözcük özellikleri anahtar sözcüğü `this` bağlama.|  
|Yerleşik nesneler için yeni yöntemler|[Dizi nesnesi](../javascript/reference/array-object-javascript.md), [matematik nesnesi](../javascript/reference/math-object-javascript.md), [sayı nesne](../javascript/reference/number-object-javascript.md), [nesne nesne](../javascript/reference/object-object-javascript.md), ve [dize nesnesi](../javascript/reference/string-object-javascript.md) yerleşik nesneler birçok yeni yardımcı işlevleri ve düzenleme ve veri İnceleme için özellikler içerir.|  
|Nesne değişmez değer geliştirmeleri|Nesneleri şimdi hesaplanan özellikleri, kısa yöntemi tanımları ve toplu değer sözdizimi değeri aynı adlı bir değişkene başlatılmadan özellikleri için destek. Daha fazla bilgi için bkz: [nesneleri oluşturma](../javascript/creating-objects-javascript.md).|  
|Proxy'leri|[Proxy'leri](../javascript/reference/proxy-object-javascript.md) nesneler için özel davranışı etkinleştirin.|  
|REST parametreleri|REST parametreler işlev çağrısı bir dizi ardışık bağımsız değişkenleri açmanızı sağlar. Daha fazla bilgi için bkz: [işlevler](../javascript/functions-javascript.md).|  
|Spread işleci|[Yayılan işleci](../javascript/reference/spread-operator-decrement-dot-dot-dot-javascript.md) (`...`) tek tek bağımsız değişken iterable ifadelere genişletir. Örneğin, `a.b(...array)` yaklaşık aynıdır `a.b.apply(a, array)`.|  
|Simgeleri|[Sembol](../javascript/reference/symbol-object-javascript.md) nesneler girişim varolan nesne özellikleri, istenmeyen bir görünürlük ve diğer eşgüdümlü olmayan eklemeler hiçbir olasılığıyla birlikte var olan nesneleri başka bir kodla eklenecek özellikleri sağlar.|  
|Şablon dizeleri|[Şablon dizeleri](../javascript/advanced/template-strings-javascript.md) değerlendirilir ve dize sabit değeri birleştirilmiş ifadeler için izin dize değişmez değerleri şunlardır.|  
|Unicode geliştirmeleri|Geliştirmeler yapılmıştır Unicode desteği. Örneğin, yeni bir kaçış dizisi biçimi astral kod noktası (dörtten fazla onaltılık basamak ile kod noktaları) destekler. Daha fazla bilgi için bkz: [özel karakterleri](../javascript/advanced/special-characters-javascript.md).|  
|WeakSet|A [WeakSet](../javascript/reference/weakset-object-javascript.md) olan başka herhangi bir yerde başvurulan değillerse toplanacak olacak nesneleri koleksiyonu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript dil başvurusu](../javascript/javascript-language-reference.md)