---
title: BPREQI_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BPREQI_FIELDS
helpviewer_keywords:
- BPREQI_FIELDS enumeration
ms.assetid: 679e771e-4a79-484e-af37-f962ef4aa245
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1e7c0206ca5834b281447e9a00c4ce3cad0c247c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bpreqifields"></a>BPREQI_FIELDS
İlgili bir kesme noktası istek alınması için bilgileri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BPREQI_FIELDS {   
   BPREQI_BPLOCATION   = 0x0001,  
   BPREQI_LANGUAGE     = 0x0002,  
   BPREQI_PROGRAM      = 0x0004,  
   BPREQI_PROGRAMNAME  = 0x0008,  
   BPREQI_THREAD       = 0x0010,  
   BPREQI_THREADNAME   = 0x0020,  
   BPREQI_PASSCOUNT    = 0x0040,  
   BPREQI_CONDITION    = 0x0080,  
   BPREQI_FLAGS        = 0x0100,  
   BPREQI_ALLOLDFIELDS = 0x01ff  
   BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only  
   BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only  
   BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only  
   BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only  
};  
typedef DWORD BPREQI_FIELDS;  
```  
  
```csharp  
public enum enum_BPREQI_FIELDS {   
   BPREQI_BPLOCATION   = 0x0001,  
   BPREQI_LANGUAGE     = 0x0002,  
   BPREQI_PROGRAM      = 0x0004,  
   BPREQI_PROGRAMNAME  = 0x0008,  
   BPREQI_THREAD       = 0x0010,  
   BPREQI_THREADNAME   = 0x0020,  
   BPREQI_PASSCOUNT    = 0x0040,  
   BPREQI_CONDITION    = 0x0080,  
   BPREQI_FLAGS        = 0x0100,  
   BPREQI_ALLOLDFIELDS = 0x01ff  
   BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only  
   BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only  
   BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only  
   BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only  
};  
```  
  
## <a name="members"></a>Üyeler  
 BPREQI_BPLOCATION  
 Başlatma/kullanım `bpLocation` (kesme noktası konum) alanı [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) veya [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapısı.  
  
 BPREQI_LANGUAGE  
 Başlatma/kullanım `guidLanguage` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_PROGRAM  
 Başlatma/kullanım `pProgram` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_PROGRAMNAME  
 Başlatma/kullanım `bstrProgramName` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_THREAD  
 Başlatma/kullanım `pThread` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_THREADNAME  
 Başlatma/kullanım `bstrThreadName` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_PASSCOUNT  
 Başlatma/kullanım `bpPassCount` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_CONDITION  
 Başlatma/kullanım `bpCondition` (kesme noktası koşul) alanı `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_FLAGS  
 Başlatma/kullanım `dwFlags` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_ALLOLDFIELDS  
 Tüm alanlar için başlatma/kullanın, `BP_REQUEST_INFO` yapısı.  
  
 BPREQI_VENDOR  
 Başlatma/kullanım `guidVendor` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_CONSTRAINT  
 Başlatma/kullanım `bstrConstraint` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_TRACEPOINT  
 Başlatma/kullanım `bstrTracepoint` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI_ALLFIELDS  
 Tüm alanlar için belirtir `BP_REQUEST_INFO2` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) ve [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) hangi alanlarının belirtmek için yöntemleri [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) ve [BP_REQUEST_INFO2 ](../../../extensibility/debugger/reference/bp-request-info2.md) yapıları başlatılması üzeresiniz.  
  
 Bu bayrakların Ayrıca hangi alanlarının belirtmek için kullanılan `BP_REQUEST_INFO` ve `BP_REQUEST_INFO2` yapıları, kullanılan ve geçerli her yapısı döndürülür.  
  
 Bu değerlerin Bitsel ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)