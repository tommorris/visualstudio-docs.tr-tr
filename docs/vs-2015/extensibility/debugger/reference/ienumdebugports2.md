---
title: IEnumDebugPorts2 | Microsoft Docs
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
- IEnumDebugPorts2
helpviewer_keywords:
- IEnumDebugPorts2
ms.assetid: 1754eef3-cf62-42e0-b218-1911acba77d4
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9ff7eac1da5cba43bf93a352e571c7a1f912932b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694363"
---
# <a name="ienumdebugports2"></a>IEnumDebugPorts2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEnumDebugPorts2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugports2).  
  
Bu arabirim, makine veya bağlantı noktası tedarikçi bağlantı noktalarını numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugPorts2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bağlantı noktası sağlayıcısı sağlayıcı tarafından oluşturulan bağlantı noktalarının bir listesini göstermek için bu arabirimi uygular. Visual Studio, kendi bağlantı noktası sağlayıcısı desteklemek üzere bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) bağlantı noktası sağlayıcısı tarafından oluşturulan bağlantı noktalarının bir listesini temsil eden bu arabirimi elde edilir. Çağrı [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md) kaydedildi bağlantı noktalarının bir listesini temsil eden bu arabirimi almak için diske.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IEnumDebugPorts2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugports2-next.md)|Belirtilen bir sabit listesi sırası rastgele bağlantı sayısını alır.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugports2-skip.md)|Bir sabit listesi sırası rastgele bağlantı belirtilen sayıda atlar.|  
|[Sıfırlama](../../../extensibility/debugger/reference/ienumdebugports2-reset.md)|Bir numaralandırma sıralı başlangıç durumuna sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugports2-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugports2-getcount.md)|Bağlantı noktası sayısını bir numaralandırıcı alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio işlemlere ekleme için kullanılan bağlantı noktaları listesini doldurmak için bu arabirimi kullanır.  
  
 Hata ayıklama altyapısı, genellikle bu arabirimi kullanmaz.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)   
 [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)

