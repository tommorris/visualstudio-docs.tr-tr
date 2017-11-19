---
title: IDebugProcessEx2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcessEx2
helpviewer_keywords: IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 45ef0413540729abb67caad992a557c5b4692dfe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
Bu arabirim, hata ayıklama Yöneticisi (SDM) bildirmek için ekleme veya işleminden ayırma işlemi oturum sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProcessEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bir bağlantı noktası sağlayıcı aynı nesne üzerinde bu arabirimi uygulayan [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) için arabirim:  
  
-   Bir işleme bağlı oturumlar destek izleme  
  
-   Hata ayıklama altyapıları destek otomatik-ekleme  
  
 Bunu seçerse, özel bir bağlantı noktası tedarikçi bu arabirimi uygulayabilirsiniz.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
  
-   SDM çağrıları [QueryInterface](/cpp/atl/queryinterface) üzerinde bir `IDebugProcess2` bu arabirimi sağlamak için arabirim.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugProcessEx2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Ekleme](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|İşlem, bir oturum işlemi artık hata ayıklama bildirir.|  
|[Ayırma](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|İşlem, bir oturum işlemi artık hata ayıklamayı bildirir.|  
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|Hata ayıklama motorları listesi için program düğümleri ekler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem SDM arasında özel bir arabirimdir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)