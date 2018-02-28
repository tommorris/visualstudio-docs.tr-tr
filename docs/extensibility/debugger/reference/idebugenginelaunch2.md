---
title: IDebugEngineLaunch2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineLaunch2
helpviewer_keywords:
- IDebugEngineLaunch2 interface
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: fb53f64b6b98ed6d02774977138cfd4faf5b8f83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugenginelaunch2"></a>IDebugEngineLaunch2
Başlatma ve programları sonlandırabilir için hata ayıklama altyapısı (DE) tarafından kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEngineLaunch2 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Tamamen özel bir bağlantı noktası tarafından işlenen bir işlemi başlatmak için özel gereksinimleri varsa, bu arabirim tarafından özel SE uygulanır. Bu genellikle bir komut dosyası ayıklanacak işlem DE bir yorumlayıcı parçası olduğunda ve bir durumdur: yorumlayıcı ilk başlatılması gerekiyor ve komut dosyası sonra yüklenen ve başlatıldı. Bir bağlantı noktası yorumlayıcı başlatabilir, ancak komut dosyası (olan DE bir role sahip olduğu) bir özel işlem gerektirebilir. Yalnızca özel bir bağlantı noktası işleyemiyor bir programı başlatmak için benzersiz gereksinimleri varsa, bu arabirim uygulanır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim SDM gidebilirse bu arabirim (SDM) oturum hata ayıklama Yöneticisi tarafından çağrılır [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) arabirimi (QueryInterface kullanılarak). Bu arabirim elde ettiyseniz SDM DE özel gereksinimleri vardır ve başlatın bağlantı noktası sahip olmak yerine programını başlatmak için bu arabirimi çağırır bilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugEngineLaunch2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|Bir işlem DE yoluyla başlatır.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|Sürdürür yürütme işlemi.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|Bir işlem sona erdirilecek belirler.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|Bir işlemi sonlandırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)