---
title: BP_LOCATION_CODE_FILE_LINE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_FILE_LINE
helpviewer_keywords:
- BP_LOCATION_CODE_FILE_LINE structure
ms.assetid: 3ff32032-d412-44d3-91bf-870cc354a09e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a37bbc808322c54d1e0c9354353de2f59b2e19af
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109022"
---
# <a name="bplocationcodefileline"></a>BP_LOCATION_CODE_FILE_LINE
Belirli bir kodu kaynak dosyası satırında bir kesme noktası konumu için verileri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _BP_LOCATION_CODE_FILE_LINE {   
   BSTR                     bstrContext;  
   IDebugDocumentPosition2* pDocPos;  
} BP_LOCATION_CODE_FILE_LINE;  
```  
  
## <a name="members"></a>Üyeler  
 `bstrContext`  
 Kesme noktası bağlamında, genellikle bir yöntemi veya işlev adı çağrı yığınında görülen olarak.  
  
 `pDocPos`  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) kesme belge konumunu temsil eden nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesi olan [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) yapısı UNION bir parçası olarak.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)