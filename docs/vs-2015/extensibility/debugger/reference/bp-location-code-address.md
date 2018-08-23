---
title: BP_LOCATION_CODE_ADDRESS | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- BP_LOCATION_CODE_ADDRESS
helpviewer_keywords:
- BP_LOCATION_CODE_ADDRESS structure
ms.assetid: 83c9da8b-19d9-4be5-b225-854543654901
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 76860054976ef0b2734871fb91e006a0b65e86fc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693052"
---
# <a name="bplocationcodeaddress"></a>BP_LOCATION_CODE_ADDRESS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [BP_LOCATION_CODE_ADDRESS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-location-code-address).  
  
Kodda bir adresteki bir kesme noktası konumu açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef struct _BP_LOCATION_CODE_ADDRESS {   
   BSTR bstrContext;  
   BSTR bstrModuleUrl;  
   BSTR bstrFunction;  
   BSTR bstrAddress;  
} BP_LOCATION_CODE_ADDRESS;  
```  
  
## <a name="members"></a>Üyeler  
 `bstrContext`  
 Kesme noktası bağlamında, genellikle de bir yöntem veya işlev adı olarak görülen bir çağrı yığınında.  
  
 `bstrModuleUrl`  
 Kesme noktasını içeren modül URL'si.  
  
 `bstrFunction`  
 Kesme noktasını içeren işlevi adı.  
  
 `bstrAddress`  
 Bağlamak için bir ifade değerlendiricisi tarafından ayrıştırılan kesme noktası adresini bir [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesidir [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) yapısı bir birleşimin parçası olarak.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)

