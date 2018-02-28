---
title: BP_PASSCOUNT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_PASSCOUNT
helpviewer_keywords:
- BP_PASSCOUNT structure
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 62c523ee3d65a7149f8e25304e0b719470242685
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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