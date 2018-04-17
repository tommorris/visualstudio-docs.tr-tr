---
title: CONTEXT_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- CONTEXT_INFO_FIELDS
helpviewer_keywords:
- CONTEXT_INFO_FIELDS enumeration
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 05616ba660af188c26f192b97e29d5b60e04fe8a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="contextinfofields"></a>CONTEXT_INFO_FIELDS
Bellek bağlam hakkında almak için hangi bilgilerin belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_CONTEXT_INFO_FIELDS {   
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
typedef DWORD CONTEXT_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_CONTEXT_INFO_FIELDS {  
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
```  
  
## <a name="members"></a>Üyeler  
 CIF_MODULEURL  
 Başlatma/kullanım `bstrModuleUrl` alanını [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) yapısı.  
  
 CIF_FUNCTION  
 Başlatma/kullanım `bstrFunction` alanını `CONTEXT_INFO` yapısı.  
  
 CIF_FUNCTIONOFFSET  
 Başlatma/kullanım `posFunctionOffset` alanını `CONTEXT_INFO` yapısı.  
  
 CIF_ADDRESS  
 Başlatma/kullanım `bstrAddress` alanını `CONTEXT_INFO` yapısı.  
  
 CIF_ADDRESSOFFSET  
 Başlatma/kullanım `bstrAddressOffset` alanını `CONTEXT_INFO` yapısı.  
  
 CIF_ALLFIELDS  
 Başlat/tüm alanları kullanın `CONTEXT_INFO` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerleri parametre olarak geçirilen [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) hangi alanlarının belirtmek için yöntemi [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) yapısı başlatılması üzeresiniz.  
  
 Bu bayrakların Ayrıca hangi alanlarının belirtmek için kullanılan `CONTEXT_INFO` yapısı, kullanılan ve geçerli yapısı döndürülür.  
  
 Bu değerlerin Bitsel veya ile birleştirilebilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)