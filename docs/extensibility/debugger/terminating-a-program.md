---
title: Program sonlandırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bc5d711783b3238c9cfe42ba3fc4edd776bcb060
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="terminating-a-program"></a>Program sonlandırma
Bir iş parçacığı ile tek bir program sonlandırma bir açıklaması verilmiştir.  
  
## <a name="termination-process"></a>Sonlandırma işlemi  
  
1.  DE gönderir bir [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) geçerli bir ile [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md).  
  
2.  DE gönderir bir [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) geçerli bir ile [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md).  
  
 IDE tasarım moduna girer. Hata ayıklama Motoru'nu veya çalışma zamanı ortamı [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) bağlantı noktasından programı kaldırmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)