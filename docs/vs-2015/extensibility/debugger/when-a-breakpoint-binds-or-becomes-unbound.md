---
title: Bir kesme noktası bağlandığı veya bağlanmamış hale geldiği zaman | Microsoft Docs
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
- debugging [Debugging SDK], breakpoint unbound events
- breakpoint bound events
ms.assetid: 61bf00b2-8293-49d3-b919-1efb0dec9151
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e2f14f141993e65509f4ee3ba21e727a5a4abfb4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630122"
---
# <a name="when-a-breakpoint-binds-or-becomes-unbound"></a>Kesme Noktasının Bağlandığı veya Bağlanmamış Hale Geldiği Durumlar
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [olduğunda bir kesme noktası bağlar veya bağlanmamış hale](https://docs.microsoft.com/visualstudio/extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound).  
  
Bir kesme noktası için bir çağrı yapılır zaman bağlanamaz olduğunda [IDebugPendingBreakpoint2::CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md) yöntemi, bağlama süresi ve oluşturma zamanı kesme noktasının farklıdır.  
  
## <a name="methods-called"></a>Olarak adlandırılan yöntemler  
 Oturum hata ayıklama Yöneticisi (SDM) aşağıdaki yöntemleri çağırır:  
  
1.  [IDebugEngine2::CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md). DE döndürür bir [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md).  
  
2.  [IDebugPendingBreakpoint2::Enable](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md).  
  
3.  [IDebugPendingBreakpoint2::Virtualize](../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md).  
  
4.  [IDebugPendingBreakpoint2::Bind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) yöntemi ve başarılıysa S_OK döndürür. DE gönderen bir [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) veya [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md).  
  
5.  [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) ve [IDebugBreakpointBoundEvent2::EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) doğrulamak ve bağlı kesme noktalarını almak için yöntemleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)

