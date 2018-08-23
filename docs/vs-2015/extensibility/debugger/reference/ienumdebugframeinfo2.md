---
title: IEnumDebugFrameInfo2 | Microsoft Docs
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
- IEnumDebugFrameInfo2
helpviewer_keywords:
- IEnumDebugFrameInfo2
ms.assetid: 994e30ad-435a-4f9e-9272-d96d9e01099c
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7e343b8caabe2a09943ccc4cd068a62598dea548
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688125"
---
# <a name="ienumdebugframeinfo2"></a>IEnumDebugFrameInfo2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEnumDebugFrameInfo2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugframeinfo2).  
  
Bu arabirim numaralandırır [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) yapıları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugFrameInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE), geçerli çağrı yığınını açıklayan yapıların listesini sağlamak için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Visual Studio çağrıları [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) bir kesme noktası olduğunda bu arabirimi almak için özel durum ya da durdurmak ayıklanan bir programda gerçekleşir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IEnumDebugFrameInfo2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)|Belirtilen sayıda alır [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) yapıları, bir sabit listesi sırası.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugframeinfo2-skip.md)|Belirtilen sayıda atlar [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) yapıları, bir sabit listesi sırası.|  
|[Sıfırlama](../../../extensibility/debugger/reference/ienumdebugframeinfo2-reset.md)|Bir numaralandırma sıralı başlangıç durumuna sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugframeinfo2-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)|Sayısını alır [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) yapılarda bir numaralandırıcı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio bu arabirim, bir kesme noktası, özel durum veya hata ayıklanan programa duraklatma kullanıcı tarafından oluşturulan işleme ilk adımı olarak alır. Listesini [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) yapılarını temsil eder, geçerli çağrı yığınını, liste ve eski işlevin başında geçerli işlev çağrısıyla listesinin sonunda çağırın. Her `FRAMEINFO` ifade değerlendirmesi yapılamıyor ve yerel değişkenler baktığı konumunda bir bağlamı bir yığın çerçevesini temsil eder.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)

