---
title: IDebugPortEvents2::Event | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortEvents2::Event
helpviewer_keywords:
- IDebugPortEvents2::Event
ms.assetid: 5cc813f7-04a1-4462-9ea7-fbddcf0e0143
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c9f1394e09cc6b7b695d1d19dee1f46df09f8514
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugportevents2event"></a>IDebugPortEvents2::Event
Bu yöntem oluşturma ve yok etme işlemlerini ve programların bir bağlantı noktası belirtmek olaylar gönderir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Event(  
   IDebugCoreServer2* pServer,  
   IDebugPort2*       pPort,  
   IDebugProcess2*    pProcess,  
   IDebugProgram2*    pProgram,  
   IDebugEvent2*      pEvent,  
   REFIID             riidEvent  
);  
```  
  
```csharp  
int Event(  
   IDebugCoreServer2 pServer,   
   IDebugPort2       pPort,   
   IDebugProcess2    pProcess,   
   IDebugProgram2    pProgram,   
   IDebugEvent2      pEvent,   
   ref Guid          riidEvent  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pMachine`  
 [in] Bir [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) hata ayıklama sunucunun temsil eden nesnesi (her örneği için bir tane olduğunu [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]) olayın oluştuğu içinde.  
  
 `pPort`  
 [in] Bir [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) olayın oluştuğu bağlantı noktasını temsil eden nesne.  
  
 `pProcess`  
 [in] Bir [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) olayın oluştuğu işlemi temsil eden nesne.  
  
 `pProgram`  
 [in] Bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) olayın oluştuğu programı temsil eden nesne.  
  
 `pEvent`  
 [in] Bir [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) olayla ilgili tanımlayıcı nesnesi. Olası olayları aşağıdaki gibidir:  
  
-   [IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)  
  
-   [IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)  
  
-   [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
-   [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)  
  
 `riidEvent`  
 [in] Olay GUID. Olay için cast çünkü [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) bu yöntemi çağırmadan önce bu tanımlayıcı, hangi olay gönderilen belirlemek kolaylaştırır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)