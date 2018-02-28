---
title: "Denetim olaylarına | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 15f9eff023fa875499881eb05a0795b0eaa83842
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="control-events"></a>Denetim olayları
Olayları programınızı denetimli yürütülmesi sırasında göndermeniz gerekir. Tüm olaylar kullanılarak gönderilen [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md) arabirim ve uygulamak ihtiyaç duyduğunuz özniteliklere sahip [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md) yöntemi.  
  
## <a name="additional-methods"></a>Ek yöntemleri  
 Bazı olaylar gibi ek yöntemleri uyarlamasını gerektirir:  
  
-   Gönderme [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) hata ayıklama altyapısı (DE) başlatıldığında arabirimi gerektirir, uygulamanızı [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md) yöntemi.  
  
-   Yürütme denetimi gerektirir gibi denetim olaylar uyarlamasını [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md) ve[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) arabirimleri. **IDebugBreakEvent2** yalnızca zaman uyumsuz sonları için gereklidir.  
  
-   İşlevler Adımlama gerektirir uyarlamasını [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) arabirimi ve onun yöntemleri.  
  
 Kesme noktaları türetme olayların gerektirdiği uyarlamasını [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md), [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), ve [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) arabirimleri, aynı zamanda [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) ve [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) yöntemleri.  
  
 Zaman uyumsuz ifade değerlendirme gerektirir, uygulamanızı [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) arabirimi ve kendi [IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md) [ve GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) yöntemleri.  
  
 Zaman uyumlu olaylar gerektiren uygulama [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) yöntemi.  
  
 Altyapınız dize stili çıkışını yazmak uygulamanız gereken [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme Denetimi ve Durum Değerlendirmesi](../../extensibility/debugger/execution-control-and-state-evaluation.md)