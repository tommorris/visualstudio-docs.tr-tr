---
title: PROCESS_INFO_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 91e4c4648108cdc6afa28f5a5dd8f9bfd46fcf59
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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