---
title: BP_UNBOUND_REASON | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 65398ac0c4bde18dc772d75ceea203bdbfe3b189
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
Bir kesme noktası ilişkisiz nedeni sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
typedef DWORD BP_UNBOUND_REASON;  
```  
  
```csharp  
public enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
```  
  
## <a name="members"></a>Üyeler  
 BPUR_UNKNOWN  
 Bunun nedeni bilinmiyor.  
  
 BPUR_CODE_UNLOADED  
 Kesme noktası içeren kodu kaldırıldı.  
  
 BPUR_BREAKPOINT_REBIND  
 Kesme noktası farklı bir konuma DataSet'e. Bu düzen sonra gerçekleşir ve kesme taşındığında veya artık geçerli olmayan bir yola sahip bir dosyaya kesme bağlandığında işlemleri devam edebilirsiniz.  
  
 BPUR_ BREAKPOINT_ERROR  
 Kesme noktası bağlı olduğu sonra hata olduğu belirlenir. Bu, koşullar artık geçerli olmayan yönetilen kesme noktaları için gerçekleşir.  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)