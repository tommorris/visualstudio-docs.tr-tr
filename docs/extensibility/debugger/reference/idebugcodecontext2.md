---
title: IDebugCodeContext2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCodeContext2
helpviewer_keywords:
- IDebugCodeContext2 interface
ms.assetid: 3670439e-2171-405d-9d77-dedb0f1cba93
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 75403c0597b2285aa9117f3ffb51acd01c967f3d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcodecontext2"></a>IDebugCodeContext2
Bu arabirim bir kod yönergesi başlangıç konumunu temsil eder. Çoğu çalışma zamanı mimari için bugün, bir kod bağlamı, adresi bir programın yürütme akış olarak düşünülebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugCodeContext2 : IDebugMemoryContext2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı belge konumu için bir kod yönergesi konumunu ilişkilendirmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çok sayıda arabirim yöntemleri dönüş bu arabirim en tipik olarak, [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md). Ayrıca yaygın ile kullanılır [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) de kesme noktası çözümleme bilgilerini olduğu gibi arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Yöntemlere ek olarak [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) arabirimi, bu arabirimi uygulayan aşağıdaki yöntemleri:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)|Etkin kod bağlamına karşılık gelen belge bağlamını alır.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugcodecontext2-getlanguageinfo.md)|Bu kodu bağlamı için dil bilgilerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Arasındaki temel farklılık bir `IDebugCodeContext2` arabirimi ve bir [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) arabirimi olan bir `IDebugCodeContext2` her zaman yönerge hizalanır. Bunun anlamı bir `IDebugCodeContext2` ancak bir yönerge başlangıcına işaret her zaman bir `IDebugMemoryContext2` tüm çalışma zamanı mimarisi bellekte baytını işaret edebilir. `IDebugCodeContext2`yönergeler yerine temel depolama boyutu (genellikle bayt) göre artırılır.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)   
 [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)   
 [Sonraki](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)