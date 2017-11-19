---
title: Int8array nesnesi | Microsoft Docs
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
ms.assetid: 0e3bdbc5-8d85-4c0d-b399-693b01674803
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7e3f85a505f41f2909330e938f4978433fc823f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="int8array-object"></a>Int8Array Nesnesi
Türü belirlenmiş 8 bit tamsayı değerleri dizisi. İçerikler 0 olarak başlatılır. Eğer istenen byte sayısı ayrılamazsa bir özel durum harekete geçirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int8Array = new Int8Array( length );  
intArray = new Int8Array( array );  
intArray = new Int8Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametreler  
 `int8Array`  
 Gerekli. Değişken adına `Int8Array` nesne atanır.  
  
 `length`  
 Dizinin içindeki öğelerin sayısını belirtir.  
  
 `array`  
 Bu dizinin içinde yer alan dizi (veya türü belirtilmiş dizi). İçerik, her öğe Int8 türüne dönüştürülerek, belirtilen veya yazılan dizinin içerikleri için başlatılır.  
  
 `buffer`  
 Int8Array tarafından temsil edilen ArrayBuffer.  
  
 `byteOffset`  
 İsteğe bağlı. Int8Array'in başlatılması gereken arabelleğin başlangıçtan itibaren bayt uzaklığını belirtir.  
  
 `length`  
 Dizideki öğelerin sayısı  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki tabloda sabitleri `Int8Array`nesnesi.  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT sabiti](../../javascript/reference/bytes-per-element-constant-int8array.md)|Dizideki her öğenin bayt cinsinden boyutu.|  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda sabitleri `Int8Array`nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[buffer özelliği](../../javascript/reference/buffer-property-int8array.md)|Salt okunur. Bu dizi tarafından başvurulan ArrayBuffer nesnesini alır.|  
|[byteLength özelliği](../../javascript/reference/bytelength-property-int8array.md)|Salt okunur. Bu dizinin, oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzunluğu.|  
|[byteOffset özelliği](../../javascript/reference/byteoffset-property-int8array.md)|Salt okunur. Bu dizinin oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzaklığı.|  
|[length özelliği](../../javascript/reference/length-property-int8array.md)|Dizinin uzunluğu.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Int8Array`nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[set yöntemi (ınt8array)](../../javascript/reference/set-method-int8array.md)|Bir değer ya da değerler dizisi ayarlar.|  
|[subarray yöntemi (ınt8array)](../../javascript/reference/subarray-method-int8array.md)|Bu dizinin ArrayBuffer deposunun yeni bir Int8Array görünümünü alır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir Int8Array nesnesinin bir XmlHttpRequest nesnesinden alınan ikili veriyi işlemek için nasıl kullanılacağını gösterir:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Int8Array(buffer.byteLength);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt8(i);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]