---
title: PENDING_BP_STATE_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PENDING_BP_STATE_INFO
helpviewer_keywords:
- PENDING_BP_STATE_INFO structure
ms.assetid: 4d73ceff-43f9-4e95-8dba-88e1fab2def3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a4bf5f77ae24d83a0c0874d2cd03d1f5abbc0e2f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135747"
---
# <a name="pendingbpstateinfo"></a>PENDING_BP_STATE_INFO
Bir kod konuma bağlamak hazır bir kesme noktası durumu hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _tagPENDING_BP_STATE_INFO {   
   PENDING_BP_STATE       state;  
   PENDING_BP_STATE_FLAGS flags;  
} PENDING_BP_STATE_INFO;  
```  
  
```csharp  
public struct PENDING_BP_STATE_INFO {   
   public uint state;  
   public uint flags;  
};  
```  
  
## <a name="members"></a>Üyeler  
 durum  
 Arasında bir değer [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md) bekleyen kesme noktası durumunu belirtir numaralandırması.  
  
 bayraklar  
 Bayraklarını bileşimini [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md) numaralandırma kesme sanallaştırılmış olup olmadığını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md) yöntemi burada bunu doldurulur.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)   
 [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md)   
 [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md)