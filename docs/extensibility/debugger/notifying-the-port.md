---
title: Bağlantı noktası bildiren | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports, notification
ms.assetid: f9fce48e-7d4e-4627-a0fb-77b75428146a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1420ca8768ddf1eaedc0d515810bc88b3491c4db
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="notifying-the-port"></a>Bağlantı noktası bildirme
Bir programı başlattıktan sonra bağlantı noktası, aşağıdaki gibi bildirilmesi gerekir:  
  
1.  Bir bağlantı noktasına yeni bir program düğüm aldığında, hata ayıklama oturumu program oluşturma olay gönderir. Olay ile program temsil eden bir arabirim taşır.  
  
2.  Hata ayıklama oturumu program ekleyebilirsiniz. bir hata ayıklama altyapısı (DE) tanıtıcısı için sorgular.  
  
3.  Hata ayıklama oturumu DE Bu program için izin verilen DEs listesinde olup olmadığını denetler. Hata ayıklama oturumu çözümün etkin program ayarları, ilk olarak hata ayıklama paketi tarafından geçirilen bu listeyi alır.  
  
     İzin verilen listesinde DE olması gerekir, aksi takdirde DE programa eklenmemiş.  
  
 Program aracılığıyla, bir bağlantı noktası önce yeni bir program düğüm aldığında, oluşturduğu bir [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) programı temsil eden arabirim.  
  
> [!NOTE]
>  Bu ile karıştırılmamalıdır `IDebugProgram2` daha sonra hata ayıklama altyapısı (DE) tarafından oluşturulan arabirimi.  
  
 Bağlantı noktası gönderir bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) program oluşturma olayı bir COM yoluyla oturum hata ayıklama Yöneticisi (SDM) dön `IConnectionPoint` arabirimi.  
  
> [!NOTE]
>  Bu ile karıştırılmamalıdır `IDebugProgramCreateEvent2` daha sonra DE tarafından gönderilen arabirimi.  
  
 Olay arabirimini birlikte kendisi, bağlantı noktası gönderir [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md), [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md), ve [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) bağlantı noktasını temsil eder, arabirimleri işlemek ve , sırasıyla program. SDM çağrıları [IDebugProgram2::GetEngineInfo](../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md) program ayıklayabilirsiniz DE GUİD'si alınamadı. GUID başlangıçta uygulamasından edinilen [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) arabirimi.  
  
 SDM DE izin verilen DEs listede olup olmadığını denetler. SDM çözümün etkin program ayarları, ilk olarak hata ayıklama paketi tarafından geçirilen bu listeyi alır. İzin verilen listesinde DE olması gerekir, aksi takdirde programına bağlanmayacak.  
  
 Aygıtların kimliğini bilinen sonra SDM programına eklemek hazırdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir Program başlatma](../../extensibility/debugger/launching-a-program.md)   
 [Başlatma sonra ekleme](../../extensibility/debugger/attaching-after-a-launch.md)   
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)