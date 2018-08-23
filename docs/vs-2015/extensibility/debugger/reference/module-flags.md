---
title: MODULE_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MODULE_FLAGS
helpviewer_keywords:
- MODULE_FLAGS enumeration
ms.assetid: 0e555b42-b846-4dbb-812e-8e3d11c85b2d
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 224a6db4b6c4860a2bf9a0b326319a3be1efc6a6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631215"
---
# <a name="moduleflags"></a>MODULE_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [MODULE_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/module-flags).  
  
Bir modülü tanımlamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Bir sistem modülünün belirtir.  
  
 MODULE_FLAG_SYMBOLS  
 Sembol Modülü belirtir.  
  
 MODULE_FLAG_64BIT  
 Bir 64-bit Modülü belirtir.  
  
 MODULE_FLAG_OPTIMIZED  
 İyileştirilmiş Modülü belirtir. Bu durumu yansıtılır **modülleri** penceresi.  
  
 MODULE_FLAG_UNOPTIMIZED  
 Modül getirilmemiş belirtir. Bu durumu yansıtılır **modülleri** penceresi. Varsayılan durum budur.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `m_dwModuleFlags` üyesi [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) yapısı.  
  
 Bu bayrak bit düzeyinde ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)

