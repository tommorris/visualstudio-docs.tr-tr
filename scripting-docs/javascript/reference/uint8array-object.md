---
title: Uint8Array nesnesi | Microsoft Docs
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
ms.assetid: ae78b3ee-b660-4625-ac7b-d414a0842c87
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72002af4ca92d1104a3c3c3bb2339e63856a80a6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791969"
---
# <a name="uint8array-object"></a>Uint8Array Nesnesi
Türü belirlenmiş 8 bit işaretsiz tamsayı değerleri dizisi. İçerikler 0 olarak başlatılır. Eğer istenen byte sayısı ayrılamazsa bir özel durum harekete geçirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      uint8Array = new Uint8Array( length );  
uint8Array = new Uint8Array( array );  
uint8Array = new Uint8Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametreler  
 `uint8Array`  
 Gerekli. Değişken adına **Uint8Array** nesne atanır.  
  
 `length`  
 Dizinin içindeki öğelerin sayısını belirtir.  
  
 `array`  
 Bu dizinin içinde yer alan dizi (veya türü belirtilmiş dizi). İçerik, her öğe Uint8 türüne dönüştürülerek, belirtilen veya yazılan dizinin içerikleri için başlatılır.  
  
 `buffer`  
 Uint8Array tarafından temsil edilen ArrayBuffer.  
  
 `byteOffset`  
 İsteğe bağlı. Uint8Array'in başlatılması gereken arabelleğin başlangıçtan itibaren bayt uzaklığını belirtir.  
  
 `length`  
 Dizideki öğelerin sayısı  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki tabloda sabitleri `Uint8Array`nesnesi.  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT sabiti](../../javascript/reference/bytes-per-element-constant-uint8array.md)|Dizideki her öğenin bayt cinsinden boyutu.|  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda sabitleri `Uint8Array`nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[buffer özelliği](../../javascript/reference/buffer-property-uint8array.md)|Salt okunur. Bu dizi tarafından başvurulan ArrayBuffer nesnesini alır.|  
|[byteLength özelliği](../../javascript/reference/bytelength-property-uint8array.md)|Salt okunur. Bu dizinin, oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzunluğu.|  
|[byteOffset özelliği](../../javascript/reference/byteoffset-property-uint8array.md)|Salt okunur. Bu dizinin oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzaklığı.|  
|[length özelliği](../../javascript/reference/length-property-uint8array.md)|Dizinin uzunluğu.|  
|||  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Uint8Array`nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[set yöntemi (Uint8Array)](../../javascript/reference/set-method-uint8array.md)|Bir değer ya da değerler dizisi ayarlar.|  
|[subarray yöntemi (Uint8Array)](../../javascript/reference/subarray-method-uint8array.md)|Bu dizinin ArrayBuffer deposunun yeni bir Uint8Array görünümünü alır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir Uint8Array nesnesinin bir XmlHttpRequest nesnesinden alınan ikili veriyi işlemek için nasıl kullanılacağını gösterir:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Uint8Array(buffer.byteLength);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getUint8(i);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]