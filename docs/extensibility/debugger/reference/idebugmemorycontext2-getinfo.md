---
title: IDebugMemoryContext2::GetInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugMemoryContext2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugMemoryContext2::GetInfo method
ms.assetid: 08c7f091-1816-4d64-8834-f9ecaac5c58d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ff035004831f8efa6e378b2ddf85251699c66c18
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmemorycontext2getinfo"></a>IDebugMemoryContext2::GetInfo
Alır bir [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) bağlam açıklar yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetInfo(   
   CONTEXT_INFO_FIELDS dwFields,  
   CONTEXT_INFO*       pInfo  
);  
```  
  
```csharp  
int GetInfo(  
   enum_CONTEXT_INFO_FIELDS dwFields,   
   CONTEXT_INFO[]           pinfo  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwFields`  
 [in] Bayraklarını bileşimini [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) hangi alanlarının belirten numaralandırma [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) yapısı olan olmasını doldurun.  
  
 `pInfo`  
 [içinde out] `CONTEXT_INFO` Doldurulur yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)