---
title: "Desteklenen olay türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], supported events
ms.assetid: a3c0386d-551e-4734-9a0c-368d1c2e6671
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d161b078e4001ea7f02311bbcefe4c7f1eb6b7b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="supported-event-types"></a>Desteklenen olay türleri
Hata ayıklama için Visual Studio şu anda aşağıdaki olay türlerini destekler:  
  
-   Zaman uyumsuz olayları  
  
     Oturum hata ayıklama Yöneticisi'ni (SDM) bildirin ve ayıklanacak uygulama durumunu değiştirme IDE. Bu olaylar SDM ve IDE zamanınızda işlenir. Olay işlendikten sonra yanıt hata ayıklama altyapısı (DE) gönderilir. [IDebugOutputStringEvent2](../../extensibility/debugger/reference/idebugoutputstringevent2.md) ve [IDebugMessageEvent2](../../extensibility/debugger/reference/idebugmessageevent2.md) arabirimleri zaman uyumsuz olayların örnekler verilmiştir.  
  
-   Zaman uyumlu olaylar  
  
     SDM ve ayıklanacak uygulama durumunu değiştirme IDE bildirin. Bu olaylar ve zaman uyumsuz olaylar arasındaki tek fark yanıt yoluyla gönderilir olan [ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) yöntemi.  
  
     Zaman uyumlu bir olay gönderme IDE alır ve olayı işleyen sonra işleme devam etmek için DE gerektiğinde kullanışlı olur.  
  
-   Zaman uyumlu olaylar durdurma ya da olaylar durdurma  
  
     SDM ve IDE ayıklanacak uygulama kodu yürütme durduruldu bildirin. Durdurma olay yöntemi yoluyla gönderdiğinizde [olay](../../extensibility/debugger/reference/idebugeventcallback2-event.md), [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) parametresi gereklidir. Durdurma olayları aşağıdaki yöntemlerden biri için bir çağrı tarafından devam ettirilen:  
  
    -   [Yürütme](../../extensibility/debugger/reference/idebugprogram2-execute.md)  
  
    -   [Adım](../../extensibility/debugger/reference/idebugprogram2-step.md)  
  
    -   [Devam etmek](../../extensibility/debugger/reference/idebugprogram2-continue.md)  
  
     Arabirimler [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) ve [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) durdurma olayları gösterilebilir.  
  
    > [!NOTE]
    >  Zaman uyumsuz durdurma olayları desteklenmez. Zaman uyumsuz durdurma olay göndermek için bir hata var.  
  
## <a name="discussion"></a>Tartışma  
 Olayların gerçek uygulamayı sizin DE tasarımına bağlıdır. Gönderilen her olayın türünü DE tasarlarken hangi ayarlanan kendi öznitelikleri tarafından belirlenir. Örneğin, bir DE gönderebilir bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) başka bir durdurma olayı olarak gönderebilir sırasında zaman uyumsuz bir olay olarak.  
  
 Aşağıdaki tabloda, hangi program ve iş parçacığı parametreleri hangi olayları, yanı sıra olay türleri gerekli olduğunu belirtir. Herhangi bir olay zaman uyumlu olabilir. Hiçbir olay zaman uyumlu olması gerekir.  
  
> [!NOTE]
>  [IDebugEngine2](../../extensibility/debugger/reference/idebugengine2.md) arabirimi tüm olaylar için gereklidir.  
  
|Olay|IDebugProgram2|IDebugThread2|Olayları durdurma|  
|-----------|--------------------|-------------------|---------------------|  
|[IDebugActivateDocumentEvent2](../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md)|Gerekli|Gerekli|Evet|  
|[IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugBreakpointUnboundEvent2](../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)|Gerekli|Gerekli|Evet|  
|[IDebugCanStopEvent2](../../extensibility/debugger/reference/idebugcanstopevent2.md)|Gerekli|Gerekli|Hayır|  
|[IDebugDocumentTextEvents2](../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|İzin verilmiyor|İzin verilmiyor|Hayır|  
|[IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)|İzin verilmiyor|İzin verilmiyor|Hayır|  
|[IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md)|Gerekli|Gerekli|Evet|  
|[IDebugErrorEvent2](../../extensibility/debugger/reference/idebugerrorevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Olabilir|  
|[IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md)|Gerekli|Gerekli|Evet|  
|[IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Olabilir|  
|[IDebugInterceptExceptionCompleteEvent2](../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)|Gerekli|Gerekli|Evet|  
|[IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md)|Gerekli|Gerekli|Evet|  
|[IDebugMessageEvent2](../../extensibility/debugger/reference/idebugmessageevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Olabilir|  
|[IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|Gerekli|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugOutputStringEvent2](../../extensibility/debugger/reference/idebugoutputstringevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|Gerekli|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|Gerekli|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugPropertyCreateEvent2](../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|Gerekli|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugPropertyDestroyEvent2](../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|Gerekli|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugReturnValueEvent2](../../extensibility/debugger/reference/idebugreturnvalueevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Hayır|  
|IDebugStopCompleteEvent2|Gerekli|Gerekli|Evet|  
|[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)|Gerekli|Gerekli|Evet|  
|[IDebugSymbolSearchEvent2](../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Hayır|  
|[IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|Gerekli|Gerekli|Hayır|  
|[IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|Gerekli|Gerekli|Hayır|  
|[IDebugThreadNameChangedEvent2](../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|İzin verilen, ancak gerekli değil|İzin verilen, ancak gerekli değil|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olayları Gönderme](../../extensibility/debugger/sending-events.md)