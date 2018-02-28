---
title: "Yürütme denetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], control of execution
ms.assetid: 97071846-007e-450f-95a6-f072d0f5e61e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a76b14f28bdb74345813931fc334f98090abd93c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="control-of-execution"></a>Yürütme denetimi
Hata ayıklama altyapısı (DE) genellikle aşağıdaki olaylardan biri son başlatma olayı olarak gönderir:  
  
-   Yeni başlatılan program için ekleme, giriş noktası olay  
  
-   Zaten çalışan bir program ekleme, yük complete olayı  
  
 Her iki bu olayları DE kullanıcıdan yanıt yoluyla IDE bekleyeceği anlamına gelen olayları duruyor. Daha fazla bilgi için bkz: [işlem modları](../../extensibility/debugger/operational-modes.md).  
  
## <a name="stopping-event"></a>Olay durdurma  
 Hata ayıklama oturumu durdurma olay gönderildiğinde:  
  
1.  Program ve geçerli yönerge işaretçisi içeren iş parçacığı olay arabiriminden elde edilebilir.  
  
2.  IDE geçerli kaynak kodu dosyasının ve görüntülediği Düzenleyicisi'nde vurgulanmış konumunu belirler.  
  
3.  Tipik olarak hata ayıklama oturumu programın çağırarak bu ilk durdurma olaya yanıt **devam** yöntemi.  
  
4.  Program, daha sonra içinde ve durum DE bir kesme noktası olay hata ayıklama oturumu gönderir, bir kesme noktası çıkma gibi bir durdurma koşulu bulduğu kadar çalıştırır. Kesme noktası olay durdurma bir olaydır ve DE bir kullanıcı yanıtı yeniden bekler.  
  
5.  Kullanıcı, üzerinde adımla ödememeyi ya da bir işlev dışında IDE programın çağırmak için hata ayıklama oturumu ister `Step` adım (yönerge, deyimi veya satırı) ve adım türü birimi geçirme yöntemi — diğer bir deyişle, üzerinde adımla verilip , veya işlev dışında. Adım tamamlandığında DE durdurma olayı hata ayıklama oturumu için adım complete olayını gönderir.  
  
     veya  
  
     Kullanıcının geçerli yönerge işaretçi çalıştırmaya devam etmeyi seçerse, IDE programın çağırmak için hata ayıklama oturumu ister **yürütme** yöntemi. Sonraki durdurma koşulu bulduğu kadar program yürütme devam ettirir.  
  
     veya  
  
     Hata ayıklama oturumu belirli durdurma olayı yoksayabilir olursa hata ayıklama oturumu programın çağırır **devam** yöntemi. Ardından durdurma koşulu karşılaştığında programın içine, üzerinden veya bir işlev dışında atlama, adım devam eder.  
  
 Programlı olarak DE durdurma koşulu karşılaştığında gibi durdurma olaylar gönderir [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) veya [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) yoluyla oturum hata ayıklama yöneticisine (SDM) bir [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) arabirimi. DE geçişleri [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) ve [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md) program ve geçerli yönerge işaretçisi içeren iş parçacığı temsil eden arabirimler. SDM çağrıları [IDebugThread2::EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) üst yığın çerçevesi ve çağrılarını almak için [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) geçerli yönerge ile ilişkili belge içerik almak için İşaretçi. Bu belge bağlam genellikle bir kaynak kodu dosya adı, satır ve sütun sayıdır. IDE bunlar geçerli yönerge işaretçisi içeren kaynak kodu vurgulamak için kullanır.  
  
 Genellikle SDM çağırarak bu ilk durdurma olaya yanıt [IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md). İçinde durum DE gönderir, bir kesme noktası basarsa gibi bir durdurma koşulu bulduğu kadar program sonra çalışır bir [IDebugBreakpointEvent2 arabirimi](../../extensibility/debugger/reference/idebugbreakpointevent2.md) SDM için. Kesme noktası olay durdurma bir olaydır ve DE bir kullanıcı yanıtı yeniden bekler.  
  
 Kullanıcı, üzerinde adımla ödememeyi ya da bir işlev dışında IDE çağırmak için SDM ister [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md), onu [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) (yönerge, deyimi veya satırı) ve [ STEPKIND](../../extensibility/debugger/reference/stepkind.md), diğer bir deyişle, içine, üzerinden veya işlev dışında adım verilip. Adım tamamlandığında DE gönderir bir [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) durdurma olayı SDM arabirimi.  
  
 Kullanıcının geçerli yönerge işaretçi çalıştırmaya devam etmeyi seçerse, IDE çağırmak için SDM ister [IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md). Sonraki durdurma koşulu bulduğu kadar program yürütme devam ettirir.  
  
 Hata ayıklama paketi belirli durdurma olayı yoksayabilir olursa hata ayıklama paket çağırır SDM çağırır [IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md). Ardından durdurma koşulu karşılaştığında programın içine, üzerinden veya bir işlev dışında atlama, adım devam eder. Nasıl devam edileceği bilir böylece bu program bir sürüm durumu tutar anlamına gelir.  
  
 SDM yapar için çağrıları `Step`, **yürütme**, ve **devam** SDM hızlı geri dönmek için çağrı beklediğini anlamı olan zaman uyumsuz. DE SDM durdurma olay önce aynı iş parçacığı üzerinde gönderirse `Step`, **yürütme**, veya **devam** döndürür, SDM askıda kalır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)