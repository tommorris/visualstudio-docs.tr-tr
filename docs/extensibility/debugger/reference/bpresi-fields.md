---
title: BPRESI_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BPRESI_FIELDS
helpviewer_keywords:
- BPRESI_FIELDS enumeration
ms.assetid: 99f17b1e-3e67-4f85-89d6-5c6cf45c8008
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1b6ecfd729762944bcf26814e735c4c73841e2d0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101699"
---
# <a name="bpresifields"></a>BPRESI_FIELDS
Başarılı bir kesme noktası çözümleme hakkında alınması için bilgileri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BPRESI_FIELDS {   
   BPRESI_BPRESLOCATION = 0x0001,  
   BPRESI_PROGRAM       = 0x0002,  
   BPRESI_THREAD        = 0x0004,  
   BPRESI_ALLFIELDS     = 0xffffffff  
};  
typedef DWORD BPRESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPRESI_FIELDS {   
   BPRESI_BPRESLOCATION = 0x0001,  
   BPRESI_PROGRAM       = 0x0002,  
   BPRESI_THREAD        = 0x0004,  
   BPRESI_ALLFIELDS     = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 BPRESI_BPRESLOCATION  
 Başlatma/kullanım `bpResLocation` (kesme noktası çözümleme konum) alanı [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) yapısı.  
  
 BPRESI_PROGRAM  
 Başlatma/kullanım `pProgram` alanını `BP_RESOLUTION_INFO` yapısı.  
  
 BPRESI_THREAD  
 Başlatma/kullanım `pThread` alanını `BP_RESOLUTION_INFO` yapısı.  
  
 BPRESI_ALLFIELDS  
 Tüm alanlar belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçirilen [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) hangi alanlarının belirtmek için yöntemi [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) yapısı başlatılması üzeresiniz.  
  
 Bu bayrakların Ayrıca hangi alanlarının belirtmek için kullanılan `BP_RESOLUTION_INFO` yapısı, kullanılan ve geçerli yapıyı döndürülür.  
  
 Bu değerlerin Bitsel ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)