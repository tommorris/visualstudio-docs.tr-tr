---
title: MODULE_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MODULE_FLAGS
helpviewer_keywords:
- MODULE_FLAGS enumeration
ms.assetid: 0e555b42-b846-4dbb-812e-8e3d11c85b2d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 945a4a0fd5a7de1e9d04d409390caddfc718d92d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="moduleflags"></a>MODULE_FLAGS
Bir modül tanımlamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_MODULE_FLAGS {   
   MODULE_FLAG_NONE        = 0x0000,  
   MODULE_FLAG_SYSTEM      = 0x0001,  
   MODULE_FLAG_SYMBOLS     = 0x0002,  
   MODULE_FLAG_64BIT       = 0x0004,  
   MODULE_FLAG_OPTIMIZED   = 0x0008,  
   MODULE_FLAG_UNOPTIMIZED = 0x0010  
};  
typedef DWORD MODULE_FLAGS;  
```  
  
```csharp  
public enum enum_MODULE_FLAGS {   
   MODULE_FLAG_NONE        = 0x0000,  
   MODULE_FLAG_SYSTEM      = 0x0001,  
   MODULE_FLAG_SYMBOLS     = 0x0002,  
   MODULE_FLAG_64BIT       = 0x0004,  
   MODULE_FLAG_OPTIMIZED   = 0x0008,  
   MODULE_FLAG_UNOPTIMIZED = 0x0010  
};  
```  
  
## <a name="members"></a>Üyeler  
 MODULE_FLAG_NONE  
 Hiçbir modül belirtir.  
  
 MODULE_FLAG_SYSTEM  
 Bir Sistem Modülü belirtir.  
  
 MODULE_FLAG_SYMBOLS  
 Bir simge modül belirtir.  
  
 MODULE_FLAG_64BIT  
 Bir 64-bit modül belirtir.  
  
 MODULE_FLAG_OPTIMIZED  
 İyileştirilmiş Modülü belirtir. Bu durum yansıtılmıştır **modülleri** penceresi.  
  
 MODULE_FLAG_UNOPTIMIZED  
 Modül getirilmemiş belirtir. Bu durum yansıtılmıştır **modülleri** penceresi. Bu varsayılan durumdur.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `m_dwModuleFlags` üyesi [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) yapısı.  
  
 Bu bayrakların bit ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)