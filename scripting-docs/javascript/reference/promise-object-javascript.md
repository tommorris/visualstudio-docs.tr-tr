---
title: Promise nesnesi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 358ad98b-f7fa-448c-9ee0-ef1e2a45e9c6
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 61e5611dd0d455c7e7b704777cc2341ca43a2404
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="promise-object-javascript"></a>Promise Nesnesi (JavaScript)
Henüz hesaplanan bir değer yapılacak işleri zamanlamak için bir mekanizma sağlar. Zaman uyumsuz API'leri ile etkileşim yönetmek için bir Özet değil.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
var promise = new Promise(function(resolve, reject) { ... });  
```  
  
#### <a name="parameters"></a>Parametreler  
 `promise`  
 Gerekli. Promise atandığı değişken adı.  
  
 `resolve`  
 Gerekli. Promise başarıyla tamamlandığını göstermek için çalışan bir işlev.  
  
 `reject`  
 İsteğe bağlı. Promise hatasıyla reddedildi belirtmek için çalışan bir işlev.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir Promise ya da bir değerle doldurulmalıdır veya bir sebeple reddedilmesi gerekir. `then` Promise nesnesinin yöntemi promise tamamlandı ya da reddedilen hangisi önce gerçekleşirse olmadığında çalıştırılabilir. Promise başarıyla tamamlanırsa yerine getirme işleyici işlevinin `then` yöntemi çalışır. Promise reddedilirse, hata işleyici işlevinin `then` yöntemi (veya `catch` yöntemi) çalıştırır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir işlevi çağırmak nasıl gösterir (`timeout`) bir promise döndürür. Karşılama işleyicisini `then` yöntemi çalıştıktan sonra 5000ms zaman aşımı süresi sona erene.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(resolve, duration);  
    });  
}  
  
// Note: This code uses arrow function syntax  
var m = timeout(5000).then(() => {  
    console.log("done!");  
})  
  
// Output (after 5 seconds):  
// done!  
```  
  
## <a name="example"></a>Örnek  
 Çağrı zincir `then` aşağıdaki kodda gösterildiği gibi yöntemi. Her tamamlama işleyicisi kendisini zincirleme desteklemek için bir promise döndürmelidir. Bu kod, çağıran aynı `timeout` işlevi, zaman aşımı ilk çağrıda 1000 ms sonra döndürür. İlk tamamlama işleyicisi çağrılarını `timeout` tekrar ve sonra 2000ms bu promise döndürür. Kendi tamamlama işleyicisi sonra bir hata oluşturur. Hata işleyicisi çağrılarını `Promise.all`, zaman aşımı hem çağrıları yalnızca tamamlandı veya reddedilen döndürür.  
  
```JavaScript  
var p = timeout(1000).then(() => {  
    return timeout(2000);  
}).then(() => {  
    throw new Error("error");  
}).catch(err => {  
    return Promise.all([timeout(100), timeout(200)]);  
})  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="functions"></a>İşlevler  
 Aşağıdaki tabloda, işlevleri açıklanmaktadır `Promise` nesnesi.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[Promise.all işlevi](../../javascript/reference/promise-all-function-promise.md)|İki veya daha fazla öneriler birleştirir ve yalnızca belirtilen tüm öneriler tamamladıktan veya reddedilen döndürür.|  
|[Promise.race işlevi](../../javascript/reference/promise-race-function-promise.md)|Gidermek veya reddetme yeni bir promise gidermek veya geçirilen bağımsız değişkenleri arasında reddetmek için ilk promise aynı sonucu değeri oluşturur.|  
|[Promise.Reject işlevi](../../javascript/reference/promise-reject-function-promise.md)|Yeni bir reddedilen promise geçirilen bağımsız değişken sonuç eşit oluşturur.|  
|[Promise.Resolve işlevi](../../javascript/reference/promise-resolve-function-promise.md)|Yeni bir çözümlenmiş promise bağımsız değişken sonuç eşit oluşturur.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini açıklar `Promise` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[catch yöntemi](../../javascript/reference/catch-method-promise.md)|Bir promise reddetme üzerinde yapılacak işleri belirtmenize olanak tanır.|  
|[Then yöntemi](../../javascript/reference/then-method-promise.md)|Bir promise yerine getirme üzerinde yapılacak işleri belirtmenize olanak tanır.|