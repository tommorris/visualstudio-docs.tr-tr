---
title: "İş parçacığı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 150e27c4b8df06784848829bfe713773cf9d48a0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Oturum hata ayıklama Yöneticisi](../../extensibility/debugger/session-debug-manager.md)