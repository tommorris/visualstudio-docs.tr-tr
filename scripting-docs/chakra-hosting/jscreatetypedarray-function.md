---
title: "JsCreateTypedArray işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1df33d0e1aadec9d7ed5aebf743e2c2f840e51fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatetypedarray-function"></a>JsCreateTypedArray İşlevi
Bir JavaScript yazılan dizi nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `arrayType`  
 Oluşturulacak dizinin türü.  
  
 `baseArray`  
 Yeni bir dizi temel dizisi. Kullanım `JS_INVALID_REFERENCE` temel bir dizi durumunda.  
  
 `byteOffset`  
 Bayt başından uzaklık `baseArray` (`ArrayBuffer`) dizi başvuru sonucu yazılan. Yalnızca uygun olduğunda `baseArray` olan bir `ArrayBuffer` nesnesi. Aksi halde 0 olmalıdır.  
  
 `elementLength`  
 Dizideki öğelerin sayısı Yeni belirlenmiş bir dizi olmadan oluştururken, yalnızca geçerli `baseArray` (`baseArray` olan `JS_INVALID_REFERENCE`) veya ne zaman `baseArray` olan bir `ArrayBuffer` nesnesi. Aksi halde 0 olmalıdır.  
  
 `result`  
 Yeni belirlenmiş bir dizi nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 `baseArray` Olabilir bir `ArrayBuffer`, dizi ya da bir JavaScript başka yazılan `Array`. Verilen yazılı dizi kullanacağı `baseArray` etkinleştirilmişse bir `ArrayBuffer`, veya aksi oluşturmak ve temel alınan kaynak dizisinin bir kopyasını kullanın.  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)