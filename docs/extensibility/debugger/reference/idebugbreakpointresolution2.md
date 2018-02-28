---
title: IDebugBreakpointResolution2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBreakpointResolution2
helpviewer_keywords:
- IDebugBreakpointRequest2 interface
ms.assetid: 451d5bce-b9c1-48ff-beaa-2b4c3e1ceea0
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a8e3b6bc1b3666a616c4ffc866116274b42b4537
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbreakpointresolution2"></a>IDebugBreakpointResolution2
Bu arabirim, ilişkili bir kesme noktası açıklayan bilgileri temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBreakpointResolution2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE), kesme noktaları desteğini bir parçası olarak bu arabirimi uygular. Bu arabirim oturum hata ayıklama Yöneticisi kullanıcı kesme noktası ait özellikler görüntülediğinde kullanan ilişkili bir kesme noktası açıklamasını sağlar.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md) bu arabirimini döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugBreakpointResolution2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetBreakpointType](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md)|Bu çözüm tarafından temsil edilen kesme noktası türünü alır.|  
|[GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)|Bu kesme açıklar kesme noktası çözümleme bilgilerini alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)