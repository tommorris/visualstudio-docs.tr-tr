---
title: Olay dinleyicilerini yönetme | Microsoft Docs
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
ms.assetid: 87717f5d-b0c6-4c8d-a293-476002b7bfcf
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a97c579716b9964b8dfb93db419e9a70160d33a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788888"
---
# <a name="managing-event-listeners"></a>Olay dinleyicilerini yönetme
DOM öğesi ya da nesne yaşam süresi, ilişkili olay dinleyicisi ömrü farklı olması durumunda kullanmanız gerekebilir [removeEventListener](http://msdn.microsoft.com/library/ie/ff975250\(v=vs.85\).aspx)bellek önlemek için yöntemi sızdırıyor.  
  
## <a name="event-listeners-and-object-scope"></a>Olay dinleyicileri ve nesne kapsamı  
 Aşağıdaki kod örneğinde bir bellek sonuçlanabilir kod gösterir sızıntısı oluyordu `dataObjFactory()` işlevi çağrılır. Bu kodda olay dinleyicisi her saat yeni bir veri nesnesi oluşturulan bir veri nesnesi için kayıtlı. Geçerli veri nesnesi içinde kullanılabilir hale getirmek `dataReady()` olay işleyicisi [bind yöntemi (işlev)](../../javascript/reference/bind-method-function-javascript.md) kullanılan `addEventListener`.  
  
```JavaScript  
 var data;  
 var dataObj;  
  
 var dataReadyEvent = document.createEvent("Event");  
 dataReadyEvent.initEvent("dataReady", true, false);  
  
 function DataObject() {  
  
     this.name = "Data Object";  
     this.data = function () {  
         return data;  
     }  
     this.onDataCompleted = dataReady;  
     // this.handlerRef = this.onDataCompleted.bind(this);  
  
     // document.addEventListener('dataReady', this.handlerRef);  
     document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
 }  
  
 // Runs when the data is available.  
 function dataReady() {  
     if (console && console.log) {  
         console.log("object value: " + this.name);  
         console.log("object value: " + this.data());  
     }  
 }  
  
setTimeout(function () {  
    // Generate data after a timeout period.  
    data = [0, 1, 2, 3];  
    document.dispatchEvent(dataReadyEvent);  
}, 10000);  
  
function dataObjFactory() {  
     for (var x = 0; x < 100; x++) {  
         if (dataObj) {  
             // The following line of code has no effect.  
             document.removeEventListener('dataReady', dataObj.onDataCompleted);  
             dataObj = null;  
         }  
         dataObj = new DataObject();  
     }  
 }  
  
 dataObjFactory();  
```  
  
 Her veri nesnesi için dinleyici kayıtlı `document` veri nesneleri daha farklı bir ömrü nesnesi. Her veri nesnesi için kayıtlı olay dinleyicisi çöp sürece olarak toplanan olmasını önleyen `document` nesne kapsam içinde kalır. (Bazı modern JavaScript tasarım modeli web uygulamasının etkin kalma süresi kapsamında belge nesnesi kalacak.) Bir bellek sızıntısı önlemek için `removeEventListener` olarak adlandırılır `dataObjFactory` işlevi. Ancak, bu kodu için başarısız `removeEventListener` tarafından döndürülen olay işleyicisi ilişkili sürümünde çağrılmadı `bind`işlevi.  
  
 Bu kod düzeltin ve veri nesneleri çöp toplama için kullanılabilir hale getirmek için önce bu kodda gösterildiği gibi olay işleyicisinin ilişkili sürümüne başvuru depolamak ve gerekir saklı referansı geçirmek `addEventListener`. Düzeltilmiş kodunu işte `DataObject`:  
  
```JavaScript  
function DataObject() {  
  
    this.name = "Data Object";  
    this.data = function () {  
        return data;  
    }  
    this.onDataCompleted = dataReady;  
    this.handlerRef = this.onDataCompleted.bind(this);  
  
    document.addEventListener('dataReady', this.handlerRef);  
    // document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
}  
  
```  
  
 Son olarak, çağırmanız gerekir `removeEventListener` saklı başvurusundaki (`handlerRef`) ilişkili işlevinin. Düzeltilmiş kodunu işte `dataObjFactory`:  
  
```JavaScript  
function dataObjFactory() {  
     for (var x = 0; x < 100; x++) {  
         if (dataObj) {  
             document.removeEventListener('dataReady', dataObj.handlerRef);  
         }  
         dataObj = new DataObject();  
     }  
 }  
  
```  
  
 Şimdi çağrısına `removeEventListener` çalışır ve gereksiz veri nesneleri çöp bile sırasında toplanan olabilir `document` nesne kapsam içinde kalır.