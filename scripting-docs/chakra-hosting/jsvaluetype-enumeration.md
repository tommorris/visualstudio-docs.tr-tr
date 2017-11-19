---
title: "JsValueType numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsValueType
helpviewer_keywords: JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df4f61cf9118c19a0fc35e7505af422b812d0b43
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsvaluetype-enumeration"></a>JsValueType Numaralandırması
Bir JsValueRef JavaScript türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum JsValueType {  
    JsUndefined      = 0,  
    JsNull           = 1,  
    JsNumber         = 2,  
    JsString         = 3,  
    JsBoolean        = 4,  
    JsObject         = 5,  
    JsFunction       = 6,  
    JsError          = 7,  
    JsArray          = 8,  
    JsSymbol         = 9,  
    JsArrayBuffer    = 10,  
    JsTypedArray     = 11,  
    JsDataView       = 12,  
};  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`JsUndefined`|Değer `undefined` değeri.|  
|`JsNull`|Değer `null` değeri.|  
|`JsNumber`|Bir JavaScript sayı değeri değerdir.|  
|`JsString`|Değer bir JavaScript dize değeridir.|  
|`JsBoolean`|Değer bir JavaScript Boolean değeridir.|  
|`JsObject`|JavaScript nesne değeri değerdir.|  
|`JsFunction`|Değer bir JavaScript işlevi nesne değerdir.|  
|`JsError`|Değer bir JavaScript hata nesnesi değerdir.|  
|`JsArray`|Değer bir JavaScript dizi nesnesi değerdir.|  
|`JsSymbol`|JavaScript sembol değeri değerdir.<br /><br /> Bu numaralandırma değeri yalnızca kenar modunda desteklenir.|  
|`JsArrayBuffer`|JavaScript değerdir `ArrayBuffer` nesne değeri.<br /><br /> Bu numaralandırma değeri yalnızca kenar modunda desteklenir.|  
|`JsTypedArray`|JavaScript değerdir yazılan dizi nesne değeri.<br /><br /> Bu numaralandırma değeri yalnızca kenar modunda desteklenir.|  
|`JsDataView`|JavaScript değerdir `DataView` nesne değeri.<br /><br /> Bu numaralandırma değeri yalnızca kenar modunda desteklenir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)