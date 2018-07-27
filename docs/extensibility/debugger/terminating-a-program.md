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
ms.openlocfilehash: e1914d00af1eeda94ef1cf9129e637ce39306257
ms.sourcegitcommit: 8d38d5d2f2b75fc1563952c0d6de0fe43af12766
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39276968"
---
# <a name="terminating-a-program"></a>Program sonlandırma
Aşağıdaki bölümde, bir iş parçacığı ile tek bir programın sonlandırılması açıklanmaktadır.  
  
## <a name="termination-process"></a>Sonlandırma işlemi  
  
1.  DE gönderen bir [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) ile geçerli bir [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md).  
  
2.  DE gönderen bir [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) ile geçerli bir [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md).  
  
 IDE tasarım moduna geçer. Hata ayıklama altyapısı veya çalışma zamanı ortamı çağrıları [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) bağlantı noktasından programı kaldırın.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Hata ayıklayıcısı olaylarını çağırma](../../extensibility/debugger/calling-debugger-events.md)