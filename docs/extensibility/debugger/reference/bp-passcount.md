---
title: BP_PASSCOUNT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_PASSCOUNT
helpviewer_keywords:
- BP_PASSCOUNT structure
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f7437a61688958a1346b9c638ad07e3e55dc51f5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="bppasscount"></a>BP_PASSCOUNT
Bağlı koşullu kesme noktası tetiklenir sayısı ve koşulları açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _BP_PASSCOUNT {   
   DWORD              dwPassCount;  
   BP_PASSCOUNT_STYLE stylePassCount;  
} BP_PASSCOUNT;  
```  
  
```csharp  
public struct BP_PASSCOUNT {   
   public uint dwPassCount;  
   public uint stylePassCount;  
};  
```  
  
## <a name="members"></a>Üyeler  
 `dwPassCount`  
 Kesme noktası tetiklemeden önce geçmesi için zamanlar sayısı.  
  
 `stylePassCount`  
 Arasında bir değer [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md) kesme stilini belirtir numaralandırması sayısı geçirin.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesi olan [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) yapısı.  
  
 Bu yapı ayrıca bir parametre olarak geçirilen[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md) ve[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)   
 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)