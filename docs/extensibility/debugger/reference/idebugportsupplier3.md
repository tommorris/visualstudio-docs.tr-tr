---
title: IDebugPortSupplier3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortSupplier3
helpviewer_keywords: IDebugPortSupplier3 interface
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3bd2a46573ca655df3372c33182860cf2d4816d7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugportsupplier3"></a>IDebugPortSupplier3
Bu arabirim, çağıran bir bağlantı noktası Tedarikçi ve bağlantı noktaları (bunları diske yazarak) hata ayıklayıcı çağırmaları arasında korumak korunan Bu bağlantı noktalarının bir listesini alma belirlemek verir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugPortSupplier3 : IDebugPortSupplier2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bir bağlantı noktası tedarikçi kalıcı yapma veya bağlantı noktası bilgilerini diske kaydetme desteklemek için bu arabirimi uygular. Bu arabirim aynı nesne üzerinde uygulanmalı [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [QueryInterface](/cpp/atl/queryinterface) üzerinde `IDebugPortSupplier2` bu arabirimi sağlamak için arabirim.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Kaynağından devralındı yöntemleri yanı sıra [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) arabirimi, bu arabirim aşağıdakileri destekler:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|Bağlantı noktası sağlayıcı bağlantı noktaları (bunları diske yazarak) hata ayıklayıcı çağırmaları arasında kalıcı olup olmadığını döndürür.|  
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|Numaralandırılacak Bu bağlantı noktası tedarikçi tarafından diske yazılan tüm bağlantı noktaları üzerinden kullanılabilir bir nesne döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir bağlantı noktası tedarikçi çağrılarını arasında bağlantı noktaları devam ederse, bu arabirimi uygulamalıdır. Bağlantı noktası sağlayıcı örneği ve bağlantı noktası tedarikçi kaldırıldığı zaman diske yazılan bağlantı noktalarını yüklenmesi.  
  
 Hata ayıklama altyapısı genellikle bir bağlantı noktası tedarikçi ile etkileşime girmez ve bu arabirim için hiçbir kullanıma sahip olur.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)