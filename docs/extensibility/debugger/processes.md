---
title: İşlemler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3c07a9cb6c16f09f2f55b543087e25d85bc300c0
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251783"
---
# <a name="processes"></a>İşlemler
Hata ayıklayıcı mimarisinde bir *işlem*:  
  
-   Bir dizi program için bir kapsayıcıdır. Bu iş parçacığı bir dizi için bir kapsayıcı bir Windows işlem yakından benzerdir.  
  
-   Kendisini adı, tanımlayıcı veya fiziksel tanımlayıcısı tarafından tespit edebilirsiniz.  
  
-   Tüm çalışan programları (ve bunların iş parçacıkları) sıralayabilirsiniz.  
  
-   Kendisi, içinde çalıştığı bağlantı noktası ve içerdiği makine tanımlayabilirsiniz.  
  
-   Bir tane oluşturabilirsiniz veya daha fazla program oluşturduğu programlardan herhangi biriyle sonlandırmak veya bir programın durmasına neden.  
  
-   Tarafından temsil edilen bir [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) işlemi başlatıldığında oluşturulduğu arabirimi. Bir işlem ya da oturum hata ayıklama Yöneticisi tarafından (SDM) başlatılmadı veya [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 Hata ayıklama paketi bir hata ayıklama altyapısı (DE) bir işleme çağırarak iliştirilebilir [iliştirme](../../extensibility/debugger/reference/idebugprocess2-attach.md), işleyebileceği işlemde çalışan tüm olası programlar için DE bağlayan anlamına gelir. Örneğin, ortak dil çalışma zamanı DE bir işleme iliştirir, yönetilen kod çalışan programlar ekler.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Programlar](../../extensibility/debugger/programs.md)   
 [İş parçacıkları](../../extensibility/debugger/threads.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [Paket hatalarını ayıklama](../../extensibility/debugger/debug-package.md)   
 [Hata ayıklama altyapısı](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md)