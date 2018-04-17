---
title: DEBUG_REASON | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_REASON
helpviewer_keywords:
- DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 47cfd171d23420396c6d7ab5416db32cc05511f0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugreason"></a>DEBUG_REASON
Hata ayıklama için işlem neden başlatıldı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
typedef DWORD DEBUG_REASON;  
```  
  
```csharp  
public enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 DEBUG_REASON_ERROR  
 Belirli olmayan bir hata oluştu (diğer hiçbiri uygun neden olduğunda bu varsayılan koşulu olarak kullanılır).  
  
 DEBUG_REASON_USER_LAUNCHED  
 İşlem, kullanıcının isteği üzerine başlatıldı.  
  
 DEBUG_REASON_USER_ATTACHED  
 Zaten çalışan işlemi kullanıcı tarafından bağlanmıştır.  
  
 DEBUG_REASON_AUTO_ATTACHED  
 Bunu başlatıldı, işlem için otomatik olarak bağlanmıştır.  
  
 DEBUG_REASON_CAUSALITY  
 İşlem nedeniyle başlatılan bir *zaman içinde sadece* (JIT) hata ayıklama olay.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)