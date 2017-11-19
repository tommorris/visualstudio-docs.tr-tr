---
title: IDebugBreakEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBreakEvent2
helpviewer_keywords: IDebugBreakEvent2 interface
ms.assetid: 57dfdbc2-4e68-4dbf-9579-006cd6fb1c62
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 41c63d947d1c59e041aef051fffc4def85e0bded
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbreakevent2"></a>IDebugBreakEvent2
Bu arabirim oturum hata ayıklama Yöneticisi'ni (SDM) zaman uyumsuz bir sonu başarıyla tamamlandığını bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBreakEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 DE bir program kullanıcı sonları desteklemek için bu arabirimi uygular. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) arabirimi uygulanan, bu arabirimle aynı nesne üzerinde (SDM kullanan [QueryInterface](/cpp/atl/queryinterface) erişimi `IDebugEvent2` arabirimi).  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 SDM çağrıları [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) zaman kullanıcı istedi Duraklatılacak ayıklanacak program. Program başarıyla duraklatıldı zaman DE gönderir `IDebugBreakEvent2` olay. Bu olay kullanılarak gönderilen [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) ayıklanacak programın eklendiğinde SDM tarafından sağlanan geri çağırma işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, bir kullanıcı seçebilirsiniz **sonu tüm** komutunu **hata ayıklama** menü sonsuz bir döngüde çalıştırılan bir program dışında bölün. SDM çağırarak durdurmak için program söyler [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md). DE gönderir `IDebugBreakEvent2` program son olarak durduğunda.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)