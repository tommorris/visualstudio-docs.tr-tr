---
title: BPERESI_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2280740766e20a048f57e58590cc529d98b85264
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31110061"
---
# <a name="bperesifields"></a>BPERESI_FIELDS
Başarısız bir kesme noktası çözümleme hakkında alınması için bilgileri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD BPERESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 PERESI_BPRESLOCATION  
 Başlatma/kullanım `bpResLocation` (kesme noktası çözümleme konum) alanı [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) yapısı.  
  
 BPERESI_PROGRAM  
 Başlatma/kullanım `pProgram` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_THREAD  
 Başlatma/kullanım `pThread` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_MESSAGE  
 Başlatma/kullanım `bstrMessage` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_TYPE  
 Başlatma/kullanım `dwType` (kesme noktası türü) alanı `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_ALLFIELDS  
 Başlat/tüm alanları kullanın `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir parametre olarak geçirilen [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md) hangi alanlarının belirtmek için yöntemi [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) yapısı başlatılması üzeresiniz.  
  
 Bu değerleri ayrıca hangi alanları belirtmek için kullanılan `BP_ERROR_RESOLUTION_INFO` yapısı, kullanılan ve geçerli yapıyı döndürülür.  
  
 Bu değerlerin Bitsel ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)