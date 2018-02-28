---
title: IEnumDebugPrograms2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEnumDebugPrograms2
helpviewer_keywords:
- IEnumDebugPrograms2
ms.assetid: 7fbb8fb7-db64-4546-a364-dc668430c8af
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: b52c4f28f1f027648674f2be561fc11d7117b6f4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugprograms2"></a>IEnumDebugPrograms2
Bu arabirimin geçerli hata ayıklama oturumunda çalışan programlar numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugPrograms2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) tarafından DE ayıklanacak programların listesini sağlamak için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Visual Studio çağrıları [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) bu arabirimi elde edilir. [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md) Visual Studio tarafından kullanılmaz.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IEnumDebugPrograms2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)|Bir numaralandırma sırasını programlarda belirtilen sayısını alır.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugprograms2-skip.md)|Bir numaralandırma sırasını programlarda belirtilen sayıda atlar.|  
|[Sıfırla](../../../extensibility/debugger/reference/ienumdebugprograms2-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugprograms2-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprograms2-getcount.md)|Program sayısını bir numaralandırıcı alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio bu arabirime kullanır:  
  
-   Doldurmak **modülleri** penceresi (çağırarak [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) ve ardından çağırma [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) her programı'nda).  
  
-   Doldurmak **ekleme işlemi için** listesi (çağırarak `IDebugProcess2::EnumPrograms` ve ardından çağırma [QueryInterface](/cpp/atl/queryinterface) her [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) bir almakiçinarabirimi[IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md) arabirimi).  
  
-   İşlemdeki her bir program ayıklayabilirsiniz DEs listesi (kullanarak [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md)).  
  
-   Düzenle ve devam (ÇÖZÜCÜ) güncelleştirmeleri her program için geçerlidir (IDebugProcess2::EnumPrograms çağırarak ve ardından çağırma [GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md)).  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)