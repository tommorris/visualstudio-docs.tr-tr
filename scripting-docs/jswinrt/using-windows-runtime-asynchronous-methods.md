---
title: "Windows çalışma zamanı zaman uyumsuz yöntemler kullanma | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime asynchronous methods
ms.assetid: 70756833-44f7-4383-827f-2ac781558082
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 215a04a2f3f875743a7fbf910a3a565cf34fb558
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="using-windows-runtime-asynchronous-methods"></a>Windows çalışma zamanı zaman uyumsuz yöntemler kullanma
Çok sayıda Windows çalışma zamanı yöntemleri, özellikle tamamlanması uzun zaman alabilir yöntemleri zaman uyumsuz. Bu yöntemler bir zaman uyumsuz eylemi veya işlemi genellikle döndürür (örneğin, `Windows.Foundation.IAsyncAction`, `Windows.Foundation.IAsyncOperation`, `Windows.Foundation.IAsyncActionWithProgress`, veya `Windows.Foundation.IAsyncOperationWithProgress`). Bu yöntemler JavaScript tarafından temsil edilen [öneriler/CommonJS/A](http://go.microsoft.com/fwlink/p/?LinkId=244434) düzeni. Sahip Promise nesnesi başka bir deyişle, döndürmeleri bir [sonra](https://msdn.microsoft.com/en-us/library/windows/apps/br229728.aspx) işlevi için sağlamanız gerekir, bir `completed` işlemi başarılı olursa, sonuç işleyen işlevi. Bir hata işleyici sağlamak üzere istemiyorsanız, kullanması gereken [Bitti](https://msdn.microsoft.com/en-us/library/windows/apps/hh701079.aspx) yerine işlev `then` işlevi.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı özellikleri, Internet Explorer'da çalışan uygulamalar kullanılabilir değil.  
  
## <a name="examples-of-asynchronous-methods"></a>Zaman uyumsuz yöntemleri örnekleri  
 Aşağıdaki örnekte, `then` işlev tamamlanmış değerini temsil eden bir parametre alır `createResourceAsync` yöntemi.  
  
```JavaScript  
client.createResourceAsync(uri, description, item)  
    // Success.  
    .then(function(newItem) {   
        console.log("New item is: " + newItem.id);  
            });  
```  
  
 Bu durumda, `createResourceAsync` yöntemi başarısız oldu, hata durumunda bir promise verir, ancak bir özel durum değil. Kullanarak bir hata işleyebilir `then` gibi işlev.  
  
```JavaScript  
client.createResourceAsync(uri, description, item)  
    // Success.  
    .then(function(newItem) {   
              console.log("New item is: " + newItem.id);  
          }  
          function(err) {  
              console.log("Got error: " + err.message);  
          });  
```  
  
 Hata açıkça işlemek istemiyorsanız, ancak bir özel durum istediğiniz, kullanabileceğiniz `done` yerine işlev.  
  
```JavaScript  
client.createResourceAsync(uri, description, item)  
    // Success.  
      .done(function(newItem) {   
               console.log("New item is: " + newItem.id);  
            });  
```  
  
 Ayrıca, üçüncü işlevini kullanarak tamamlama yapılan ilerlemeyi görüntüleyebilirsiniz.  
  
```JavaScript  
client.createResourceAsync(uri, description, item)  
    // Success.  
      .then(function(newItem) {   
               console.log("New item is: " + newItem.id);  
            },  
    // Error.  
            function(error) {   
               alert("Failed to create a resource.");  
            },  
    // Progress.  
            function(progress, resultSoFar) {   
               setProgressBar(progress);  
            });  
```  
  
 Zaman uyumsuz programlama hakkında daha fazla bilgi için bkz: [JavaScript zaman uyumsuz programlama](https://msdn.microsoft.com/en-us/library/windows/apps/hh700330.aspx).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı JavaScript kullanma](../jswinrt/using-the-windows-runtime-in-javascript.md)