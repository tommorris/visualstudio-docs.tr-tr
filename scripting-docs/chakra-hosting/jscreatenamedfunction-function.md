---
title: JsCreateNamedFunction işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a55f3df1d086394a7431b355f037b33e3f4a86c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788216"
---
# <a name="jscreatenamedfunction-function"></a>JsCreateNamedFunction İşlevi
Yeni bir JavaScript işlevinin adı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `name`  
 Tanılama ve stringification amacıyla kullanılacak bu işlevin adı.  
  
 `nativeFunction`  
 İşlevi çağrıldığında çağrılacak yöntem.  
  
 `callbackState`  
 Kullanıcı tarafından sağlanan geri geri çağırma geçirilen durumu.  
  
 `function`  
 Yeni işlev nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)