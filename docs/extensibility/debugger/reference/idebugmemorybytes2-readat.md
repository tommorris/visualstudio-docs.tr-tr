---
title: IDebugMemoryBytes2::ReadAt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f4c71da3152394442d63c937b77e4f6538fcc1ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmemorybytes2readat"></a>IDebugMemoryBytes2::ReadAt
Belirli bir konumda başlangıç bayt dizisi okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT ReadAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory,  
   DWORD*                pdwRead,  
   DWORD*                pdwUnreadable  
);  
```  
  
```csharp  
int ReadAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory,  
   out uint             pdwRead,  
   ref uint             pdwUnreadable  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) bayt okumaya başlamak konumu belirtir nesnesi.  
  
 `dwCount`  
 [in] Okunacak bayt sayısı. Ayrıca uzunluğunu belirtir `rgbMemory` dizi.  
  
 `rgbMemory`  
 [içinde out] Oturum bayt doldurulmuş dizi gerçekte okuyun.  
  
 `pdwRead`  
 [out] Gerçekte okunan bitişik bayt sayısını döndürür.  
  
 `pdwUnreadable`  
 [içinde out] Okunamaz bayt sayısını döndürür. İstemci okunamaz bayt sayısı uninterested ise boş bir değer olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 100 bayt istenir ve ilk 50 okunabilir, sonraki 20 okunamaz ve kalan 30 okunabilir varsa, bu yöntemi döndürür:  
  
 *`pdwRead` = 50  
  
 *`pdwUnreadable` = 20  
  
 Bu durumda, çünkü `*pdwRead + *pdwUnreadable < dwCount`, arayan istenen özgün 100 kalan 30 baytını okumak için ek bir arama yapmanız gerekir ve [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) nesnesi geçirildi `pStartContext` parametresi Gelişmiş 70 tarafından.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)