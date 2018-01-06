---
title: IDebugEngine2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2
helpviewer_keywords: IDebugEngine2 interface
ms.assetid: 1f0e9ac0-6dfb-461a-976c-888d82144cdb
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 95a1a8c48bd6eab0f21ccc85a125b5d10f42ef4e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine2"></a>IDebugEngine2
Bu arabirimi hata ayıklama altyapısı (DE) temsil eder. Ayarlama ve özel durumları temizlemek için kesme noktaları oluşturulurken bir hata ayıklama oturumu çeşitli yönlerini yönetmek için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Bu arabirim programları hata ayıklama yönetmek için özel bir DE tarafından uygulanır. Bu arabirim tarafından DE uygulanmalıdır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim, oturum hata ayıklama Yöneticisi özel durumları yönetme, kesme noktaları oluşturma ve DE tarafından gönderilen zaman uyumlu olaylar yanıtlama gibi hata ayıklama oturumu yönetmek için (SDM) tarafından çağrılır.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugEngine2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)|Tarafından SE ayıklanacak tüm programlar için bir numaralandırıcı oluşturur.|  
|[Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)|SE bir programa ekler.|  
|[CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)|Bekleyen bir kesme noktası DE oluşturur.|  
|[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)|Belirli bir özel durum DE nasıl yöneteceğini belirtir.|  
|[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)|Artık hata ayıklama altyapısı tarafından işlenir için belirtilen özel durum kaldırır.|  
|[RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)|IDE belirli çalışma zamanı mimarisi veya dil için ayarlanmış özel durumlar listesine kaldırır.|  
|[GetEngineID](../../../extensibility/debugger/reference/idebugengine2-getengineid.md)|GUID DE değerini alır.|  
|[DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)|Belirtilen program beklenmedik şekilde sona erdi ve Aygıtların program için tüm başvuruları temizlemek ve bir programın gönderip SE destroy olay bildirir.|  
|[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)|SDM için daha önce DE tarafından gönderilen bir zaman uyumlu hata ayıklama olayı alındı ve işlenen olduğunu belirtmek için SDM tarafından çağrılır.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)|DE yerel ayarlar.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugengine2-setregistryroot.md)|Kayıt defteri kök şu anda DE tarafından kullanılacak ayarlar.|  
|[SetMetric](../../../extensibility/debugger/reference/idebugengine2-setmetric.md)|Ölçüm ayarlar.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugengine2-causebreak.md)|İstekleri tüm programlar tarafından bu DE ayıklanacak yürütme kendi iş parçacığı birini çalıştırmak için bir sonraki başlatışında durdurun.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)