---
title: IDebugCoreServer3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCoreServer3
helpviewer_keywords:
- IDebugCoreServer3 interface
ms.assetid: 51f5f41b-a5a4-4df0-a703-41f3d1811d7f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9456ddbe7588217e4864f6f8c8b994bc9323ab76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver3"></a>IDebugCoreServer3
Bu arabirim işlemin çalıştığı sunucu hakkındaki bilgileri erişmenizi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugCoreServer3 : IDebugCoreServer2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Kullanım [QueryInterface](/cpp/atl/queryinterface) bu arabirimden elde etmek için bir [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) arabirimi. Çağrı [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) da bu arabirimi dönebilirsiniz. Bu arabirim, programlar bir sunucuda (yerel veya uzak) başlatmak için özel bir bağlantı noktası tedarikçi tarafından en sık kullanılır.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Yöntemlere ek olarak [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) arabirimi, bu arabirimi uygulayan aşağıdaki yöntemleri:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)|Sunucunun adını alır.|  
|[GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)|Sunucu adının kullanıcı dostu bir sürümü alır.|  
|[EnableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-enableautoattach.md)|Bu işlemleri başlattığınızda işlemleri otomatik olarak eklemek için belirli hata ayıklama motorları söyler.|  
|[DiagnoseWebDebuggingError](../../../extensibility/debugger/reference/idebugcoreserver3-diagnosewebdebuggingerror.md)|Otomatik ekleme başarısız olduğunda bir özel hata kodu alır.|  
|[CreateInstanceInServer](../../../extensibility/debugger/reference/idebugcoreserver3-createinstanceinserver.md)|Sunucuda bir hata ayıklama altyapısı örneği oluşturur.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugcoreserver3-queryislocal.md)|Sunucusu çağıran ile aynı makinede olup olmadığını belirten bir bayrak alır.|  
|[GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)|Sunucu ile iletişim kurmak için kullanılan protokol belirten bir değer alır.|  
|[DisableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-disableautoattach.md)|Tüm devre dışı bırakır otomatik-bu sunucu bildiği tüm hata ayıklama altyapılar ayarlarını ekleyin.|  
  
## <a name="remarks"></a>Açıklamalar  
 Özel bir bağlantı noktası tedarikçi alır [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) yapılan bir çağrı arabirimde [olay](../../../extensibility/debugger/reference/idebugportevents2-event.md). `IDebugCoreServer3` Arabirimi arabirimden elde edilebilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)