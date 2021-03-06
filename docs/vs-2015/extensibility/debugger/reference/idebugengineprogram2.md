---
title: IDebugEngineProgram2 | Microsoft Docs
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
- IDebugEngineProgram2
helpviewer_keywords:
- IDebugEngineProgram2 interface
ms.assetid: 151003a9-2e4d-4acf-9f4d-365dfa6b9596
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f9af106d32cf62e8ce07b8d27dec8ae7f2c9016
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689225"
---
# <a name="idebugengineprogram2"></a>IDebugEngineProgram2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugEngineProgram2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugengineprogram2).  
  
Bu arabirim, çok iş parçacıklı hata ayıklama desteği sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEngineProgram2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısını aynı anda birden çok iş parçacığı hata ayıklamayı desteklemek için bu arabirimi uygular. Bu arabirimi uygulayan aynı nesne üzerinde uygulanan [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Kullanım [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) bu arabirimden almak için bir `IDebugProgram2` arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugEngineProgram2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)|Bu programa tüm iş parçacıkları durdurur.|  
|[WatchForThreadStep](../../../extensibility/debugger/reference/idebugengineprogram2-watchforthreadstep.md)|İzleyen yürütme (veya yürütme için İzlemeyi Durdur) için verilen iş parçacığı üzerinde gerçekleşmesi için.|  
|[WatchForExpressionEvaluationOnThread](../../../extensibility/debugger/reference/idebugengineprogram2-watchforexpressionevaluationonthread.md)|İfade değerlendirme programı durdurulmuş olsa bile verilen iş parçacığı üzerinde gerçekleşmesi için izin verir (veya izin vermiyor).|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio yanıt olarak bu arabirimi çağıran bir [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) olay ve programın "İş parçacığı adım İzle" ve "İzleme için ifade değerlendirme üzerinde iş parçacığı" durumlarını ayarlama. [Durdur](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) zaman çağrılır program durdurulacak; bu yöntem program tüm iş parçacıklarını sonlandırma olanağı verir.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

