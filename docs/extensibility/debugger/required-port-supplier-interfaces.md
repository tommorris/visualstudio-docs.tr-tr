---
title: Bağlantı noktası tedarikçi arabirimleri gerekli | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- port suppliers, required interfaces
- debugging [Debugging SDK], port suppliers
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e34627effce5e2f0d1401da683536548a32d3f6e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128668"
---
# <a name="required-port-supplier-interfaces"></a>Gerekli bağlantı noktası tedarikçi arabirimleri
Bir bağlantı noktası tedarikçi uygulamalıdır [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) arabirimi.[ IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)  
  
 Bir bağlantı noktası sağlayıcı bağlantı noktaları sağlayan olduğundan, ayrıca bunları uygulamalıdır. Bu nedenle, aşağıdaki arabirimleri uygulamanız gerekir:  
  
-   [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)  
  
     Bağlantı noktası açıklar ve bağlantı noktası üzerinde çalışan tüm işlemler sıralayabilirsiniz.  
  
-   [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)  
  
     Başlatma ve bağlantı noktası işlemleri sona erdirmek için sağlar.  
  
-   [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)  
  
     Bu program düğüm oluşturma ve yok etme bildirmek için bu bağlantı noktasının bağlamı içinde çalışan programlar için bir mekanizma sağlar. Daha fazla bilgi için bkz: [Program düğümleri](../../extensibility/debugger/program-nodes.md).  
  
-   `IConnectionPointContainer`  
  
     Bir bağlantı noktası sağlar [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md).  
  
## <a name="port-supplier-operation"></a>Bağlantı noktası tedarikçi işlemi  
 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md) havuz işlem bildirimlerini alır ve program oluşturulur ve bir bağlantı noktası yok. Bir bağlantı noktası göndermek için gereken [IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md) bir işlem oluşturulduğunda ve [IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md) ne zaman bir işlem yok bağlantı noktası üzerinde. Bir bağlantı noktası da göndermek için gereken [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) bir program oluşturulduğunda ve [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) ne zaman bir program yok bağlantı noktası üzerinde çalışan bir işlemin içinde.  
  
 Bir bağlantı noktası genellikle gönderir program oluşturmak ve olayları yanıt olarak destroy [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) ve [RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) yöntemleri, sırasıyla.  
  
 Bir bağlantı noktası başlatın ve fiziksel işlemler ve mantıksal programlar sonlandırmak için bu arabirimleri hata ayıklama altyapısı tarafından da uygulanması gerekiyor:  
  
-   [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)  
  
     Fiziksel işlemini açıklar. En az aşağıdaki yöntemlerden uygulanması gerekir:  
  
    -   [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprocess2-getname.md)  
  
    -   [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)  
  
    -   [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
    -   [Getprocessıd](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)  
  
    -   [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)  
  
-   [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)  
  
     SDM ekleme ve kendisi bir işlemden ayırma bir yol sağlar.  
  
-   [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)  
  
     Mantıksal program açıklar. En az aşağıdaki yöntemlerden uygulanması gerekir:  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprogram2-getname.md)  
  
    -   [GetProcess](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)  
  
    -   [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)  
  
-   [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)  
  
     Bu program eklemek SDM için bir yol sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı Noktası Sağlayıcısı Uygulama](../../extensibility/debugger/implementing-a-port-supplier.md)