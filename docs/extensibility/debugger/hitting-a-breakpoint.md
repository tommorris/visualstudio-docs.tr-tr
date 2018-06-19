---
title: Bir kesme noktası basarsa | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9f4788f8a038a274d6d94b4edf368e30ef495665
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109148"
---
# <a name="hitting-a-breakpoint"></a>Bir kesme noktası çıkma
Hata ayıklama altyapısı (DE) çalıştıran veya atlama bir kesme noktası geldiğinde aşağıdaki işlemini açıklar:  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>İsabet bir kesme noktası sorunlarını giderme  
  
1.  DE gönderir bir [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) olarak arabirim bir **EVENT_SYNC_STOP**.  
  
2.  Oturum hata ayıklama Yöneticisi'ni (SDM) çağırır [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) ulaşıldı kesme noktası almak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)