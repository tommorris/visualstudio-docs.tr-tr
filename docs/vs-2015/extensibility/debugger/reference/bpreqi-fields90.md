---
title: BPREQI_FIELDS90 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPREQI_FIELDS90 enumeration
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5ddba39cc7a540c1c88997c09fd864dd8c22464f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693707"
---
# <a name="bpreqifields90"></a>BPREQI_FIELDS90
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [BPREQI_FIELDS90](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bpreqi-fields90).  
  
Alınacak bir kesme noktası isteği bilgilerini belirtin. geçerli değerler numaralandırır. Bu numaralandırma genişletir [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) sabit listesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Başlatma veya kullanın `bpLocation` (kesme noktası konumu) alanının [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) veya [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapısı.  
  
 BPREQI90_LANGUAGE  
 Başlatma veya kullanın `guidLanguage` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_PROGRAM  
 Başlatma veya kullanın `pProgram` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_PROGRAMNAME  
 Başlatma veya kullanın `bstrProgramName` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_THREAD  
 Başlatma veya kullanın `pThread` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_THREADNAME  
 Başlatma veya kullanın `bstrThreadName` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_PASSCOUNT  
 Başlatma veya kullanın `bpPassCount` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_CONDITION  
 Başlatma veya kullanın `bpCondition` (kesme noktası koşulu) alanının `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_FLAGS  
 Başlatma veya kullanın `dwFlags` alanını `BP_REQUEST_INFO` veya `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_ALLOLDFIELDS  
 Başlatma veya tüm alanlar için kullanın, `BP_REQUEST_INFO` yapısı.  
  
 BPREQI90_VENDOR  
 Başlatma veya kullanın `guidVendor` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_CONSTRAINT  
 Başlatma veya kullanın `bstrConstraint` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_TRACEPOINT  
 Başlatma veya kullanın `bstrTracepoint` alanını `BP_REQUEST_INFO2` yapısı.  
  
 BPREQI90_MACROTRACEPOINT  
 Başlatma veya kullanın `bstrMacroTracepoint` alanını `BP_REQUEST_INFO2` yapısı. Bu alan BPREQI_ALLFIELDS içermez.  
  
 BPREQI90_ALLFIELDS  
 Tüm alanlar için belirtir `BP_REQUEST_INFO2` yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit Listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)

