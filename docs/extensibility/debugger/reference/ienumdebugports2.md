---
title: IEnumDebugPorts2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugPorts2
helpviewer_keywords: IEnumDebugPorts2
ms.assetid: 1754eef3-cf62-42e0-b218-1911acba77d4
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8379dc1c7dfedfcf46b594fe6ea3bfbc64dfb950
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugports2"></a>IEnumDebugPorts2
Bu arabirim, bir makine veya bağlantı noktası sağlayıcı bağlantı noktaları numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugPorts2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bir bağlantı noktası tedarikçi sağlayıcı tarafından oluşturulan bağlantı noktalarının bir listesini temsil etmek için bu arabirimi uygular. Visual Studio kendi bağlantı noktası tedarikçi desteklenmesi amacıyla bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) bağlantı noktası sağlayıcı tarafından oluşturulan bağlantı noktalarının bir listesini temsil eden bu arabirimi elde edilir. Çağrı [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md) kaydedildi bağlantı noktalarının bir listesini temsil eden bu arabirimi sağlamak için diske.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IEnumDebugPorts2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Sonraki](../../../extensibility/debugger/reference/ienumdebugports2-next.md)|Bağlantı noktaları bir numaralandırma dizisinde belirtilen sayısını alır.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugports2-skip.md)|Bağlantı noktaları bir numaralandırma dizisinde belirtilen sayıda atlar.|  
|[Sıfırla](../../../extensibility/debugger/reference/ienumdebugports2-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugports2-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugports2-getcount.md)|Bağlantı noktası sayısını bir numaralandırıcı alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio bu arabirim işlemlere ekleme için kullanılan bağlantı noktaları listesini doldurmak yardımcı olmak için kullanır.  
  
 Hata ayıklama altyapısı bu arabirimi genellikle kullanmaz.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)   
 [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)