---
title: ArrayBuffer nesnesi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 9fda1261-f450-493b-b3db-ecfa9ca93cd7
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c253d63d12a4a5e71d1661aae560b74debecdd62
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789239"
---
# <a name="arraybuffer-object"></a>ArrayBuffer Nesnesi
Ham arabellek farklı yazılmış diziler verilerini depolamak için kullanılan ikili veri temsil eder. `ArrayBuffers`Okuma veya doğrudan yazma ancak belirlenmiş bir dizi geçirilebilir veya [DataView nesnesi](../../javascript/reference/dataview-object.md) gerektiği gibi ham arabellek yorumlamak için.  
  
 Yazılmış diziler hakkında daha fazla bilgi için bkz: [yazılan diziler](../../javascript/advanced/typed-arrays-javascript.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
  
arrayBuffer = new ArrayBuffer(length);  
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayBuffer`  
 Gerekli. Değişken adına `ArrayBuffer` nesne atanır.  
  
 `length`  
 Arabellek uzunluğu. ArrayBuffer içeriğini 0 olarak başlatılır. Eğer istenen byte sayısı ayrılamazsa bir özel durum harekete geçirilir.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `ArrayBuffer` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[byteLength özelliği](../../javascript/reference/bytelength-property-arraybuffer.md)|Salt okunur. ArrayBuffer (bayt cinsinden) uzunluğu.|  
  
## <a name="functions"></a>İşlevler  
 Aşağıdaki tabloda işlevlerini listeler `ArrayBuffer` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[ArrayBuffer.isView işlevi](../../javascript/reference/arraybuffer-isview-function-arraybuffer.md)|Bir nesne arabellek bir görünümünü sunan olup olmadığını belirler.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `ArrayBuffer` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[slice yöntemi](../../javascript/reference/slice-method-arraybuffer.md)|Bir bölümünü döndürür bir `ArrayBuffer`.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir ArrayBuffer nesnesi öğesinden edinilen ikili verileri işlemek için nasıl kullanılacağını gösterir bir [XMLHttpRequest](http://msdn.microsoft.com/library/ie/ms535874\(v=vs.85\).aspx). Kullanabileceğiniz bir [DataView nesnesi](../../javascript/reference/dataview-object.md) tek tek değerleri alabilirsiniz.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Int32Array(buffer.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanma hakkında daha fazla bilgi için `XmlHttpRequest`, bkz: [XMLHttpRequest geliştirmeleri](http://msdn.microsoft.com/en-us/be09137c-6546-441b-b953-dcbf72b77069).  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]