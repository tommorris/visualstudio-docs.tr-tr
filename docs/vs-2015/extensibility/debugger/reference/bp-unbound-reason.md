---
title: BP_UNBOUND_REASON | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 554bdd9def52cfbde5b4fe535f017f762f1c8edc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627539"
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [BP_UNBOUND_REASON](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-unbound-reason).  
  
Bir kesme noktası ilişkisiz nedeni sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Kesme noktasını içeren kod kaldırıldı.  
  
 BPUR_BREAKPOINT_REBIND  
 Farklı bir konuma kesme noktası yansıdı. Bu düzenlemeden sonra gerçekleşir ve kesme noktası hareket ettiğinde veya artık geçerli olmayan bir yola sahip bir dosya kesme noktasına bağlandığında işlemler devam edebilirsiniz.  
  
 BPUR_ BREAKPOINT_ERROR  
 Kesme noktasına bağlı sonra hata olarak değerlendirilir. Bu, koşullar artık geçerli olmayan yönetilen kesme noktaları için gerçekleşir.  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)

