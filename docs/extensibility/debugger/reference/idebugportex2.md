---
title: IDebugPortEx2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPortEx2
helpviewer_keywords:
- IDebugPortEx2 interface
ms.assetid: 144724d0-38ee-4c9b-87ca-8a504371182b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8e7ee976d2dfb5872474090d4fabbd56f963faf8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportex2"></a>IDebugPortEx2
Bu arabirim, programlar ve bağlantı noktası üzerinde çalışan işlemler Yöneticisi'ni (SDM) denetiminde hata ayıklama oturumu sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugPortEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bir bağlantı noktası sağlayıcı uygulayan aynı nesne üzerinde bu arabirimi uygulayan [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md).  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 SDM çağrıları [QueryInterface](/cpp/atl/queryinterface) üzerinde `IDebugPort2` bu arabirimi sağlamak için arabirim.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugPortEx2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)|Yürütülebilir bir dosyanın başlatır.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)|Bir işlemin yürütülmesi sürdürür.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugportex2-canterminateprocess.md)|Bir işlem sonlandırıldı olup olmadığını belirler.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugportex2-terminateprocess.md)|Bir işlemi sonlandırır.|  
|[GetPortProcessId](../../../extensibility/debugger/reference/idebugportex2-getportprocessid.md)|Bağlantı işlem Kimliğini alır.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugportex2-getprogram.md)|Bir program düğümüyle ilişkilendirilen bir program alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim normalde SDM ve özel bağlantı noktası tedarikçi arasında özeldir.  
  
 İsterseniz, bir hata ayıklama altyapısı (DE) Bu arabirim için bakabilirsiniz [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) arabirimi geçirilen [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) ve [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) programını başlatmak için. Ancak, bu bir gereklilik olmadığı ve ne olursa olsun istek programını başlatmak için yapması gereken bir DE yapabilirsiniz.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)