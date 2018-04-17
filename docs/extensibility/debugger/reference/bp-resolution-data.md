---
title: BP_RESOLUTION_DATA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_RESOLUTION_DATA
helpviewer_keywords:
- BP_RESOLUTION_DATA structure
ms.assetid: 9e0b9000-6a84-47b9-b07a-367a75764389
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f76cba8fa2b1ea01a2cbd7670a05b449d476127b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="bpresolutiondata"></a>BP_RESOLUTION_DATA
Veri kesme noktası bağlamanın sonucunu açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _BP_RESOLUTION_DATA {   
   BSTR              bstrDataExpr;  
   BSTR              bstrFunc;  
   BSTR              bstrImage;  
   BP_RES_DATA_FLAGS dwFlags;  
} BP_RESOLUTION_DATA;  
```  
  
```csharp  
public struct BP_RESOLUTION_DATA {   
   public string bstrDataExpr;  
   public string bstrFunc;  
   public string bstrImage;  
   public uint   dwFlags;  
};  
```  
  
## <a name="members"></a>Üyeler  
 `bstrDataExpr`  
 Bağlı veri ifade.  
  
 `bstrFunc`  
 İşlevin adını veri kesme noktası (varsa) bağlanan.  
  
 `bstrImage`  
 Veri kesme noktası bağlanan Modülü (örneğin, MyModule.dll) adı.  
  
 `dwFlags`  
 Arasında bir değer [BP_RES_DATA_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md) veri kesme noktası nasıl uygulandığını açıklayan numaralandırması.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesi olan [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md) üyesi kapatma yapısı [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) tarafından döndürülen yapısı [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)