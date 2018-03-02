---
title: IDebugProgramNode2::Attach_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramNode2::Attach
helpviewer_keywords:
- IDebugProgramNode2::Attach_V7
- IDebugProgramNode2::Attach
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7db57be153634476b8c0ba5ff6b6b1273ef190be
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="idebugprogramnode2attachv7"></a>IDebugProgramNode2::Attach_V7

> [!Note]
> KULLANIM DIŞI. KULLANMAYIN.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Attach_V7 (
   IDebugProgram2*       pMDMProgram,
   IDebugEventCallback2* pCallback,
   DWORD                 dwReason
);
```

```csharp
int Attach_V7 (
   IDebugProgram2       pMDMProgram,
   IDebugEventCallback2 pCallback,
   uint                 dwReason
);
```

#### <a name="parameters"></a>Parametreler

`pMDMProgram` [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) eklemek için program temsil eden arabirim.

 `pCallback` [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM için hata ayıklama olayları göndermek için kullanılacak arabirimi.

 `dwReason` [in] Arasında bir değer [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) ekleme nedenini belirtir numaralandırması.

## <a name="return-value"></a>Dönüş Değeri

Bir uygulama her zaman döndürmelidir `E_NOTIMPL`.

## <a name="remarks"></a>Açıklamalar

> [!WARNING]
> Visual Studio 2005 ' ten itibaren bu yöntem artık kullanılmıyor ve her zaman döndürmelidir `E_NOTIMPL`. Bkz: [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) program düğümü onu eklenemez için belirtmek gerekirse veya program düğüm yalnızca program ayarlıyorsanız alternatif bir yaklaşım için arabirim `GUID`. Aksi takdirde uygulama [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi.

## <a name="prior-to-visual-studio-2005"></a>Visual Studio 2005 önce

Bu yöntem yalnızca DE ayıklanacak program adres alanında çalışıyorsa uygulanması gerekir. Aksi takdirde, bu yöntem döndürmelidir `S_FALSE`.

Bu yöntem çağrıldığında DE göndermelidir [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) olay nesne, zaten bu örneği için gönderilmedi, [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) arabirimi, yanı sıra [ IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) ve [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) olay nesneleri. [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) olay nesnesi, ardından gönderilen `dwReason` parametresi `ATTACH_REASON_LAUNCH`.

DE çağırmanız gerekir [GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) yöntemi [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) tarafından sağlanan nesne [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) olay nesne ve bu programın GUID depolamanız gerekir Örnek verileri `IDebugProgram2` DE tarafından uygulanan nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)  
[IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)  
[Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)  
[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)  
[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)  
[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)  
[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
[IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
[IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)  
[ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)