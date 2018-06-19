---
title: Yazılmış diziler (JavaScript) | Microsoft Docs
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
ms.assetid: fa82c562-0ebf-4559-aecc-166e59f7fb64
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5fc3b29a4593e7c627a6e606242229e87fa5be54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789140"
---
# <a name="typed-arrays-javascript"></a>Yazılmış Diziler (JavaScript)
Ağ protokolleri, ikili dosya biçimlerini ve ham grafik arabellekleri gibi kaynaklardan gelen ikili verileri işlemek için yazılmış diziler kullanın. Yazılmış diziler, iyi bilinen bayt düzenleri ile bellek içi ikili verileri yönetmek için de kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösteren bir [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md) yanıt olarak bir [XMLHttpRequest](http://msdn.microsoft.com/library/ie/ms535874\(v=vs.85\).aspx). Farklı yöntemleri kullanarak yanıta bayt işleyebilir [DataView nesnesi](../../javascript/reference/dataview-object.md), ya da uygun yazılan diziye bayt kopyalayarak.  
  
> [!TIP]
>  Farklı yanıt türleri ile kullanma hakkında daha fazla bilgi için bir `XmlHttpRequest`, bkz: [XMLHttpRequest.responseType](http://msdn.microsoft.com/en-us/8d7738d1-4bfd-4cf1-8015-174def089556), [XMLHttpRequest geliştirmeleri](http://msdn.microsoft.com/en-us/be09137c-6546-441b-b953-dcbf72b77069), ve [farklı indirme İçerik (Windows mağazası uygulamaları) türlerini](http://msdn.microsoft.com/en-us/c0006bbd-17f9-4c6a-af81-2acaf109111d).  
  
```JavaScript  
...  
<div id="xhrDiv"></div>  
...  
var name = "http://www.microsoft.com";  
var xhrDiv = document.getElementById("xhrDiv");  
  
var req = new XMLHttpRequest();  
req.open("GET", name, true);  
req.responseType = "arraybuffer";  
req.onreadystatechange = function () {  
if (req.readyState == req.DONE) {  
    var arrayResponse = req.response;  
    var dataView = new DataView(arrayResponse);  
    var ints = new Uint32Array(dataView.byteLength / 4);  
  
    xhrDiv.style.backgroundColor = "#00FF00";  
    xhrDiv.innerText = "Array is " + ints.length + "uints long";  
    }  
}  
req.send();  
```  
  
## <a name="arraybuffer"></a>ArrayBuffer  
 Bir [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md) bir arabellek farklı yazılmış diziler verilerini depolamak için kullanılan ham verileri temsil eder. Okuma veya yazma bir `ArrayBuffer`, ancak belirlenmiş bir dizi geçirin veya [DataView nesnesi](../../javascript/reference/dataview-object.md) ham arabellek yorumlayamadı. Kullanabileceğiniz bir `ArrayBuffer` veri (veya karma veri türleri) herhangi bir tür depolamak için.  
  
## <a name="dataview"></a>DataView  
 Kullanabileceğiniz bir [DataView nesnesi](../../javascript/reference/dataview-object.md) okuyun ve herhangi bir konuma farklı türde ikili verileri yazmak için `ArrayBuffer`.  
  
## <a name="typed-arrays"></a>Yazılmış Diziler  
 Yazılı dizi türleri görünümlerini temsil eden bir [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md) , kullanılabilir dizine ve yönetilebilir. Tüm dizi sabit uzunluk türleridir.  
  
||||  
|-|-|-|  
|Ad|Boyutu (bayt)|Açıklama|  
|[Int8array nesnesi](../../javascript/reference/int8array-object.md)|1.|Sekiz bit iki kişinin imzalı tamsayı tamamlar|  
|[Uint8Array nesnesi](../../javascript/reference/uint8array-object.md)|1.|Sekiz bit işaretsiz tamsayıyı|  
|[Int16array nesnesi](../../javascript/reference/int16array-object.md)|2|On altı bit iki kişinin imzalı tamsayı tamamlar|  
|[Uint16Array nesnesi](../../javascript/reference/uint16array-object.md)|2|On altı bit işaretsiz tamsayıyı|  
|[Int32array nesnesi](../../javascript/reference/int32array-object.md)|4|Otuz iki bit iki kişinin imzalı tamsayı tamamlar|  
|[Uint32Array nesnesi](../../javascript/reference/uint32array-object.md)|4|Otuz iki bit işaretsiz tamsayıyı|  
|[Float32Array nesnesi](../../javascript/reference/float32array-object.md)|4|Otuz iki bit IEEE kayan nokta|  
|[Float64Array nesnesi](../../javascript/reference/float64array-object.md)|8|Kayan nokta sayısı altmış dört bit IEEE|