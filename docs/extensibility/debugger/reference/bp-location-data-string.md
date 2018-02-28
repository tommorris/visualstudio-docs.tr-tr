---
title: BP_LOCATION_DATA_STRING | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_LOCATION_DATA_STRING
helpviewer_keywords:
- BP_LOCATION_DATA_STRING structure
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 98be0e0eec66d1829569f88b38f710ddc616be85
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bplocationdatastring"></a>BP_LOCATION_DATA_STRING
Kullanıcı tümleşik geliştirme ortamı (IDE) girebilirsiniz bir dize temel alan veri kesme noktaları ayarlamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _BP_LOCATION_DATA_STRING {   
   IDebugThread2* pThread;  
   BSTR           bstrContext;  
   BSTR           bstrDataExpr;  
   DWORD          dwNumElements;  
} BP_LOCATION_DATA_STRING;  
```  
  
## <a name="members"></a>Üyeler  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) kesme oluştuğu iş parçacığı temsil eden nesne.  
  
 `bstrContext`  
 Kod içinde kesme, genellikle bir yöntemi veya işlev adı olarak görülen bir çağrı yığınında bağlamı.  
  
 `bstrDataExpr`  
 Kesme noktası ayarlamak için kullanıcı veri dizesi girer.  
  
 `dwNumElements`  
 Kesme noktası oluştuğu veri dizesi öğe sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı üyesi olan [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) yapısı UNION bir parçası olarak.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)