---
title: Int16array nesnesi | Microsoft Docs
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
ms.assetid: b87f36b4-4e38-4f32-b258-654c4ad2c615
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 550208f0f13ac05f96c13b240952d59ee62c097e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790856"
---
# <a name="int16array-object"></a>Int16Array Nesnesi
16 bit tamsayı değerleri belirlenmiş bir dizi. İçerikler 0 olarak başlatılır. Eğer istenen byte sayısı ayrılamazsa bir özel durum harekete geçirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int16Array = new Int16Array( length );  
int16Array = new Int16Array( array );  
int16Array = new Int16Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametreler  
 `int16Array`  
 Gerekli. Değişken adına **ınt16array** nesne atanır.  
  
 `length`  
 Dizinin içindeki öğelerin sayısını belirtir.  
  
 `array`  
 Bu dizinin içinde yer alan dizi (veya türü belirtilmiş dizi). İçerik, her öğe Int16 türüne dönüştürülerek, belirtilen veya yazılan dizinin içerikleri için başlatılır.  
  
 `buffer`  
 Int16Array tarafından temsil edilen ArrayBuffer.  
  
 `byteOffset`  
 İsteğe bağlı. Int16Array'in başlatılması gereken arabelleğin başlangıçtan itibaren bayt uzaklığını belirtir.  
  
 `length`  
 Dizideki öğelerin sayısı  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki tabloda sabitleri `Int16Array`nesnesi.  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT sabiti](../../javascript/reference/bytes-per-element-constant-int16array.md)|Dizideki her öğenin bayt cinsinden boyutu.|  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda sabitleri `Int16Array`nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[buffer özelliği](../../javascript/reference/buffer-property-int16array.md)|Salt okunur. Bu dizi tarafından başvurulan ArrayBuffer nesnesini alır.|  
|[byteLength özelliği](../../javascript/reference/byteoffset-property-int16array.md)|Salt okunur. Bu dizinin, oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzunluğu.|  
|[byteOffset özelliği](../../javascript/reference/byteoffset-property-int16array.md)|Salt okunur. Bu dizinin oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzaklığı.|  
|[length özelliği](../../javascript/reference/length-property-int16array.md)|Dizinin uzunluğu.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Int16Array`nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[set yöntemi (ınt16array)](../../javascript/reference/set-method-int16array.md)|Bir değer ya da değerler dizisi ayarlar.|  
|[subarray yöntemi (ınt16array)](../../javascript/reference/subarray-method-int16array.md)|Bu dizinin ArrayBuffer deposunun yeni bir Int16Array görünümünü alır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir Int16Array nesnesinin bir XmlHttpRequest nesnesinden alınan ikili veriyi işlemek için nasıl kullanılacağını gösterir:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Int16Array(buffer.byteLength / 2);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt16(i * 2);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]