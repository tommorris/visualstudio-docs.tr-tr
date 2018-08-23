---
title: IDebugPendingBreakpoint2 | Microsoft Docs
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
- IDebugPendingBreakpoint2
helpviewer_keywords:
- IDebugPendingBreakpoint2 interface
ms.assetid: d416b095-917e-475e-b796-ec0a03ffb8da
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f979af5789d6e695c5ca33c8cc9acdc74cc66815
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632847"
---
# <a name="idebugpendingbreakpoint2"></a>IDebugPendingBreakpoint2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugPendingBreakpoint2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpendingbreakpoint2).  
  
Bu arabirim, bir kod konuma bağlamak hazır bir kesme noktası temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugPendingBreakpoint2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE), kesme noktaları desteğini bir parçası olarak bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bir çağrı [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) bir bekleyen kesme noktasından oluşturur bir [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) arabirimi. Bir çağrı [bağlama](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) oluşturur bir `IDebugBreakpoint2` programı ilişkili bir kesme noktası temsil eden arabirim.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugPendingBreakpoint2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)|Bu bekleyen kesme noktasının bir kod konumuna bağlayabilirsiniz olup olmadığını belirler.|  
|[bağlama](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)|Bu bekleyen kesme noktasının bir veya daha fazla kod konumlara bağlar.|  
|[GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)|Bekleyen kesme noktası bu durumu alır.|  
|[GetBreakpointRequest](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)|Bu bekleyen kesme noktası oluşturmak için kullanılan bir kesme noktası istek alır.|  
|[Sanallaştırın](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)|Bu sanallaştırılmış bekleyen kesme noktasının durumunu değiştirir.|  
|[Etkinleştirme](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)|Bu etkin bekleyen kesme noktasının durumunu değiştirir.|  
|[SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)|Bu kesme noktası ilişkilendirilmiş olan koşul değiştirir veya ayarlar.|  
|[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)|Bu kesme noktası ilişkili parola sayısı değiştirir veya ayarlar.|  
|[EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)|Bu bekleyen kesme noktasından bağlı tüm kesme noktalarını numaralandırır.|  
|[EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)|Bu bekleyen kesme noktasından sonuçlanan tüm hata kesme noktalarını numaralandırır.|  
|[DELETE](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)|Bu bekleyen kesme noktasının ve ondan bağlı tüm kesme noktalarını siler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IDebugPendingBreakpoint2` bir kesme noktası için bir veya daha çok programlar uygulanabilir kodu bağlamak için gereken tüm gerekli bilgileri sağlayıcısı olarak düşünülebilir.  
  
 Bir bekleyen kesme noktasının potansiyel olarak birden fazla bağlı Kesme noktasının üretebilir. Örneğin, bir kesme noktası C++ stili şablonunda, şablon benzersiz her örneği için ilişkili bir kesme noktası üretebilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)

