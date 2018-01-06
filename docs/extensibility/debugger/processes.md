---
title: "İşlemler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e69270c5d90c26cf653ee31b81bcb9f453b814e1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="processes"></a>İşlemler
Hata ayıklayıcı mimarisi bakımından bir **işlem**:  
  
-   Programları kümesi için bir kapsayıcıdır. Bu, yakından iş parçacığı kümesi için bir kapsayıcıdır Windows işlemine benzerdir.  
  
-   Kendisi adına, tanımlayıcı veya fiziksel tanımlayıcı göre tanımlayabilirsiniz.  
  
-   Çalışan diğer tüm programları (ve bunların iş parçacıkları) sıralayabilirsiniz.  
  
-   Kendisi, onu çalıştığı bağlantı noktasını ve içerdiği makine tanımlayabilirsiniz.  
  
-   Bir tane oluşturabilirsiniz veya daha fazla program oluşturduğu programlardan herhangi biri sonlandırma veya durdurmak bir program neden.  
  
-   Tarafından temsil edilen bir [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) işlemi başlatıldığında oluşturmuş arabirimi. Bir işlem ya da oturum hata ayıklama Yöneticisi tarafından (SDM) başlatılır veya [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 Hata ayıklama paket hata ayıklama altyapısı (DE) bir işlemin çağırarak iliştirebilirsiniz [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md). Başka bir deyişle, DE ele alabilir işlemde çalışan tüm olası programlar ekler. Örneğin, ortak dil çalışma zamanı DE bir işlem bağlanıyorsa, yönetilen kod çalışmakta olan programların ekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Programlar](../../extensibility/debugger/programs.md)   
 [İş parçacıkları](../../extensibility/debugger/threads.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [Paket hata ayıklama](../../extensibility/debugger/debug-package.md)   
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md)