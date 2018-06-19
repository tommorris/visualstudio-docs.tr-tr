---
title: Jsbackgroundworkıtemcallback | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c4281ae1abf1df07d4b6374b6989377c66c1fd7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788174"
---
# <a name="jsbackgroundworkitemcallback-typedef"></a>JsBackgroundWorkItemCallback Tür Tanımı
Bir arka plan iş öğesi geri çağırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(  
   _In_opt_ void *callbackData  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 callbackData  
 İş parçacığı hizmete veri bağımsız değişken geçirildi.  
  
## <a name="remarks"></a>Açıklamalar  
 İş öğesi geri çağırma arka plan iş parçacığı kendi seçtikleri çağırmak konak izin vermek için bu (sağladıysanız) ana bilgisayarın iş parçacığı hizmetine geçirilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)