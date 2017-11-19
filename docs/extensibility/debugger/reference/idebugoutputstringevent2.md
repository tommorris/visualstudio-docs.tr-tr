---
title: IDebugOutputStringEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugOutputStringEvent2
helpviewer_keywords: IDebugOutputStringEvent2 interface
ms.assetid: 86596fd1-cecc-4813-8add-dc3d70068f9b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 18c8443ad5f609a3c31e867fa88e4621471aeec2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugoutputstringevent2"></a>IDebugOutputStringEvent2
Bu arabirim (DE) hata ayıklama altyapısı tarafından bir dize çıktısını almak için oturum hata ayıklama Yöneticisi (SDM) gönderilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugOutputStringEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 DE bir dizeye göndermek için bu arabirimi uygulayan **çıkış** IDE penceresi. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) arabirimi uygulanan, bu arabirimle aynı nesne üzerinde. SDM kullanan [QueryInterface](/cpp/atl/queryinterface) erişimi `IDebugEvent2` arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Aygıtların oluşturur ve bir dizeye göndermek için bu olay nesnesi gönderir **çıkış** penceresi. Olay kullanılarak gönderilen [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) ayıklanacak programın eklendiğinde, SDM tarafından sağlanan geri çağırma işlevi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Yöntemini aşağıdaki tabloda gösterilmektedir `IDebugOutputStringEvent2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetString](../../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)|Görüntülenebilecek iletisini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayıklanacak program Win32'ye bir dize gönderdiğinde yönetilmeyen kodunda çıktı dize örneğin kaynaklanan `OutputDebugString` işlevi. Bu dize DE tarafından müdahale ve SDM gönderilen `IDebugOutputStringEvent2` olay.  
  
 Kullanım [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md) kullanıcı yanıt isteyen bir ileti göndermek için.  
  
 Kullanım [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) yanıt gerektirmeyen bir hata iletisi göndermek için.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)