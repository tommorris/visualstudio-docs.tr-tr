---
title: IDebugQueryEngine2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugQueryEngine2
helpviewer_keywords:
- IDebugQueryEngine2 interface
ms.assetid: 8f0e1838-a818-4459-9138-a3dceb7408de
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a54b6f6ab5667993553074f1ca2511a544a0eaea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugqueryengine2"></a>IDebugQueryEngine2
Bu arabirim, hata ayıklama Yöneticisi (SDM) almak hata ayıklama altyapısı (DE) temsil eden bir arabirim oturum sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugQueryEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 DE en yaygın DE arabirimleri uygulayan nesneler üzerinde bu arabirimi uygulayan (gibi [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md), [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md), ve [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)) içinde erişmesine izin vermek için sipariş [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) DE arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [QueryInterface](/cpp/atl/queryinterface) bu arabirimi sağlamak için tipik bir DE arabiriminde.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugQueryEngine2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetEngineInterface](../../../extensibility/debugger/reference/idebugqueryengine2-getengineinterface.md)|Bir özel hata ayıklama altyapısı (DE) arabirimi alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirimi uygulayan nesne genel uygulanır [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) causality sıralı aracılığıyla işlevleri atlama; diğer bir deyişle, hata ayıklayıcı dışında işlevi, zaman atlama desteklemek için arabirimi yürütülecek sonraki işlevi yığında önceki işlevi ancak başka bir iş parçacığı işlevinde tamamen olmayabilir. "Causality" tanımı için bkz: [Visual Studio hata ayıklayıcısı sözlüğü](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)