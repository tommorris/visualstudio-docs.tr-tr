---
title: "Jsthreadservicecallback tür | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c4b7ea4d0d5eaba17269a1777cdf96b5a2a5cda3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsthreadservicecallback-typedef"></a>JsThreadServiceCallback Tür Tanımı
Bir iş parçacığı hizmet geri araması.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 geri arama  
 Arka plan iş öğesi için geri arama.  
  
 callbackData  
 Geri arama işlemine aktarılacak veri bağımsız değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 Ana bilgisayar, JsCreateRuntime çağrılırken bir arka plan iş parçacığı hizmeti belirtebilir. Belirtilmiş olması durumunda arka plan iş öğeleri, bu geri arama kullanılarak ana bilgisayara gönderilir. Ana bilgisayar, arka plan iş öğesini hemen çalıştırmaya başlar ve doğru döndürür ya da yanlış döndürür ve çalışma zamanı iş parçacığındaki iş öğesini işler.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)