---
title: IDebugDefaultPort2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugDefaultPort2
helpviewer_keywords:
- IDebugDefaultPort2 interface
ms.assetid: 7b3452af-9a96-4c4c-9946-4339b72d3d7b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e2a388d25ec828eeedb5c86860ad697848a5cb77
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdefaultport2"></a>IDebugDefaultPort2
Bu arabirim, bir bağlantı noktasının sunucu ve bildirim tesis erişmek için çeşitli yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugDefaultPort2 : IDebugPort2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio erişim programları için hata ayıklama bağlantı noktası temsil etmek için bu arabirimi uygular. Uzaktan hata ayıklama işliyorsa özel bir bağlantı noktası tedarikçi da bu arabirimi uygulayabilirsiniz.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Yöntemlere bağımsız değişken [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) arabirimi bu arabirim sağlar. Çağırma [QueryInterface](/cpp/atl/queryinterface) üzerinde bir [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) arabirimi bu arabirimin de edinebilirsiniz.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 İçinde tanımlanan yöntemler yanı sıra [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md), aşağıdaki yöntemlerden bu arabirimi uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)|Bağlantı noktası bildirim arabirimi Bu bağlantı noktasından alır.|  
|[GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)|Bu bağlantı noktasını barındıran sunucuya arabirimi alır.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugdefaultport2-queryislocal.md)|Bu bağlantı noktasını yerel makinede çalışıp çalışmadığını belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Adı "`IDebugDefaultPort2`" varsayılan bir bağlantı noktası göstermiyor biraz bir misnomer aynıdır. "IDebugPort3." çağrılabilir  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)