---
title: BP_RESOLUTION_LOCATION | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_RESOLUTION_LOCATION
helpviewer_keywords: BP_RESOLUTION_LOCATION structure
ms.assetid: 21dc5246-69c1-43e3-855c-9cd4e596c0e6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a85c6c097867aea17be4b4aeca1431a05c74903a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bpresolutionlocation"></a>BP_RESOLUTION_LOCATION
Kesme noktası çözümleme konum yapısını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
struct _BP_RESOLUTION_LOCATION {  
   BP_TYPE bpType;  
   union {  
      BP_RESOLUTION_CODE bpresCode;  
      BP_RESOLUTION_DATA bpresData;  
      int                unused;  
   } bpResLocation;  
} BP_RESOLUTION_LOCATION;  
```  
  
```csharp  
public struct BP_RESOLUTION_LOCATION {  
   public uint bpType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public uint   unionmember4;  
};  
```  
  
## <a name="members"></a>Üyeler  
 `bpType`  
 Arasında bir değer [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md) yorumlama belirten numaralandırma `bpResLocation` Birliği veya `unionmemberX` üyeleri.  
  
 `bpResLocation.bpresCode`  
 [Yalnızca C++] İçeren [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md) , yapı `bpType`  =  `BPT_CODE`.  
  
 `bpResLocation.bpresData`  
 [Yalnızca C++] İçeren [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) , yapı `bpType`  =  `BPT_DATA`.  
  
 `bpResLocation.unused`  
 [Yalnızca C++] Yer tutucu.  
  
 `unionmember1`  
 [Sadece C#] Yorumlama ilgili açıklamalar bakın.  
  
 `unionmember2`  
 [Sadece C#] Yorumlama ilgili açıklamalar bakın.  
  
 `unionmember3`  
 [Sadece C#] Yorumlama ilgili açıklamalar bakın.  
  
 `unionmember4`  
 [Sadece C#] Yorumlama ilgili açıklamalar bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesi olan [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) ve [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) yapıları.  
  
 [Sadece C#] `unionmemberX` Üyeleri aşağıdaki tabloya göre yorumlanır. Sol sütunda için aşağıya bakın `bpType` her belirlemek için çapraz değer `unionmemberX` üye temsil eder ve sıralama `unionmemberX` uygun şekilde. Bu yapı C# yorumlamak için bir yol örneğine bakın.  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPT_CODE`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|  
|`BPT_DATA`|`string`(veri ifade)|`string`(işlev adı)|`string`(görüntü adı)|`enum_BP_RES_DATA_FLAGS`|  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl yorumlanacağını gösterir `BP_RESOLUTION_LOCATION` C# yapısı.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(BP_RESOLUTION_LOCATION bprl)  
        {  
            if (bprl.bpType == (uint)enum_BP_TYPE.BPT_CODE)  
            {  
                 IDebugCodeContext2 pContext = (IDebugCodeContext2)Marshal.GetObjectForIUnknown(bp.unionmember1);  
            }  
            else if (bprl.bpType == (uint)enum_BP_TYPE.BPT_DATA)  
            {  
                 string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 string functionName = Marshal.PtrToStringBSTR(bp.unionmember2);  
                 string imageName = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 enum_BP_RES_DATA_FLAGS numElements = (enum_BP_RES_DATA_FLAGS)bp.unionmember4;  
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
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md)   
 [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)   
 [BP_RES_DATA_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md)