---
title: SEEK_START | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SEEK_START
helpviewer_keywords: SEEK_START enumeration
ms.assetid: 55bd8901-626e-428b-a263-23b14417f4c6
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 10937c4a5078574f7658bc54f2508b576209f9d5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="seekstart"></a>SEEK_START
Ayrıştırılmış akışında aramayı başlayacağı konumu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
typedef DWORD SEEK_START;  
```  
  
```csharp  
public enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
```  
  
## <a name="members"></a>Üyeler  
 SEEK_START_BEGIN  
 Geçerli belgenin başında aramayı başlatır.  
  
 SEEK_START_END  
 Geçerli belgenin sonuna aramayı başlatır.  
  
 SEEK_START_CURRENT  
 Geçerli belge geçerli konumuna aramayı başlatır.  
  
 SEEK_START_CODECONTEXT  
 Geçerli belgede verilen kodu bağlamı aramayı başlatır.  
  
 SEEK_START_CODELOCID  
 Verilen kodu konumu tanımlayıcıda aramayı başlatır. Kod konumu tanımlayıcıları elde edilir çağırarak [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Arama](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)   
 [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)