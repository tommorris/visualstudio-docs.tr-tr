---
title: Float32Array nesnesi | Microsoft Docs
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
ms.assetid: 4b29456a-1488-4006-ae66-5bf4c05003b1
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f7ef022b43179d2d9ce3f88fc78b8854d3cea62
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790703"
---
# <a name="float32array-object"></a>Float32Array Nesnesi
Türü belirlenmiş 32-bit kayan değerler dizisi. İçerikler 0 olarak başlatılır. Eğer istenen byte sayısı ayrılamazsa bir özel durum harekete geçirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      float32Array = new Float32Array( length );  
float32Array = new Float32Array( array );  
float32Array = new Float32Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametreler  
 `float32Array`  
 Gerekli. Değişken adına **Float32Array** nesne atanır.  
  
 `length`  
 Dizinin içindeki öğelerin sayısını belirtir.  
  
 `array`  
 Bu dizinin içinde yer alan dizi (veya türü belirtilmiş dizi). İçerik, her öğe Float32 türüne dönüştürülerek, belirtilen veya yazılan dizinin içerikleri için başlatılır.  
  
 `buffer`  
 Float32Array tarafından temsil edilen ArrayBuffer.  
  
 `byteOffset`  
 İsteğe bağlı. Float32Array'in başlatılması gereken arabelleğin başlangıçtan itibaren bayt uzaklığını belirtir.  
  
 `length`  
 Dizideki öğelerin sayısı  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki tabloda sabitleri `Float32Array`nesnesi.  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT sabiti](../../javascript/reference/bytes-per-element-constant-float32array.md)|Dizideki her öğenin bayt cinsinden boyutu.|  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda sabitleri `Float32Array`nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[buffer özelliği](../../javascript/reference/buffer-property-float32array.md)|Salt okunur. Bu dizi tarafından başvurulan ArrayBuffer nesnesini alır.|  
|[byteLength özelliği](../../javascript/reference/bytelength-property-float32array.md)|Salt okunur. Bu dizinin, oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzunluğu.|  
|[byteOffset özelliği](../../javascript/reference/byteoffset-property-float32array.md)|Salt okunur. Bu dizinin oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzaklığı.|  
|[length özelliği](../../javascript/reference/length-property-float32array.md)|Dizinin uzunluğu.|  
|||  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Float32Array`nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[get yöntemi](../../javascript/reference/get-method-float32array.md)|Atlanabilir. Belirtilen dizindeki öğeyi alır.|  
|[set yöntemi (Float32Array)](../../javascript/reference/set-method-float32array.md)|Bir değer ya da değerler dizisi ayarlar.|  
|[subarray yöntemi (Float32Array)](../../javascript/reference/subarray-method-float32array.md)|Bu dizinin ArrayBuffer deposunun yeni bir Float32Array görünümünü alır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir Float32Array nesnesinin bir XmlHttpRequest nesnesinden alınan ikili veriyi işlemek için nasıl kullanılacağını gösterir:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Float32Array(buffer.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getFloat32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]