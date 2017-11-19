---
title: "Bir kesme noktası basarsa | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73cdce5415dd50059dcd443f67424203430aba87
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="hitting-a-breakpoint"></a>Bir kesme noktası çıkma
Hata ayıklama altyapısı (DE) çalıştıran veya atlama bir kesme noktası geldiğinde aşağıdaki işlemini açıklar:  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>İsabet bir kesme noktası sorunlarını giderme  
  
1.  DE gönderir bir [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) olarak arabirim bir **EVENT_SYNC_STOP**.  
  
2.  Oturum hata ayıklama Yöneticisi'ni (SDM) çağırır [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) ulaşıldı kesme noktası almak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama hata ayıklayıcı olayları](../../extensibility/debugger/calling-debugger-events.md)