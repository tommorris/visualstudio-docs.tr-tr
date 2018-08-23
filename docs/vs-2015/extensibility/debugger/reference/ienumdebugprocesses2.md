---
title: IEnumDebugProcesses2 | Microsoft Docs
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
- IEnumDebugProcesses2
helpviewer_keywords:
- IEnumDebugProcesses2
ms.assetid: 06a1368f-10f0-44eb-af61-e388c2327111
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 802dfd38f3a2765c876a5e026c21a9028fb6642e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690018"
---
# <a name="ienumdebugprocesses2"></a>IEnumDebugProcesses2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEnumDebugProcesses2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugprocesses2).  
  
Bu arabirim, hata ayıklama bağlantı noktasında çalışan işlemleri numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugProcesses : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bağlantı noktası sağlayıcısı bir bağlantı noktasında çalışan işlemlerin bir listesini sağlamak üzere bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Visual Studio çağrıları [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md) bu arabirimi elde edilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IEnumDebugProcesses2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)|Bir numaralandırma sıralı işlemlerde belirtilen sayıda alır.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugprocesses2-skip.md)|Bir numaralandırma sıralı işlemlerde belirtilen sayıda atlar.|  
|[Sıfırlama](../../../extensibility/debugger/reference/ienumdebugprocesses2-reset.md)|Bir numaralandırma sıralı başlangıç durumuna sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugprocesses2-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprocesses2-getcount.md)|İşlem sayısı bir numaralandırıcı alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio doldurmak için bu arabirimi kullanan **işlemleri** penceresi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)

