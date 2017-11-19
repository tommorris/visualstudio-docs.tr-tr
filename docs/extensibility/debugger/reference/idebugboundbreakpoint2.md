---
title: IDebugBoundBreakpoint2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBoundBreakpoint2
helpviewer_keywords: IDebugBoundBreakpoint2 interface
ms.assetid: df33c52e-ded2-48a0-951d-1f36c8fc922e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2322b548106a7cbfff5ca4d96d7fc2d317308b10
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugboundbreakpoint2"></a>IDebugBoundBreakpoint2
Bu arabirim bir kod konuma bağlı bir kesme noktası temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBoundBreakpoint2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE), kesme noktaları desteğini bir parçası olarak bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [bağlamak](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) bu arabirimi oluşturur. Çağrılar [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md) ve [sonraki](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md) da bu arabirimi elde edebilirsiniz.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugBoundBreakpoint2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|Belirtilen ilişkili kesme noktası oluşturulduğu bekleyen kesme noktası alır.|  
|[GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|Bu bağlama kesme noktası durumunu alır.|  
|[GetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-gethitcount.md)|Geçerli isabet sayısı için ilişkili bu kesme noktası alır.|  
|[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|Bu kesme açıklar kesme noktası çözümleme alır.|  
|[Etkinleştir](../../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|Etkinleştirir veya kesme devre dışı bırakır.|  
|[SetHitCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-sethitcount.md)|Bu bağlama kesme noktası isabet sayısı ayarlar.|  
|[SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)|Bu bağlama kesme noktası ile ilişkilendirilen koşulu değiştirir veya ayarlar.|  
|[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)|Kümeleri veya parola sayısı ile ilişkili bu kesme ilişkili değiştirme.|  
|[Sil](../../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|Kesme noktası siler.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)   
 [Sonraki](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)   
 [Bağlama](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)