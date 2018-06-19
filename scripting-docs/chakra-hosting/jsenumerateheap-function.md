---
title: JsEnumerateHeap işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEnumerateHeap
helpviewer_keywords:
- JsEnumerateHeap function
ms.assetid: 3e518e0b-b959-4686-899c-83e6b1946c9d
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 48d7698218df49b8ffd680cf26df370c2f97b7c0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788273"
---
# <a name="jsenumerateheap-function"></a>JsEnumerateHeap İşlevi
Geçerli bağlam yığın numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsEnumerateHeap(  
   _Out_ IActiveScriptProfilerHeapEnum **enumerator  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `enumerator`  
 Yığın Numaralandırıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Öbek numaralandırılan olsa da, geçerli bağlam kaldırılamaz ve yığın Numaralandırıcı serbest kadar içerik durumunu değiştirmek için tüm çağrıları başarısız olur.  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Bu API, masaüstü uygulamalarında desteklenir, ancak mağaza uygulamalarında desteklenmiyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)