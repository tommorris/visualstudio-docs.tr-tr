---
title: IDebugOutputStringEvent2 | Microsoft Docs
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
- IDebugOutputStringEvent2
helpviewer_keywords:
- IDebugOutputStringEvent2 interface
ms.assetid: 86596fd1-cecc-4813-8add-dc3d70068f9b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cceb929a7f75420e1b93f15d653a48c1e112798e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693444"
---
# <a name="idebugoutputstringevent2"></a>IDebugOutputStringEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugOutputStringEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugoutputstringevent2).  
  
Bu arabirim hata ayıklama altyapısı (DE) tarafından bir dize çıktısı için oturum hata ayıklama Yöneticisi (SDM) gönderilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugOutputStringEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 DE bir dizeye göndermek için bu arabirimi uygulayan **çıkış** IDE bir pencerenin. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) arabirim uygulandığında, bu arabirimle aynı nesne üzerinde. SDM kullanan [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) erişimi `IDebugEvent2` arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 KODU oluşturur ve bu olay göndermek için bir dize nesnesine gönderir **çıkış** penceresi. Olay kullanılarak gönderilen [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) ayıklanan programa eklendiğinde SDM tarafından sağlanan geri çağırma işlevi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Yöntemini aşağıdaki tabloda gösterilmektedir `IDebugOutputStringEvent2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetString](../../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)|Annotatable iletisini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, bir dize için Win32 hata ayıklanan programa gönderdiğinde yönetilmeyen kodda çıkış dize gönderilebilir `OutputDebugString` işlevi. Bu dize DE tarafından kesildi ve SDM gönderilen `IDebugOutputStringEvent2` olay.  
  
 Kullanım [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md) kullanıcı yanıt isteyen bir ileti göndermek için.  
  
 Kullanım [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) yanıt gerektirmeyen bir hata iletisi göndermek için.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)

