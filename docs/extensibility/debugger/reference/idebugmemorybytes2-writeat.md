---
title: IDebugMemoryBytes2::WriteAt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryBytes2::WriteAt
helpviewer_keywords:
- IDebugMemoryBytes2::WriteAt method
- WriteAt method
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4d1d79d88baf9688fe68ff44d59dcd4d19baf9f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmemorybytes2writeat"></a>IDebugMemoryBytes2::WriteAt
Belirtilen sayıda baytı belirtilen adresten başlayarak belleğin yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT WriteAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory  
);  
```  
  
```csharp  
int WriteAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) bayt yazmaya başlamak konumu belirtir nesnesi.  
  
 `dwCount`  
 [in] Yazılacak bayt sayısı.  
  
 `rgbMemory`  
 [in] Yazılacak bayt sayısı. Bu dizi en az olduğu varsayılır `dwCount` bayt cinsinden boyutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` tüm bayt yazılabilir veya bir hata kodu döndürür (genellikle `E_FAIL`).  
  
## <a name="remarks"></a>Açıklamalar  
 Başlangıç adresi bu tarafından temsil edilen bellek penceresi içinde olup olmadığını [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) nesnesi, hiçbir yazma oluşur ve hata kodunu `E_FAIL` döndürülen — bellek alanına yazmak için tutar çakışıyor olsa bile.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)