---
title: "Kesme noktası ilgili yöntemleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], breakpoint methods
- breakpoints, methods
ms.assetid: a6f77bf0-bf81-443f-8683-5f12075bbe10
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f5bf80b78545242a625b9c3e212c101712ecbd9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="breakpoint-related-methods"></a>Kesme noktası ilgili yöntemleri
Hata ayıklama altyapısı (DE) kesme noktaları ayarını desteklemesi gerekir. Visual Studio hata ayıklama kesme noktaları aşağıdaki türlerini destekler:  
  
-   Bağlı  
  
     Kullanıcı Arabirimi aracılığıyla istenir ve belirtilen kod konuma başarılı bir şekilde bağlı  
  
-   Bekleniyor  
  
     UI ancak gerçek henüz ilişkili yönergeleri istendi  
  
## <a name="discussion"></a>Tartışma  
 Bekleyen bir kesme noktası Örneğin, yönergeleri henüz yüklenmedi oluşur. Ne zaman kodu, kesme noktaları deneyin kodu belirtilen konumda, yani bağlamak için kodda kesme yönergeleri eklemek için bekleyen yüklenir. Olayları oturum hata ayıklama Yöneticisi (SDM) başarılı bağlama belirtin veya bağlama hatalar bildirmek için gönderilir.  
  
 Bekleyen bir kesme noktası da kendi karşılık gelen bağlı kesme noktaları iç listesini yönetir. Bir kesme noktası bekleyen birçok kesme noktaları ekleme kodu neden olabilir. Kesme noktaları karşılık gelen bağlı ve Visual Studio kullanıcı Arabirimi hata ayıklama kesme noktaları bekleyen bir ağaç görünümünü gösterir.  
  
 Oluşturma ve kesme noktaları bekleyen kullanımını gerektiren uyarlamasını [IDebugEngine2::CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) aşağıdaki yöntemlerinden birini yanı sıra yöntemi [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) arabirimleri.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)|Belirtilen bir olup olmadığını belirleyen kesme noktası bir kod konuma bağlayabilirsiniz.|  
|[Bağlama](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)|Belirtilen bir kesme noktası bir veya daha fazla kod konumlara bağlar.|  
|[GetState](../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)|Bekleyen bir kesme noktası durumunu alır.|  
|[GetBreakpointRequest](../../extensibility/debugger/reference/idebugpendingbreakpoint2-getbreakpointrequest.md)|Bekleyen bir kesme noktası oluşturmak için kullanılan kesme isteğini alır.|  
|[Etkinleştir](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)|Bekleyen bir kesme noktası etkin durumunu değiştirir.|  
|[EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)|Bekleyen bir kesme noktası bağlı tüm kesme noktaları numaralandırır.|  
|[EnumErrorBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)|Bekleyen bir kesme noktası neden tüm hata kesme noktaları numaralandırır.|  
|[Sil](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)|Bekleyen bir kesme noktası ve ondan bağlı tüm kesme noktalarını siler.|  
  
 Hata kesme noktaları ve ilişkili kesme noktaları numaralandırmak için tüm yöntemleri uygulamak [IEnumDebugBoundBreakpoints2](../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md) ve [IEnumDebugErrorBreakpoints2](../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md).  
  
 Konum bir kod bağlamak kesme noktaları bekleyen aşağıdaki uyarlamasını gerektiren [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) yöntemleri.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../extensibility/debugger/reference/idebugboundbreakpoint2-getpendingbreakpoint.md)|Bir kesme noktası içerdiğinden bekleyen kesme noktası alır.|  
|[GetState](../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)|İlişkili bir kesme noktası durumunu alır.|  
|[GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)|Bir kesme noktası açıklar kesme noktası çözümleme alır.|  
|[Etkinleştir](../../extensibility/debugger/reference/idebugboundbreakpoint2-enable.md)|Etkinleştirir veya bir kesme noktası devre dışı bırakır.|  
|[Sil](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)|İlişkili bir kesme noktası siler.|  
  
 Çözümleme ve bilgi gerektiren aşağıdaki uyarlamasını isteği [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) yöntemleri.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetBreakpointType](../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md)|Bir çözüm tarafından temsil edilen kesme noktası türünü alır.|  
|[GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)|Bir kesme noktası açıklar kesme noktası çözümleme bilgilerini alır.|  
  
 Bağlama sırasında oluşabilecek hatalar çözümlemesini gerektirir aşağıdaki uyarlamasını [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) yöntemleri.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)|Bir hata kesme noktası içerdiğinden bekleyen kesme noktası alır.|  
|[GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)|Bir hata kesme noktası açıklar kesme hatası çözümleme alır.|  
  
 Bağlama sırasında oluşabilecek hatalar çözümlenmesi ayrıca aşağıdaki yöntemlerinden birini gerektirir [IDebugErrorBreakpointResolution2](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md).  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetBreakpointType](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md)|Bir kesme noktası türünü alır.|  
|[GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)|Bir kesme noktası çözümleme bilgilerini alır.|  
  
 Kesme noktasında kaynak kodu görüntüleme gerektirir yöntemlerini uygulamak [IDebugStackFrame2::GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) ve/veya yöntemlerinin [IDebugStackFrame2::GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme Denetimi ve Durum Değerlendirmesi](../../extensibility/debugger/execution-control-and-state-evaluation.md)