---
title: IDebugEventCallback2::Event | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEventCallback2::Event
helpviewer_keywords:
- IDebugEventCallback2::Event
ms.assetid: e5a3345b-d460-4e40-8f5b-3111c56a2ed9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8ea52b8be040df50da1585165599c4fdea635557
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugeventcallback2event"></a>IDebugEventCallback2::Event
Hata ayıklama olayların bildirim gönderir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Event(   
   IDebugEngine2*  pEngine,  
   IDebugProcess2* pProcess,  
   IDebugProgram2* pProgram,  
   IDebugThread2*  pThread,  
   IDebugEvent2*   pEvent,  
   REFIID          riidEvent,  
   DWORD           dwAttrib  
);  
```  
  
```csharp  
int Event(   
   IDebugEngine2  pEngine,  
   IDebugProcess2 pProcess,  
   IDebugProgram2 pProgram,  
   IDebugThread2  pThread,  
   IDebugEvent2   pEvent,  
   ref Guid       riidEvent,  
   uint           dwAttrib  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pEngine`  
 [in] Bir [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) bu olay gönderme hata ayıklama altyapısı (DE) temsil eden nesne. SE bu parametreyi doldurmak için gereklidir.  
  
 `pProcess`  
 [in] Bir [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) olayın oluştuğu işlemi temsil eden nesne. Bu parametre (SDM) oturum hata ayıklama Yöneticisi tarafından girilir. SE Bu parametre için null değer her zaman geçirir.  
  
 `pProgram`  
 [in] Bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) bu olay gerçekleştiği programı temsil eden nesne. Çoğu olaylar için bu parametre bir null değer değil.  
  
 `pThread`  
 [in] Bir [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) bu olay gerçekleştiği iş parçacığı temsil eden nesne. Yığın çerçevesi bu parametresinden elde olayları durdurmak için bu parametre bir null değer olamaz.  
  
 `pEvent`  
 [in] Bir [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) hata ayıklama olayı temsil eden nesne.  
  
 `riidEvent`  
 [in] Almak üzere hangi olay arabirimi tanımlayan GUID `pEvent` parametresi.  
  
 `dwAttrib`  
 [in] Bayraklarını bileşimini [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md) numaralandırması.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağrılırken `dwAttrib` parametresi, döndürülen değer eşleşmelidir [GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md) yöntemini olay nesne üzerinde çağrılan gibi geçirilen `pEvent` parametresi.  
  
 Bir olay zaman uyumsuz olup olmamasına bakılmaksızın tüm hata ayıklama olayları zaman uyumsuz olarak gönderilir. SE bu yöntem aradığında, yalnızca olay alındı olup olmadığını dönüş değerini olay olup olmadığını işlendi, göstermez. Aslında, bu yöntem döndürüldüğünde çoğu koşullar altında olay işlenmedi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)