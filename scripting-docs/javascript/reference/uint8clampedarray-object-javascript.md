---
title: Uint8ClampedArray nesnesi (JavaScript) | Microsoft Docs
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
ms.assetid: 0c5537f7-00b4-487a-8fba-ef032e67e7bd
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51673eadc8eb905355bf136dc82b2f240462180a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792167"
---
# <a name="uint8clampedarray-object-javascript"></a>Uint8ClampedArray nesnesi (JavaScript)
8 bit işaretsiz tamsayı aralığı 0-255 clamped değerlerle belirlenmiş bir dizi. İçerikler 0 olarak başlatılır. İstenen bayt sayısı ayrılamıyor, özel durum oluşur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      uint8ClampedArray = new Uint8ClampedArray( length );  
uint8ClampedArray = new Uint8ClampedArray( array );  
uint8ClampedArray = new Uint8ClampedArray( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametreler  
 `uint8ClampedArray`  
 Gerekli. Değişken adına `Uint8ClampedArray` nesne atanır.  
  
 `length`  
 İsteğe bağlı. Dizideki öğelerin sayısı  
  
 `array`  
 İsteğe bağlı. Array (ya da yazılı array), bu dizisi içerir. İçerikleri verilen dizi içeriğini başlatılır veya her öğe ile yazılan dizi dönüştürülür `Uint8` türü.  
  
 `buffer`  
 İsteğe bağlı. [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) , `Uint8ClampedArray` temsil eder.  
  
 `byteOffset`  
 İsteğe bağlı. Bayt withintext arabellek başından uzaklık `Uint8ClampedArray` başlamanız gerekir.  
  
 `length`  
 İsteğe bağlı. Dizideki öğelerin sayısı  
  
## <a name="remarks"></a>Açıklamalar  
 Depolanan değerleri bir `Uint8ClampedArray` nesne olan 0 ile 255 arasında. Bir dizi üyesi için negatif bir değer ayarlarsanız, 0 değerini ayarlanır. 255 255'ten büyük bir değer ayarlarsanız, değer olarak ayarlanır.  
  
 Değerler bir `Uint8ClampedArray` nesne için yuvarlanır çift değer en yakın adlandırılan banker yuvarlaması.  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki tabloda sabitleri `Uint8ClampedArray` nesnesi.  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT sabiti](../../javascript/reference/bytes-per-element-constant-uint8clampedarray.md)|Dizideki her öğe bayt cinsinden boyutu.|  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda sabitleri `Uint8ClampedArray` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[buffer özelliği](../../javascript/reference/buffer-property-uint8clampedarray.md)|Salt okunur. Alır [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) bu dizisi tarafından başvurulan.|  
|[byteLength özelliği](../../javascript/reference/bytelength-property-uint8clampedarray.md)|Salt okunur. Başından bu dizi uzunluğu, kendi [ArrayBuffer](../../javascript/reference/arraybuffer-object.md), oluşturma zamanında sabit olarak bayt cinsinden.|  
|[byteOffset özelliği](../../javascript/reference/byteoffset-property-uint8clampedarray.md)|Salt okunur. Bu dizinin başından uzaklık kendi [ArrayBuffer](../../javascript/reference/arraybuffer-object.md), oluşturma zamanında sabit olarak bayt cinsinden.|  
|[length özelliği](../../javascript/reference/length-property-uint8clampedarray.md)|Dizinin uzunluğu.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Uint8ClampedArray` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[set yöntemi](../../javascript/reference/set-method-uint8clampedarray.md)|Bir değer ya da değerler dizisi ayarlar.|  
|[subarray yöntemi](../../javascript/reference/subarray-method-uint8clampedarray.md)|Yeni bir alır `Uint8ClampedArray` görünümünü [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) subarray ilk ve son öğelerini belirtme bu dizi için depolama.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösteren bir `Uint8ClampedArray` öğesinden alınan ikili verileri işlemek için nesne bir `XmlHttpRequest`:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Uint8ClampedArray(buffer.byteLength);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getUint8(i);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, değerleri nasıl kısıtlanır gösterir bir `Uint8ClampedArray`.  
  
```JavaScript  
var ints = new Uint8ClampedArray(2);  
ints[0] = -1;  // 0 will be assigned.  
ints[1] = 256; // 255 will be assigned.  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, değerler nasıl yuvarlanır gösterir bir `Uint8ClampedArray`.  
  
```  
var ints = new Uint8ClampedArray(4);  
ints[0] = 11.3; // 11 will be assigned (same as Int8Array).  
ints[1] = 11.8; // 12 will be assigned (same as Int8Array).  
ints[2] = 10.5; // 10 will be assigned (rounded to the nearest   
                // even value).  
ints[3] = 11.5; // 12 will be assigned (rounded to the nearest   
                // even value).  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uint8Array nesnesi](../../javascript/reference/uint8array-object.md)   
 [ArrayBuffer nesnesi](../../javascript/reference/arraybuffer-object.md)
