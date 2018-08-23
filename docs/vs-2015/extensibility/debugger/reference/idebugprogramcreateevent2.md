---
title: IDebugProgramCreateEvent2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgramCreateEvent2
helpviewer_keywords:
- IDebugProgramCreateEvent2 interface
ms.assetid: b19a7934-6179-4a68-9075-bd7dcd640b05
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eb1cf67cc10925323d6995c5b3816e949347a79c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684504"
---
# <a name="idebugprogramcreateevent2"></a>IDebugProgramCreateEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgramCreateEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramcreateevent2).  
  
Bir program bağlı olduğu bu arabirimi hata ayıklama altyapısı (DE) oturum hata ayıklama Yöneticisi (SDM) gönderilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProgramCreateEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 DE veya özel bağlantı noktası sağlayıcısı programı, genellikle programın bağlı olduğu zaman oluşturulduğunu bildirmek için bu arabirimi uygular. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) arabirim uygulandığında, bu arabirimle aynı nesne üzerinde. SDM kullanan `QueryInterface` erişmeye yöntemi `IDebugEvent2` arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 DE veya özel bağlantı noktası sağlayıcısı oluşturur ve bu olay bir program oluşturmayı rapor nesnesine gönderir. Kullanarak DE bu olay gönderen [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) ayıklanan programa eklendiğinde SDM tarafından sağlanan geri çağırma işlevi. Özel bağlantı noktası sağlayıcısı kullanarak bu olay gönderir [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 Özel bağlantı noktası sağlayıcısı ve DE yeni bir yayımlar [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) çağırarak arabirim [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

