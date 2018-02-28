---
title: BP_LOCATION_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_LOCATION_TYPE
helpviewer_keywords:
- BP_LOCATION_TYPE structure
ms.assetid: 0248430a-3b61-4809-87a9-e9b6bb7d1130
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 919cef75834c6606cf4980b3a0e861302f29b73a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bplocationtype"></a>BP_LOCATION_TYPE
Kesme noktası bir kesme noktası isteği için konum türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
typedef DWORD BP_LOCATION_TYPE;  
```  
  
```csharp  
public enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
```  
  
## <a name="members"></a>Üyeler  
 BPLT_NONE  
 Kesme noktası konumu belirtir.  
  
 BPLT_FILE_LINE  
 Konum kesme noktası bir dosya satırı türünü belirtir.  
  
 BPLT_FUNC_OFFSET  
 Konum kesme noktası işlevi offset türünü belirtir.  
  
 BPLT_CONTEXT  
 Konum kesme noktası bir içerik türünü belirtir.  
  
 BPLT_STRING  
 Kesme noktası konum türü bir dize olarak belirtir.  
  
 BPLT_ADDRESS  
 Konum kesme noktası bir adres türünü belirtir.  
  
 BPLT_RESOLUTION  
 Konum kesme noktası bir çözüm türünü belirtir.  
  
 BPLT_CODE_FILE_LINE  
 Bir kaynak kodu satır kesme konum türünü belirtir.  
  
 BPLT_CODE_FUNC_OFFSET  
 Konum kesme noktası kodu işlevi offset türünü belirtir.  
  
 BPLT_CODE_CONTEXT  
 Konum kesme noktası kodu bağlamı olarak türünü belirtir.  
  
 BPLT_CODE_STRING  
 Kesme noktası konum türünü kod dize olarak belirtir.  
  
 BPLT_CODE_ADDRESS  
 Konum kesme noktası kodu adresi olarak türünü belirtir.  
  
 BPLT_DATA_STRING  
 Kesme noktası konum türünü verileri dize olarak belirtir.  
  
 BPLT_TYPE_MASK  
 Kesme noktası türü değeri dışında ayıklanabilir böylece bir bit maskesi belirtir.  
  
 BPLT_LOCATION_TYPE_MASK  
 Kesme noktası konum türü değeri dışında ayıklanabilir böylece bir bit maskesi belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir parametre olarak geçirilen [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md) yöntemi.  
  
 Kesme noktası konum türü bir kesme noktası türü ve konumu türü oluşur. Bu bir kesme noktası konum türü hiçbir zaman yalnızca bir kesme noktası türü olduğu anlamına gelir (örneğin, `BPT_CODE`) veya bir konum yazın (örneğin, `BPLT_FILE_LINE`). Bu numaralandırma şu anda desteklenen tüm kesme noktası konumu türleri için önceden tanımlanmış sabitleri dahil edilen (`BPLT_CODE_FILE_LINE` aracılığıyla `BPLT_DATA_STRING`).  
  
 `BPT_CODE`ve `BPT_DATA` üyeleri olan [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md) numaralandırması.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)   
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)