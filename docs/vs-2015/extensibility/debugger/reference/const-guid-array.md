---
title: CONST_GUID_ARRAY | Microsoft Docs
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
- CONST_GUID_ARRAY
helpviewer_keywords:
- CONST_GUID_ARRAY structure
ms.assetid: bd55e7d8-372c-4c3e-9eed-28f6b415a5db
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73bf618000deba98523918003214717f77a6a360
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688881"
---
# <a name="constguidarray"></a>CONST_GUID_ARRAY
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CONST_GUID_ARRAY](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/const-guid-array).  
  
Bir listesini tutan bir yapı `GUID`s.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef struct tagCONST_GUID_ARRAY {  
   DWORD       dwCount;  
   CONST GUID* Members;  
} CONST_GUID_ARRAY;  
```  
  
```csharp  
public struct CONST_GUID_ARRAY {  
   public uint   dwCount;  
   public Guid[] Members;  
}  
```  
  
## <a name="members"></a>Üyeler  
 dwCount  
 Sayısı `GUID`s'te `Members` dizisi.  
  
 Üyeler  
 Dizi `GUID`s.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md) yöntemi ve öğesinden döndürülen [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) ve [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md) yöntemleri.  
  
 Bu yapının bir örneğinin sahibi, ayrılan belleği serbest bırakma için sorumludur.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)   
 [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)

