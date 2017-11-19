---
title: "ArrayBuffer.isView işlevi (ArrayBuffer) | Microsoft Docs"
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
ms.assetid: 1887324f-892b-4fcd-ad33-748ba9517a06
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5aaae2acb38aa2f8c4b5e49ea203e86665315700
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="arraybufferisview-function-arraybuffer"></a>ArrayBuffer.isView İşlevi (ArrayBuffer)
Bir nesne arabellek bir görünümünü sunan olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
ArrayBuffer.isView(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Sınanacak nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`Aşağıdaki true ise:  
  
-   `object`olan bir `DataView` nesnesi.  
  
-   `object`türü belirtilmiş bir dizidir.  
  
 Aksi durumda, yöntem döndürür `false`.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `isView` belirlenmiş bir dizi test etmek için işlev ve `DataView` nesne.  
  
```JavaScript  
var uint = new UInt8ClampedArray(10);  
  
if(console && console.log) {  
    console.log( ArrayBuffer.isView(uint) ); // Outputs true  
{  
var dataView = new DataView(uint.buffer);  
  
if(console && console.log) {  
    console.log( ArrayBuffer.isView(dataView) ); // Outputs true.  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uint8ClampedArray nesnesi](../../javascript/reference/uint8clampedarray-object-javascript.md)