---
title: "Bir kesme noktası oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoints, creating
- debugging [Debugging SDK], creating breakpoints
ms.assetid: 6f9f87bb-192e-45e0-9a7a-ffe729e87f7d
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 529c0a018aa48ab4e66fbe1e550b4d2909dc340f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-breakpoint"></a>Bir kesme noktası oluşturma
Bir kesme noktası oluşturma işlemi açıklanır.  
  
## <a name="methods-in-breakpoint-creation"></a>Kesme noktası oluşturma yöntemleri  
 Bir kesme noktası bağlanması gereken modülü yüklendiğinde oturum hata ayıklama Yöneticisi'ni (SDM) aşağıdaki yöntemleri çağırır:  
  
1.  [IDebugPendingBreakpoint2::Enable](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)  
  
2.  [IDebugPendingBreakpoint2::Virtualize](../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)  
  
3.  [IDebugPendingBreakpoint2::CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)  
  
    > [!NOTE]
    >  **CanBind** yalnızca bir kullanıcı kesme noktaları penceresinden bir kesme noktası bulunduğunda çağrılır.  
  
4.  [IDebugPendingBreakpoint2::Bind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)  
  
5.  [IDebugPendingBreakpoint2::EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama hata ayıklayıcı olayları](../../extensibility/debugger/calling-debugger-events.md)