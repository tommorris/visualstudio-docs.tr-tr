---
title: JavaScript'te Windows çalışma zamanı olayları işleme | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1118fa4e6408698187e7f50ca6f9b61bf596a6e
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234952"
---
# <a name="handling-windows-runtime-events-in-javascript"></a>JavaScript'te Windows çalışma zamanı olayları işleme
C++ veya .NET Framework oldukları gibi Windows çalışma zamanı olayları JavaScript aynı yolla temsil edilmez. Sınıf özelliklerini değildir ancak bunun yerine sınıfına ait geçirilen (dönüştürüldükten) dize tanımlayıcıları olarak temsil edilir `addEventListener` ve `removeEventListener` yöntemleri. Örneğin, bir olay işleyicisi ekleyebilirsiniz [Geolocator.PositionChanged](https://msdn.microsoft.com/library/windows/apps/xaml/windows.devices.geolocation.geolocator.positionchanged.aspx) için "positionchanged" dizesi geçirerek olay `Geolocator.addEventListener` yöntemi:  
  
```JavaScript  
var locator = new Windows.Devices.Geolocation.Geolocator();  
locator.addEventListener(  
    "positionchanged",   
     function (ev) {  
        console.log("Got event");  
    });  
```  
  
 Ayrıca ayarlayabilirsiniz `locator.onpositionchanged` özelliği:  
  
```JavaScript  
locator.onpositionchanged =    
    function (ev) {  
        console.log("Got event");  
    };  
```  
  
 JavaScript'te, Windows çalışma zamanı olay bağımsız değişkenler tek bir olay nesnesi olarak temsil edilir. Aşağıdaki örnekte bir olay işleyicisi yönteminin `ev` parametredir (hedef özelliği) gönderen ve, başka bir olay bağımsız değişken içeren bir nesne. Olay bağımsız değişkenlerinin her olay için belgelenen olanlardır.  
  
```JavaScript  
function (ev) {  
    console.log("Target: " + ev.target);  
    console.log("Position: " +  
        ev.position.latitude + "," +  
        ev.position.longitude);  
};  
  
```  
  
> [!IMPORTANT]
>  Windows çalışma zamanı özellikleri, Internet Explorer'da çalışan uygulamalar kullanılabilir değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript’te Windows Çalışma Zamanını Kullanma](../jswinrt/using-the-windows-runtime-in-javascript.md)