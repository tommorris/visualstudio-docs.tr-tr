---
title: BP_CONDITION | Microsoft Docs
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
- BP_CONDITION
helpviewer_keywords:
- BP_CONDITION structure
ms.assetid: 407f87a3-2878-429b-8c65-b68feb36622a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 569588d108de05823a733feef4137d35e1b79693
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693082"
---
# <a name="bpcondition"></a>BP_CONDITION
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [BP_CONDITION](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-condition).  
  
Altında bir kesme noktası harekete koşullar açıklanmaktadır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef struct _BP_CONDITION {   
   IDebugThread2* pThread;  
   BP_COND_STYLE  styleCondition;  
   BSTR           bstrContext;  
   BSTR           bstrCondition;  
   UINT           nRadix;  
} BP_CONDITION;  
```  
  
```csharp  
public struct BP_CONDITION {   
   public IDebugThread2 pThread;  
   public uint          styleCondition;  
   public string        bstrContext;  
   public string        bstrCondition;  
   public uint          nRadix;  
};  
```  
  
## <a name="members"></a>Üyeler  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) etkin iş parçacığı için kesme noktasını içeren uygulamayı temsil eden nesne.  
  
 `styleCondition`  
 Bir değer [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md) bu kesme noktası koşulu stilini açıklayan sabit listesi.  
  
 `bstrContext`  
 Kesme noktası konumu.  
  
 `bstrCondition`  
 Kesme noktası tetikleyicisinin tetikleme koşulunu.  
  
 `nRadix`  
 Sayısal yedeklenmesine değerlendirmede kullanılacak sayı tabanı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesidir [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) ve [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapıları.  
  
 Bu yapı ayrıca bir parametre olarak geçirilen [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md) ve [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md)

