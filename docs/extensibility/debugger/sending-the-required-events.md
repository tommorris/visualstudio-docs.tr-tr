---
title: "Gerekli olayları gönderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], required events
ms.assetid: 08319157-43fb-44a9-9a63-50b919fe1377
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 30a5b1150d44c138465db36da2b032b71f075397
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sending-the-required-events"></a>Gerekli olayları gönderme
Gerekli olayları göndermek için bu yordamı kullanın.  
  
## <a name="process-for-sending-required-events"></a>Gerekli olayları gönderme işlemi  
 Aşağıdaki olaylar, bu sırada bir hata ayıklama oluşturma altyapısı, (DE) ve bir programa ekleme gereklidir:  
  
1.  Gönderme bir [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) olay nesnesine oturum hata ayıklama Yöneticisi'ni (bir veya daha fazla program bir işlemde hata ayıklamak için DE başlatıldığında SDM).  
  
2.  Ayıklanacak program iliştirildiği gönderilsin bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) SDM olay nesnesine. Bu olay altyapısı tasarımınızın bağlı olarak bir durdurma olay olabilir.  
  
3.  Program ekli ise işlemi başlatıldığında Gönder bir [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) yeni bir iş parçacığı IDE bildirmek için SDM olay nesnesine. Bu olay altyapısı tasarımınızın bağlı olarak bir durdurma olay olabilir.  
  
4.  Gönderme bir [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) ayıklanacak program tamamlanan yükleme veya programa ekleme tamamlandığında olduğunda SDM olay nesnesine. Bu olay durdurma olay olması gerekir.  
  
5.  Ayıklanacak uygulama başlatılırsa Gönder bir [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) ilk yönerge kodu çalıştırma mimarisinde çalıştırılmak üzere olduğunda SDM olay nesnesine. Bu olay her zaman bir durdurma olayıdır. Hata ayıklama oturumu Adımlama, IDE üzerinde bu olaya durdurur.  
  
> [!NOTE]
>  Birçok dil kodlarını başında genel başlatıcıları veya dış, önceden derlenmiş işlevleri (CRT kitaplık veya _main'den) kullanın. Ayıkladığınız program dilinin ya da bu tür ilk giriş noktası önce öğeler içeriyorsa, sonra bu kodu çalıştırmak ve giriş noktası olayı gönderilir, kullanıcı giriş noktası, gibi **ana** veya `WinMain`, ulaşıldı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ayıklanacak bir Program etkinleştirme](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)