---
title: Uint32Array nesnesi | Microsoft Docs
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
ms.assetid: c4bf5409-2d4b-4660-9f4b-a45d7a02b47e
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 05f185e02ac117491d067ddca6605197d126620e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791981"
---
# <a name="uint32array-object"></a>Uint32Array Nesnesi
32-bit işaretsiz tamsayı değerleri belirlenmiş bir dizi. İçerikler 0 olarak başlatılır. Eğer istenen byte sayısı ayrılamazsa bir özel durum harekete geçirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      uint32Array = new Uint32Array( length );  
uint32Array = new Uint32Array( array );  
uint32Array = new Uint32Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametreler  
 `uint32Array`  
 Gerekli. Değişken adına **Uint32Array** nesne atanır.  
  
 `length`  
 Dizinin içindeki öğelerin sayısını belirtir.  
  
 `array`  
 Bu dizinin içinde yer alan dizi (veya türü belirtilmiş dizi). İçerik, her öğe Uint32 türüne dönüştürülerek, belirtilen veya yazılan dizinin içerikleri için başlatılır.  
  
 `buffer`  
 Uint32Array tarafından temsil edilen ArrayBuffer.  
  
 `byteOffset`  
 İsteğe bağlı. Uint32Array'in başlatılması gereken arabelleğin başlangıçtan itibaren bayt uzaklığını belirtir.  
  
 `length`  
 Dizideki öğelerin sayısı  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki tabloda sabitleri `Uint32Array`nesnesi.  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT sabiti](../../javascript/reference/bytes-per-element-constant-uint32array.md)|Dizideki her öğenin bayt cinsinden boyutu.|  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda sabitleri `Uint32Array`nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[buffer özelliği](../../javascript/reference/buffer-property-uint32array.md)|Salt okunur. Bu dizi tarafından başvurulan ArrayBuffer nesnesini alır.|  
|[byteLength özelliği](../../javascript/reference/bytelength-property-uint32array.md)|Salt okunur. Bu dizinin, oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzunluğu.|  
|[byteOffset özelliği](../../javascript/reference/byteoffset-property-uint32array.md)|Salt okunur. Bu dizinin oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzaklığı.|  
|[length özelliği](../../javascript/reference/length-property-uint32array.md)|Dizinin uzunluğu.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Uint32Array`nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[set yöntemi (Uint32Array)](../../javascript/reference/set-method-uint32array.md)|Bir değer ya da değerler dizisi ayarlar.|  
|[subarray yöntemi (Uint32Array)](../../javascript/reference/subarray-method-uint32array.md)|Bu dizinin ArrayBuffer deposunun yeni bir Uint32Array görünümünü alır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir Uint32Array nesnesinin bir XMLHttpRequest nesnesinden alınan ikili veriyi işlemek için nasıl kullanılacağını gösterir:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Uint32Array(buffer.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getUint32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]