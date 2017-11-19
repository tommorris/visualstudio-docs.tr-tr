---
title: IDebugProgramNode2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNode2
helpviewer_keywords: IDebugProgramNode2 interface
ms.assetid: 80e511d8-9b40-4a85-aa5d-952fa5ee6ae7
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a1696e3c22ff1e23c7728c5e12940a5559959ac1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramnode2"></a>IDebugProgramNode2
Bu arabirim hata ayıklaması yapılabilir bir programı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProgramNode2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) veya özel bir bağlantı noktası tedarikçi hata ayıklaması yapılabilir bir programı temsil etmek için bu arabirimi uygular. Bu arabirimi uygulayan aynı nesne üzerinde genel uygulanır [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) arabirimi. Bu arabirim kayıtlı [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] çağırarak [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md) bu arabirim dönün. Özel bir bağlantı noktası tedarikçi çağrısıyla bu arabirimin aldığı [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Bu arabirimin çağrısıyla SE aldığı [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugProgramNode2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetProgramName](../../../extensibility/debugger/reference/idebugprogramnode2-getprogramname.md)|Bir programın adını alır.|  
|[GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)|Bir program barındıran işlem adını alır.|  
|[GetHostPid](../../../extensibility/debugger/reference/idebugprogramnode2-gethostpid.md)|Bir program barındırma işlemi için sistem işlemi tanımlayıcısını alır.|  
|[GetHostMachineName_V7](../../../extensibility/debugger/reference/idebugprogramnode2-gethostmachinename-v7.md)|KULLANIM DIŞI. KULLANMAYIN.|  
|[Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)|KULLANIM DIŞI. KULLANMAYIN. Bkz: [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) alternatif bir yaklaşım için arabirim.|  
|[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)|Bu programı çalıştırmayı DE tanıtıcısı ve adını alır.|  
|[DetachDebugger_V7](../../../extensibility/debugger/reference/idebugprogramnode2-detachdebugger-v7.md)|KULLANIM DIŞI. KULLANMAYIN.|  
  
## <a name="remarks"></a>Açıklamalar  
 Oturum hata ayıklama Yöneticisi'ni (SDM) genellikle çağırır [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md) bu arabirimi elde edilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)   
 [RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)   
 [Ekleme](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)   
 [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)