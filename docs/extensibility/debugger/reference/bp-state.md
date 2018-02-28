---
title: BP_STATE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_STATE
helpviewer_keywords:
- BP_STATE enumeration
ms.assetid: 08aa6a3f-3e5f-4c83-8eca-7b7b5f8e208d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9b6c4dee3540b061c967a01730ae0da8de644c7a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bpstate"></a>BP_STATE
İlişkili bir kesme noktası varlığını ve ayrıca etkin olup olmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BP_STATE {   
   BPS_NONE     = 0x0000,  
   BPS_DELETED  = 0x0001,  
   BPS_DISABLED = 0x0002,  
   BPS_ENABLED  = 0x0003  
};  
typedef DWORD BP_STATE;  
```  
  
```csharp  
public enum enum_BP_STATE {   
   BPS_NONE     = 0x0000,  
   BPS_DELETED  = 0x0001,  
   BPS_DISABLED = 0x0002,  
   BPS_ENABLED  = 0x0003  
};  
```  
  
## <a name="members"></a>Üyeler  
 BPS_NONE  
 Hiçbir kesme noktası var olduğunu belirtir.  
  
 BPS_DELETED  
 Kesme noktası silinmiş olduğunu belirtir.  
  
 BPS_DISABLED  
 Kesme noktası devre dışı olduğunu belirtir.  
  
 BPS_ENABLED  
 Kesme noktası etkinleştirilip etkinleştirilmediğini belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)