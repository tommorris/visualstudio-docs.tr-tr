---
title: IDebugPortEvents2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortEvents2
helpviewer_keywords:
- IDebugPortEvents2 interface
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
caps.latest.revision: 18
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0a5782f0a50ac37b45c4b7e3402bcdded96b4683
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="idebugportevents2"></a>IDebugPortEvents2
Bu arabirim, işlem ve program oluşturma ve yok etme belirli bir bağlantı noktası dinleyicisi (genellikle oturum hata ayıklama Yöneticisi [SDM] veya bir hata ayıklama altyapısı) bildirir. Bu bilgiler bağlantı noktası üzerinde çalışan programları ve işlemleri gerçek zamanlı bir görünümünü sunmak için kullanılabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugPortEvents2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio genellikle program oluşturma ve yok etme hakkında bildirim almak için bu arabirimi uygular. Hata ayıklama altyapısı da bu tür bağlantı noktası olaylarını dinleyecek şekilde bu arabirimi uygulayabilirsiniz.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Tüm [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) arabirimleri seçmeleri için bir <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> arabirimi. Ardından <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.FindConnectionPoint%2A> yöntemi `IDebugPortEvents2` olarak adlandırılır <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> almak için arabirimi bir <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> arabirimi. Son olarak, <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> yönteminde <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> arabirimi aracılığıyla olayları göndermek için çağrılır [olay](../../../extensibility/debugger/reference/idebugportevents2-event.md) yöntemi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Yöntemini aşağıdaki tabloda gösterilmektedir `IDebugPortEvents2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Olay](../../../extensibility/debugger/reference/idebugportevents2-event.md)|Oluşturma ve yok etme işlemlerini ve programları bağlantı noktası açıklayan olaylar gönderir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IDebugPortEvents2` SDM tarafından zaten ayıklanacak bir işlemde çalışan programlar hata ayıklamak için de kullanılır.  
  
 Bağlantı noktası olayları SDM bu arabirim tarafından geçirilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)