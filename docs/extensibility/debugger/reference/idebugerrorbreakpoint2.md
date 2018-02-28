---
title: IDebugErrorBreakpoint2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugErrorBreakpoint2
helpviewer_keywords:
- IDebugErrorBreakpoint2 interface
ms.assetid: 1f2a4b94-3713-46e9-8272-3917187792bd
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2ea3b71f0ae5e66e100d7252c77c2fb1068b8985
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugerrorbreakpoint2"></a>IDebugErrorBreakpoint2
Bu arabirim, bir hata veya geçersiz bir konum, geçersiz bir ifade veya neden bekleyen kesme noktası (kod yüklenmedi henüz, vb.) bağlı değil nedenleri gibi uyarı kesme noktası temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugErrorBreakpoint2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı, kesme noktaları desteğini bir parçası olarak bu arabirimi uygular. Bu arabirim, bir kesme noktası bağlama sorunları bildirmek için kullanılır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) bu arabirim alır. Bu arabirim de döndürülebilecek (tarafından temsil edilen bir listesinin bir parçası olarak bir [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md) arabirimi) için yapılan bir çağrı tarafından [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md) veya [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md).  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugErrorBreakpoint2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)|Hatanın nedeni bekleyen kesme noktası alır.|  
|[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)|Hatayı açıklayan kesme hatası çözümleme alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)   
 [GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)   
 [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)   
 [Sonraki](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-next.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpointResolution2](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md)