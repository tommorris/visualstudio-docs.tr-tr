---
title: BPREQI_FIELDS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPREQI_FIELDS90 enumeration
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1988bbe5262bc6a4807a6068adf45f381ccf4296
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bpreqifields90"></a>BPREQI_FIELDS90
Alınacak bir kesme noktası isteği bilgilerini belirtmek geçerli değerlerini sıralar. Bu numaralandırma genişletir [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) numaralandırması.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BPREQI_FIELDS90  
{  
   // VS 8.0 values  
   BPREQI90_BPLOCATION                = 0x0001,  
   BPREQI90_LANGUAGE                  = 0x0002,  
   BPREQI90_PROGRAM                   = 0x0004,  
   BPREQI90_PROGRAMNAME               = 0x0008,  
   BPREQI90_THREAD                    = 0x0010,  
   BPREQI90_THREADNAME                = 0x0020,  
   BPREQI90_PASSCOUNT                 = 0x0040,  
   BPREQI90_CONDITION                 = 0x0080,  
   BPREQI90_FLAGS                     = 0x0100,  
   BPREQI90_ALLOLDFIELDS              = 0x01ff,  
   BPREQI90_VENDOR                    = 0x0200,  
   BPREQI90_CONSTRAINT                = 0x0400,  
   BPREQI90_TRACEPOINT                = 0x0800,  
  
   // Values added in VS 9.0  
   BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
   BPREQI90_ALLFIELDS                 = 0xffff  
};  
typedef DWORD BPREQI_FIELDS90;  
```  
  
```csharp  
public enum enum_BPREQI_FIELDS90  
{  
    // VS 8.0 values  
    BPREQI90_BPLOCATION                = 0x0001,  
    BPREQI90_LANGUAGE                  = 0x0002,  
    BPREQI90_PROGRAM                   = 0x0004,  
    BPREQI90_PROGRAMNAME               = 0x0008,  
    BPREQI90_THREAD                    = 0x0010,  
    BPREQI90_THREADNAME                = 0x0020,  
    BPREQI90_PASSCOUNT                 = 0x0040,  
    BPREQI90_CONDITION                 = 0x0080,  
    BPREQI90_FLAGS                     = 0x0100,  
    BPREQI90_ALLOLDFIELDS              = 0x01ff,  
    BPREQI90_VENDOR                    = 0x0200,  
    BPREQI90_CONSTRAINT                = 0x0400,  
    BPREQI90_TRACEPOINT                = 0x0800,  
  
    // Values added in VS 9.0  
    BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
    BPREQI90_ALLFIELDS                 = 0xffff  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 BPREQI90_BPLOCATION  
 Başlatması veya kullanmak `bpLocation` (kesme noktası konum) alanı [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) veya [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapısı.  
  
 BPREQI90_LANGUAGE  
 Başlatması veya kullanmak `guidLanguage` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_PROGRAM  
 Başlatması veya kullanmak `pProgram` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_PROGRAMNAME  
 Başlatması veya kullanmak `bstrProgramName` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_THREAD  
 Başlatması veya kullanmak `pThread` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_THREADNAME  
 Başlatması veya kullanmak `bstrThreadName` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_PASSCOUNT  
 Başlatması veya kullanmak `bpPassCount` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_CONDITION  
 Başlatması veya kullanmak `bpCondition` (kesme noktası koşul) alanı `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_FLAGS  
 Başlatması veya kullanmak `dwFlags` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_ALLOLDFIELDS  
 Başlatması veya tüm alanlar için kullanmak, `BP_REQUEST_INFO` yapısı.  
  
 BPREQI90_VENDOR  
 Başlatması veya kullanmak `guidVendor` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_CONSTRAINT  
 Başlatması veya kullanmak `bstrConstraint` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_TRACEPOINT  
 Başlatması veya kullanmak `bstrTracepoint` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_MACROTRACEPOINT  
 Başlatması veya kullanmak `bstrMacroTracepoint` alanını `BP_REQUEST_INFO2` yapısı. Bu alan BPREQI_ALLFIELDS içermez.  
  
 BPREQI90_ALLFIELDS  
 Tüm alanlar için belirtir `BP_REQUEST_INFO2` yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit Listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)