---
title: IDebugProgramEngines2 | Microsoft Docs
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
- IDebugProgramEngines2
helpviewer_keywords:
- IDebugProgramEngines2 interface
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3dc2e1af08e6668730e48956e184bfc3fad1d4a9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631876"
---
# <a name="idebugprogramengines2"></a>IDebugProgramEngines2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgramEngines2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramengines2).  
  
Bu arabirim tarafından program düğümleri bu programda hata ayıklamak tüm olası hata ayıklama altyapısı (DE) belirtmek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProgramEngines2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Bir DE veya özel bağlantı noktası sağlayıcısı bu arabirimi uygulayan aynı nesne üzerinde uygulayan [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) belirli bir program için kullanılacak belirli bir DE oluşturma desteklemek için.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) üzerinde bir `IDebugProgramNode2` arabirimi bu arabirim elde edilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugProgramEngines2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|Bu programda hata ayıklamak olası DEs gösterir.|  
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|Bu program hata ayıklama için kullanılacak DE seçer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir DE kullanıcı tarafından seçilen sonra bu seçimi program düğümle çağırarak kayıtlı [SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md). Seçili olan altyapı tarafından döndürülen altyapısı olur [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)
