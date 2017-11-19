---
title: IDebugProgramEngines2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEngines2
helpviewer_keywords: IDebugProgramEngines2 interface
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 99ff94445caf60edde57f4365abbb5241d61127d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramengines2"></a>IDebugProgramEngines2
Bu arabirim, bu program ayıklayabilirsiniz tüm olası hata ayıklama altyapısı (DE) belirtmek için program düğümler tarafından kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProgramEngines2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 SE veya özel bir bağlantı noktası sağlayıcı uygulayan aynı nesne üzerinde bu arabirimi uygulayan [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) belirli bir program için kullanılacak belirli SE oluşturma desteklemek için.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [QueryInterface](/cpp/atl/queryinterface) üzerinde bir `IDebugProgramNode2` bu arabirimi sağlamak için arabirim.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugProgramEngines2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|Bu program ayıklayabilirsiniz olası DEs gösterir.|  
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|Bu program hata ayıklama için kullanılacak DE seçer.|  
  
## <a name="remarks"></a>Açıklamalar  
 SE kullanıcı tarafından seçilen sonra bu seçenek program düğümle çağırarak kayıtlı [SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md). Seçili olan altyapı tarafından döndürülen altyapısı hale [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)