---
title: ATTACH_REASON | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2dc7736f9210ef15cec8cece45d7899cc116a334
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="attachreason"></a>ATTACH_REASON
Bir program düğüm eklemek için hata ayıklama altyapısı (DE) nedenini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
typedef DWORD ATTACH_REASON;  
```  
  
```csharp  
public enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
```  
  
## <a name="members"></a>Üyeler  
 ATTACH_REASON_AUTO  
 İşlem şu anda hata ayıklama modunda olduğundan ekleyin.  
  
 ATTACH_REASON_LAUNCH  
 İşlem başlatıldığından ekleyin.  
  
 ATTACH_REASON_USER  
 Bir kullanıcı isteği nedeniyle ekleyin.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerleri parametre olarak kullanılan [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) ve [Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Ekleme](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)