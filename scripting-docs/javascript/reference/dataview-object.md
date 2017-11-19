---
title: DataView nesnesi | Microsoft Docs
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
ms.assetid: 250ec067-7505-4ee0-82ab-bfd3c2820afa
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 370ee1afbdf7fe1d87843c4979833d54a575a4fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="dataview-object"></a>DataView Nesnesi
DataView nesnesi okuyun ve herhangi bir konumda ArrayBuffer farklı türde ikili verileri yazmak için kullanabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
dataView = new DataView(buffer, byteOffset, byteLength);  
```  
  
## <a name="parameters"></a>Parametreler  
 `dataView`  
 Gerekli. Değişken adına **DataView** nesne atanır.  
  
 `buffer`  
 DataView temsil eden ArrayBuffer.  
  
 `byteOffset`  
 İsteğe bağlı. Başından aktarılma DataView başlaması gereken arabellek, bayt uzaklığı belirtir.  
  
 `byteLength`  
 İsteğe bağlı. DataView temsil etmelidir arabellek bölümünü uzunluğunu (bayt cinsinden) belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 ByteOffset ve byteLength atlanırsa, tüm ArrayBuffer aralığını DataView yayar. ByteLength atlanırsa, DataView verilen byteOffset ArrayBuffer sonuna kadar genişletir. ByteLength ve verilen byteOffset ArrayBuffer ötesinde bir alanı başvuruyorsa bir özel durum oluşturulur.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `DataView` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[buffer özelliği](../../javascript/reference/buffer-property-dataview.md)|Salt okunur. Bu görünüm tarafından başvurulan ArrayBuffer alır.|  
|[byteLength özelliği](../../javascript/reference/bytelength-property-dataview.md)|Salt okunur. Bu görünümün oluşturma zamanında sabitlendiği gibi ArrayBuffer'ın başından itibaren bayt cinsinden uzunluğu.|  
|[byteOffset özelliği](../../javascript/reference/byteoffset-property-dataview.md)|Salt okunur. Bu görünüm oluşturma zamanında sabit olarak bayt cinsinden kendi ArrayBuffer başından uzaklık.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `DataView`nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Getınt8 yöntemi](../../javascript/reference/getint8-method-dataview.md)|Int8 değer görünümü başından belirtilen bayt uzaklığı alır.|  
|[getUint8 yöntemi (DataView)](../../javascript/reference/getuint8-method-dataview.md)|Uint8 değer görünümü başından belirtilen bayt uzaklığı alır.|  
|[Getınt16 yöntemi (DataView)](../../javascript/reference/getint16-method-dataview.md)|Int16 değeri belirtilen bayt uzaklığı görünümü başından alır.|  
|[getUint16 yöntemi (DataView)](../../javascript/reference/getuint16-method-dataview.md)|Uint16 değer görünümü başından belirtilen bayt uzaklığı alır.|  
|[Getınt32 yöntemi (DataView)](../../javascript/reference/getint32-method-dataview.md)|Int32 değeri belirtilen bayt uzaklığı görünümü başından alır.|  
|[getUint32 yöntemi (DataView)](../../javascript/reference/getuint32-method-dataview.md)|Uint32 değer görünümü başından belirtilen bayt uzaklığı alır.|  
|[getFloat32 yöntemi (DataView)](../../javascript/reference/getfloat32-method-dataview.md)|Float32 değeri belirtilen bayt uzaklığı görünümü başından alır.|  
|[getFloat64 yöntemi (DataView)](../../javascript/reference/getfloat64-method-dataview.md)|Float64 değer görünümü başından belirtilen bayt uzaklığı alır.|  
|[Setınt8 yöntemi (DataView)](../../javascript/reference/setint8-method-dataview.md)|Görünüm başlangıç belirtilen bayt uzaklığı Int8 değerinde depolar.|  
|[setUint8 yöntemi (DataView)](../../javascript/reference/setuint8-method-dataview.md)|Görünüm başlangıç belirtilen bayt uzaklığı Uint8 değerinde depolar.|  
|[Setınt16 yöntemi (DataView)](../../javascript/reference/setint16-method-dataview.md)|Görünüm başlangıç belirtilen bayt uzaklığı Int16 değerinde depolar.|  
|[setUint16 yöntemi (DataView)](../../javascript/reference/setuint16-method-dataview.md)|Görünüm başlangıç belirtilen bayt uzaklığı Uint16 değerinde depolar.|  
|[Setınt32 yöntemi (DataView)](../../javascript/reference/setint32-method-dataview.md)|Görünüm başlangıç belirtilen bayt uzaklığı bir Int32 değeri depolar.|  
|[setUint32 yöntemi (DataView)](../../javascript/reference/setuint32-method-dataview.md)|Görünüm başlangıç belirtilen bayt uzaklığı Uint32 değerinde depolar.|  
|[setFloat32 yöntemi (DataView)](../../javascript/reference/setfloat32-method-dataview.md)|Görünüm başlangıç belirtilen bayt uzaklığı Float32 değerinde depolar.|  
|[setFloat64 yöntemi (DataView)](../../javascript/reference/setfloat64-method-dataview.md)|Görünüm başlangıç belirtilen bayt uzaklığı Float64 değerinde depolar.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir DataView nesnesi bir XmlHttpRequest edinilen ikili verileri işlemek için nasıl kullanılacağını gösterir:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var ints = new Int32Array(dataView.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]