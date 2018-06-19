---
title: İş parçacığı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a2754d3b1b15771f876855e7ca7d1dc510748308
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31125792"
---
# <a name="threads"></a>İş Parçacıkları
Hata ayıklayıcı mimarisi bakımından bir **iş parçacığı**:  
  
-   Temel hesaplama birimidir. Bir iş parçacığı bağlamında kendi yönergeleri bir kod bağlamdan sonraki taşıma tek çağrı yığınının, sıralı olarak yürütür.  
  
-   Kendisi ve programın, çalıştıran ve adlandırılmış, askıya ve olması sürdürüldü tanımlayabilirsiniz. Bir iş parçacığı Ayrıca kendi ilişkili yığın çerçeveleri numaralandırabilir ve bazı koşullarda, başka bir yığın çerçevesine taşınabilir. Yığın çerçevesi bağlamında verildiğinde, bir iş parçacığı, ilişkili mantıksal iş parçacığı varsa geri dönebilirsiniz. Bir iş parçacığı IDE iş parçacığı penceresinde görüntülenen bir askıya alma sayısı gibi özelliklere sahiptir.  
  
-   Tarafından temsil edilen bir [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) arabirimi, genellikle bir hata ayıklama altyapısı (DE) veya bir program yürütme gruplarındaki sonucu olarak sanal makine tarafından oluşturulmuş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Programlar](../../extensibility/debugger/programs.md)   
 [Yığın çerçeveleri](../../extensibility/debugger/stack-frames.md)   
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [Oturum Hata Ayıklama Yöneticisi](../../extensibility/debugger/session-debug-manager.md)