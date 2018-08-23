---
title: BP_PASSCOUNT | Microsoft Docs
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
- BP_PASSCOUNT
helpviewer_keywords:
- BP_PASSCOUNT structure
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d0706ddf3ee032d612ba72f31c59c7675376aae4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627716"
---
# <a name="bppasscount"></a>BP_PASSCOUNT
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [BP_PASSCOUNT](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-passcount).  
  
Bağlı bir koşullu kesme noktası tetiklendiğinde sayısı ve koşullar açıklanmaktadır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Kaç kez tetiklemeden önce üzerinde bir kesme noktası geçirilecek.  
  
 `stylePassCount`  
 Bir değer [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md) kesme noktası stilini belirten sabit listesi sayısı geçirin.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesidir [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) yapısı.  
  
 Bu yapı ayrıca bir parametre olarak geçirilen[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md) ve[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)   
 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)

