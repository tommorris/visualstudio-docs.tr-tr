---
title: Denetim olaylarına | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ac93da53f21b56df38a6ad597d7c4911075a670
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691439"
---
# <a name="control-events"></a>Denetim Olayları
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [denetim olayları](https://docs.microsoft.com/visualstudio/extensibility/debugger/control-events).  
  
Olay denetimli programınızı yürütülmesi sırasında göndermeniz gerekir. Tüm olayları kullanılarak gönderilen [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md) uygulamak ihtiyaç duyduğunuz özniteliklere sahip ve arabirim [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md) yöntemi.  
  
## <a name="additional-methods"></a>Ek yöntemleri  
 Bazı olaylar şu şekilde ek yöntemleri uygulaması gerekir:  
  
-   Gönderme [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) hata ayıklama altyapısı (DE) başlatıldığında arabirim uygulamak gerektirir [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md) yöntemi.  
  
-   Yürütme denetimi gibi denetim olaylar uygulaması gerektirir [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md) ve[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) arabirimleri. **IDebugBreakEvent2** yalnızca zaman uyumsuz kesmeleri için gereklidir.  
  
-   İşlevlerin içine Adımlama gerektirir uygulaması [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) arabirimi ve yöntemleri.  
  
 Kesme noktaları türetme olayları gerektiren uygulaması [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md), [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), ve [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) arabirimleri, hem de [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) ve [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) yöntemleri.  
  
 Zaman uyumsuz bir ifade değerlendirme uygulamak gerektirir [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) arabirimi ve kendi [IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md) [ve GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) yöntemleri.  
  
 Zaman uyumlu olayları gerektiren uygulama [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) yöntemi.  
  
 Altyapınız dize stili çıkışını yazmak uygulamanız gereken [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme Denetimi ve Durum Değerlendirmesi](../../extensibility/debugger/execution-control-and-state-evaluation.md)

