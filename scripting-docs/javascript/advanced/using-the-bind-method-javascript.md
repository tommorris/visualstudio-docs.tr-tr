---
title: "Bind yöntemi (JavaScript) kullanarak | Microsoft Docs"
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
- bind method [JavaScript]
- this object [JavaScript]
ms.assetid: f608f95b-3b9d-437a-a67a-5a4ef8f6c07f
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c49f6e8c5606845f41cc947029ac9405f97665f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="using-the-bind-method-javascript"></a>Bağlama yöntemini kullanma (JavaScript)
JavaScript `bind` yöntemi birkaç kullanımı vardır. Genellikle, başka bir bağlamda çalışan bir işlev için çalıştırma içeriğini korumak için kullanılır. `bind`özgün işlevi olarak aynı gövdesine sahip yeni bir işlev oluşturur. Geçirilen ilk bağımsız değişken `bind` değerini belirtir. `this` bağlı işlev anahtar sözcük. Ayrıca ek, isteğe bağlı bağımsız değişkenler geçirebilirsiniz `bind`. Ek kullanım örnekleri için bkz: [bind yöntemi (işlev)](../../javascript/reference/bind-method-function-javascript.md). Kullanarak bir örnek için `bind` kısmen işlevleri uygulamak için bkz: [zaman uyumsuz programlama desenleri ve Hilo JavaScript (Windows mağazası) ipuçları](http://msdn.microsoft.com/library/windows/apps/jj649740.aspx).  
  
## <a name="preserving-the-execution-context-using-bind"></a>Bind kullanarak çalıştırma bağlamını koruma  
 `bind` İşlevi olay dinleyicileri eklerken sık kullanılır. Aşağıdaki kod örneğinde, `bind` geçerli nesne bağlamında korumak için kullanılır (`DataObject`). Veri nesnesi geçirilir `bind` kullanarak `this` veri nesne özellikleri ve işlevleri erişim sağlayan anahtar sözcüğü, olay işleyicisi (`dataReadyHandler`) çalıştırır. Göstermek için nasıl `bind` çalışır, bu kod, özel bir olay oluşturur.  
  
```JavaScript  
var data;  
  
var dataReadyEvent = document.createEvent("Event");  
dataReadyEvent.initEvent("dataReady", true, false);  
  
function DataObject() {  
    this.name = "Data Object";  
    this.data = function () {  
        return data;  
    }  
    this.onDataCompleted = dataReadyHandler;  
    document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
    // To see the result of not using bind, comment out the preceding line,   
    // and uncomment the following line of code.  
    // document.addEventListener('dataReady', this.onDataCompleted);  
}  
function dataReadyHandler() {  
    if (console && console.log) {  
        console.log("Data object property value: " + this.name);  
        console.log("Data object property value: " + this.data());  
    }  
}  
  
setTimeout(function () {  
    data = [0, 1, 2, 3];  
    document.dispatchEvent(dataReadyEvent);  
    }, 5000);  
}  
  
var dataObj = new DataObject();  
  
// Output:  
// Data Object  
// 0,1,2,3  
  
```  
  
 Kullanır kod satırını açıklama varsa `bind`, çağıran kodu satırı açıklamadan kaldırmasına `addEventListener` olmadan `bind`ve kod yeniden `dataReadyHandler` işlevi başarısız olur. Örneğin, `dataReadyHander`, `this.name` tanımlanmamış, olacaktır ve `this.data()` çünkü bir hatayla sonuçlanır `this` nesne artık veri nesnesine başvuruyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [bind yöntemi (işlev)](../../javascript/reference/bind-method-function-javascript.md)