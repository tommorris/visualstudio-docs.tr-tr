---
title: JsStartDebugging işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStartDebugging
helpviewer_keywords:
- JsStartDebugging function
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd9b7e3deb407d1a1e9d16db38e17c85ccc8c797
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788675"
---
# <a name="jsstartdebugging-function"></a>JsStartDebugging İşlevi
Geçerli bağlamda hata ayıklama başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
// Edge mode signature  
STDAPI_(JsErrorCode) JsStartDebugging();  
  
// Legacy mode signature  
STDAPI_(JsErrorCode)  JsStartDebugging(  
   _In_ IDebugApplication *debugApplication  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `debugApplication`  
 Hata ayıklama için kullanılacak hata ayıklama uygulama.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Ana bilgisayar olduğundan emin olmalısınız `CoInitializeEx` çağrılır `COINIT_MULTITHREADED` veya `COINIT_APARTMENTTHREADED` bu API kullanmadan önce en az bir kez  
  
 `debugApplication` Parametresi kenar modunda desteklenmiyor. Bu API kenar modda kullanma hakkında daha fazla bilgi için bkz: [hedefleme kenar vs. Eski altyapıların](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)