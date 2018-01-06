---
title: IDebugPortRequest2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortRequest2
helpviewer_keywords: IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5b47a9bde47049c957af9f60e1d09d03b55c2359
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
Bu arabirim, bir bağlantı noktası açıklar. Bu açıklama, bir bağlantı noktası sağlayıcı bağlantı noktası eklemek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio genellikle bir hata ayıklama bağlantı noktası listesinden bir bağlantı noktası tedarikçi alma işleminde bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim uygulamasına geçirilen [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) hata ayıklama bağlantı noktası oluşturulamadı. Çağrı [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md) bağlantı noktası ilk başta oluşturmak için kullanılan istek temsil eden bu arabirimini döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugPortRequest2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|Oluşturmak istediğiniz bağlantı noktasının adını alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı genellikle bir bağlantı noktası tedarikçi ile etkileşime girmez ve bu arabirim için hiçbir kullanıma sahip olur.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)