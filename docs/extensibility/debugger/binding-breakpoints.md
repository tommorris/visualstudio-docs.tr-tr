---
title: "Kesme noktaları bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: breakpoints, binding
ms.assetid: 70737387-c52f-4dae-8865-77d4b203bf25
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 08000dddcd574d21225aa110cf9eb4ab2487aadb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="binding-breakpoints"></a>Kesme noktaları bağlama
Kullanıcı bir kesme noktası ayarlarsa, belki de F9 basarak IDE isteği formulates ve kesme noktası oluşturmak için hata ayıklama oturumu ister.  
  
## <a name="setting-a-breakpoint"></a>Kesme noktası ayarlama  
 Kod veya kesme noktası tarafından etkilenen veri henüz kullanılamayabilir kesme noktası ayarlama iki adımlı bir işlem nedeni. İlk olarak, kesme açıklanan ve kod ve veriler kullanılabilir duruma geldiğinde, daha sonra bu, kod veya verileri gibi bağlı olması gerekir:  
  
1.  Kesme noktası ilgili hata ayıklama motorlarından (DEs) istenen ve kullanılabilir hale geldiğinde ardından kesme kod veya veri bağlıdır.  
  
2.  Kesme noktası isteği için tüm ilgili DEs gönderdiği hata ayıklama oturumu için gönderilir. Kesme noktası işlemek için seçtiği DE karşılık gelen kesme noktası bir eylem oluşturur.  
  
3.  Hata ayıklama oturumu bekleyen kesme noktaları toplar ve bunları hata ayıklama paket geri (Visual Studio hata ayıklama bileşeni) gönderir.  
  
4.  Hata ayıklama paket bekleyen kesme noktası kod veya veri bağlamak için hata ayıklama oturumu ister. Hata ayıklama oturumu için tüm ilgili DEs bu isteği gönderir.  
  
5.  DE kesme bağlamak mümkün ise, bir kesme noktası olay hata ayıklama oturumu bağımlı gönderir. Değilse, bunun yerine bir kesme noktası hata olayı gönderir.  
  
## <a name="pending-breakpoints"></a>Bekleyen kesme noktaları  
 Bekleyen bir kesme noktası birden fazla kod konuma bağlayabilirsiniz. Örneğin, bir C++ şablonu için kaynak kod satırı şablondan oluşturulan her kod dizisi bağlayabilirsiniz. Hata ayıklama oturumu bir kesme noktası ilişkili olay bir kesme noktası olay gönderildiği aynı anda bağlı kod bağlamları numaralandırmak için kullanabilirsiniz. Daha fazla kod bağlamları daha sonra birden çok kesme noktası her bağlama istek için olayları bağlı DE gönderebilir şekilde bağlanabilir. Ancak, bir DE bağ istek başına yalnızca bir kesme noktası hata olayı göndermesi gerekir.  
  
## <a name="implementation"></a>Uygulama  
 Programlı olarak hata ayıklama Paket Yöneticisi'ni (SDM) oturum hata ayıklama çağırır ve buna verir bir [IDebugBreakpointRequest2](../../extensibility/debugger/reference/idebugbreakpointrequest2.md) sarmalar arabirimi bir [BP_REQUEST_INFO](../../extensibility/debugger/reference/bp-request-info.md) açıklar yapısı Ayarlanacak kesme noktası. Kesme noktaları birçok biçimlerinin olsa da, bunlar sonuçta bir kod veya veri bağlamı çözümleyin.  
  
 SDM çağırarak her ilgili DE bu çağrıyı geçirir, [CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) yöntemi. Kesme noktası işlemek DE seçerse, oluşturur ve döndüren bir [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) arabirimi. SDM bu arabirimleri toplar ve bunları geri tek bir hata ayıklama paketin geçirir `IDebugPendingBreakpoint2` arabirimi.  
  
 Şu ana kadar hiçbir olay oluşturulmuş.  
  
 Hata ayıklama paket çağırarak bekleyen kesme noktası kod veya veri bağlamak daha sonra çalışır [bağlamak](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md), DE tarafından gerçekleştirilir.  
  
 Kesme noktası bağlıysa DE gönderir bir [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) olay arabirimi hata ayıklama paket için. Hata ayıklama paket kullandığı tüm kod bağlamları (veya tek bir veri bağlamı) numaralandırmak için bu arabirimi çağırarak kesme noktasına bağlı [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md), bir veya daha fazla döndürür [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) arabirimleri. [GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md) arabirimi döndürür bir [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) arabirimi ve [GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) döndüren bir [BP_ RESOLUTION_INFO](../../extensibility/debugger/reference/bp-resolution-info.md) kod veya veri bağlamı içeren birleşimi.  
  
 DE kesme bağlanamıyor ise, tek bir gönderir [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) olay arabirimi hata ayıklama paket için. Hata ayıklama paket çağırarak bilgi iletisi ve hata türü (hata veya uyarı) alır [GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md), ardından [GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) ve [ GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md). Bu döndürür bir [BP_ERROR_RESOLUTION_INFO](../../extensibility/debugger/reference/bp-error-resolution-info.md) iletisi ve hata türünü içeren yapısı.  
  
 SE bir kesme noktası işler, ancak bağlama yapılamaz ise hata türü döndürür `BPET_TYPE_ERROR`. Bir hata iletişim kutusu görüntüleyerek hata ayıklama paket yanıt verir ve IDE bir ünlem işareti karakteri kaynak kod satırı solundaki kesme karakteri içine yerleştirir.  
  
 SE bir kesme noktası işlediğinde, ancak bazı diğer bağlanamıyor DE bağlamak, bir uyarı verir. IDE soru karakter kaynak kod satırı solundaki kesme karakteri içine girerek yanıt verir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama görevleri](../../extensibility/debugger/debugging-tasks.md)