---
title: "Jsmemoryallocationcallback tür | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9672c23f48a2cb3e20de58012b267b30f4514d66
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsmemoryallocationcallback-typedef"></a>JsMemoryAllocationCallback Tür Tanımı
Bellek ayırma olayları için kullanıcı tarafından uygulanan geri çağırma yordamı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 callbackState  
 Durum JsSetRuntimeMemoryAllocationCallback'e geçti.  
  
 allocationEvent  
 Tür ayırma olayının türü.  
  
 allocationSize  
 Ayırmanın boyutu.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 JsMemoryAllocate olayı için doğru değerine döndürme, çalışma zamanının ayırmaya devam etmesini sağlar. Yanlış değerine döndürme, ayırma isteğinin reddedildiğini gösterir. Dönüş değeri diğer ayırma olayları için yok sayılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu geri çağırmayı kaydetmek için JsSetRuntimeMemoryAllocationCallback'i kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)