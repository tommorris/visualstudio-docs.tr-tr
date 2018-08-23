---
title: IDebugEvent2 | Microsoft Docs
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
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7fc387733e1472afe5f21f5e0638374ebda9f677
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694672"
---
# <a name="idebugevent2"></a>IDebugEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugevent2).  
  
Bu arabirim, bir kesme noktasında durdurma gibi kritik hata ayıklama bilgileri hem hata ayıklama iletisi gibi kritik olmayan bilgileri iletişim kurmak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bağlantı noktası sağlayıcısı ve hata ayıklama altyapısı (DE) tüm olay arabirimleri olarak aynı nesne üzerinde bu arabirimi uygulayın.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 ' % S'arabirimi için verilen Kimliğini (IID) bağımsız değişkeni kullanarak [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) veya [olay](../../../extensibility/debugger/reference/idebugportevents2-event.md), oturum hata ayıklama Yöneticisi (SDM) çağırır [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) üzerinde `IDebugEvent2` almak için arabirimi uygun olay arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugEvent2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|Bu hata ayıklama olayı özniteliklerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Gibi daha belirli olay arabirimleri [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), IDebugEvent2 arabirimden türetilmiş değil ancak bunun yerine ayrı bir arabirimi aynı nesne üzerinde uygulanan `IDebugEvent2`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Olay](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)

