---
title: IDebugPortRequest2 | Microsoft Docs
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
- IDebugPortRequest2
helpviewer_keywords:
- IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7873d3d73556bae671cc1150525eb3d08a136e27
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695336"
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugPortRequest2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportrequest2).  
  
Bu arabirim bir bağlantı noktası açıklar. Bu açıklama, bağlantı noktası için bağlantı noktası sağlayıcısı eklemek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio, genellikle hata ayıklama bağlantı noktası bağlantı noktası sağlayıcısı alma işleminde bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim yöntemlere geçirilen [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) hata ayıklama bağlantı oluşturmak için. Bir çağrı [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md) ilk başta bağlantı noktası oluşturmak için kullanılan istek temsil eden bu arabirimi döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugPortRequest2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|Oluşturmak için bağlantı noktası adını alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı genellikle bağlantı noktası sağlayıcısı ile etkileşime girmez ve bu arabirim için herhangi bir kullanıma sahip olur.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)

