---
title: PROCESS_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6e95e9f66b804fed102c0d51aa17a1bfe4f51ca5
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS

Açıklar veya bir işlem özelliklerini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
typedef DWORD PROCESS_INFO_FLAGS;
```

```csharp
enum enum_PROCESS_INFO_FLAGS { 
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,
   PIFLAG_PROCESS_STOPPED   = 0x00000004,
   PIFLAG_PROCESS_RUNNING   = 0x00000008,
};
```

## <a name="members"></a>Üyeler

PIFLAG_SYSTEM_PROCESS  
İşlem bir sistem işlemi olduğunu gösterir.

PIFLAG_DEBUGGER_ATTACHED  
İşlemi bir hata ayıklayıcı tarafından ayıklanacak gösterir. Bu olabilir bir [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı veya bazı diğer hata ayıklayıcı, örneğin, WinDbg olabilir.

PIFLAG_PROCESS_STOPPED  
İşlem durduruldu gösterir. Geçerli eksikse `PIFLAG_DEBUGGER_ATTACHED` da belirtilmiş. Visual Studio 2005 ve sonraki sürümlerinde kullanılabilir.

PIFLAG_PROCESS_RUNNING  
İşlemin çalışmadığını gösterir. Geçerli eksikse `PIFLAG_DEBUGGER_ATTACHED` da belirtilmiş. Visual Studio 2005 ve sonraki sürümlerinde kullanılabilir.

## <a name="remarks"></a>Açıklamalar

İçin kullanılan `Flags` üyesi [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) yapısı.

Bu bayrakların bit ile birleştirilebilir `OR`.

## <a name="requirements"></a>Gereksinimler

Başlık: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Ayrıca Bkz.

[Sabit Listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)