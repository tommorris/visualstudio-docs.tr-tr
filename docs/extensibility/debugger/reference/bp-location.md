---
title: BP_LOCATION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_LOCATION
helpviewer_keywords:
- BP_LOCATION union
ms.assetid: ed1e874c-f289-4c31-8b6c-04dde03ad0f5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b73a625e21da8e8ba026df140e437e96bdeb1ff5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107026"
---
# <a name="bplocation"></a>BP_LOCATION
Kesme noktası konumunu tanımlamak için kullanılan yapısı türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _BP_LOCATION {  
   BP_LOCATION_TYPE bpLocationType;  
   union {  
      BP_LOCATION_CODE_FILE_LINE   bplocCodeFileLine;  
      BP_LOCATION_CODE_FUNC_OFFSET bplocCodeFuncOffset;  
      BP_LOCATION_CODE_CONTEXT     bplocCodeContext;  
      BP_LOCATION_CODE_STRING      bplocCodeString;  
      BP_LOCATION_CODE_ADDRESS     bplocCodeAddress;  
      BP_LOCATION_DATA_STRING      bplocDataString;  
      BP_LOCATION_RESOLUTION       bplocResolution;  
      DWORD                        unused;  
   } bpLocation;  
} BP_LOCATION;  
```  
  
```csharp  
public struct BP_LOCATION {  
   public uint   bpLocationType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public IntPtr unionmember4;  
};  
```  
  
## <a name="members"></a>Üyeler  
 `bpLocationType`  
 Arasında bir değer [BP_LOCATION_TYPE](../../../extensibility/debugger/reference/bp-location-type.md) bilgilerini yorumlamak için kullanılacak numaralandırma `bpLocation` Birliği veya `unionmemberX` üyeleri.  
  
 `bpLocation`.`bplocCodeFileLine`  
 [Yalnızca C++] İçeren [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) , yapı `bpLocationType`  =  `BPLT_CODE_FILE_LINE`.  
  
 `bpLocation.bplocCodeFuncOffset`  
 [Yalnızca C++] İçeren [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) , yapı `bpLocationType`  =  `BPLT_CODE_FUNC_OFFSET`.  
  
 `bpLocation.bplocCodeContext`  
 [Yalnızca C++] İçeren [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md) , yapı `bpLocationType`  =  `BPLT_CODE_CONTEXT`.  
  
 `bpLocation.bplocCodeString`  
 [Yalnızca C++] İçeren [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md) , yapı `bpLocationType`  =  `BPLT_CODE_STRING`.  
  
 `bpLocation.bplocCodeAddress`  
 [Yalnızca C++] İçeren [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md) , yapı `bpLocationType`  =  `BPLT_CODE_ADDRESS`.  
  
 `bpLocation.bplocDataString`  
 [Yalnızca C++] İçeren [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md) , yapı `bpLocationType`  =  `BPLT_DATA_STRING`.  
  
 `bpLocation.bplocResolution`  
 [Yalnızca C++] İçeren [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md) , yapı `bpLocationType`  =  `BPLT_RESOLUTION`.  
  
 `unionmember1`  
 [Sadece C#] Yorumlama ilgili açıklamalar bakın.  
  
 `unionmember2`  
 [Sadece C#] Yorumlama ilgili açıklamalar bakın.  
  
 `unionmember3`  
 [Sadece C#] Yorumlama ilgili açıklamalar bakın.  
  
 `unionmember4`  
 [Sadece C#] Yorumlama ilgili açıklamalar bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesi olan [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) ve [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapıları.  
  
 [Sadece C#] `unionmemberX` Üyeleri aşağıdaki tabloya göre yorumlanır. Sol sütunda için aşağıya bakın `bpLocationType` değer sonra her belirlemek için diğer sütunları arasında ara `unionmemberX` üye temsil eder ve sıralama `unionmemberX` uygun şekilde. C# bu yapısının parçası yorumlamak için bir yol örneğine bakın.  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPLT_CODE_FILE_LINE`|`string` (bir bağlam)|[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)|-|-|  
|`BPLT_CODE_FUNC_OFFSET`|`string` (bir bağlam)|[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)|-|-|  
|`BPLT_CODE_CONTEXT`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|  
|`BPLT_CODE_STRING`|`string` (bir bağlam)|`string` (koşullu ifade)|-|-|  
|`BPLT_CODE_ADDRESS`|`string` (bir bağlam)|`string` (modülü URL)|`string` (işlev adı)|`string` (adres)|  
|`BPLT_DATA_STRING`|[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)|`string` (bir bağlam)|`string` (veri ifade)|`uint` (öğe sayısı)|  
|`BPLT_RESOLUTION`|[IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)|-|-|-|  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl yorumlanacağını gösterir `BP_LOCATION` yapısını C# için `BPLT_DATA_STRING` türü. Bu türdeki tüm dört yorumlama gösterir `unionmemberX` tüm olası biçimleri (nesne, dize ve numarası) üyeleri.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(BP_LOCATION bp)  
        {  
            if (bp.bpLocationType == (uint)enum_BP_LOCATION_TYPE.BPLT_DATA_STRING)  
            {  
                 IDebugThread2 pThread = (IDebugThread2)Marshal.GetObjectForIUnknown(bp.unionmember1);  
                 string context = Marshal.PtrToStringBSTR(bp.unionmember2);  
                 string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 uint numElements = (uint)Marshal.ReadInt32(bp.unionmember4);  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md)   
 [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md)   
 [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md)   
 [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md)   
 [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md)