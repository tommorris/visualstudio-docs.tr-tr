---
title: Güvenlik sorunları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d45ebd8c4d80b84749838c2034d72159c9e39627
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126903"
---
# <a name="security-issues"></a>Güvenlik sorunları
Visual Studio kullanarak bir program hata ayıklamak için gereken tek izinleri olanları programı çalıştırmak için geliştiricinin ihtiyacı aynıdır. Bu, çoğu durumlarda (Internet bilgi hizmeti gibi başka hizmetleri içeren bazı durumlarda izinler daha yüksek düzeyde gerektirebilir) uzaktan hata ayıklama içerir.  
  
 Visual Studio çalışırken, işlem hata ayıklama Yöneticisi'ni (PDM) yerel makine üzerinde hata ayıklama işlemleri izler. Uzaktan msvsmon.exe adlı bir programı uzaktan hata ayıklama işlemek ve PDM kullanılabilmesi için geliştirici tarafından başlatılır. (Unutmayın. Bu msvsmon.exe hizmet değildir ve bu makinede uzaktan hata ayıklamayı etkinleştirmek için el ile başlatılması gerekir.) Visual Studio (veya msvsmon.exe) çalışmadığında, hiçbir işlem hata ayıklama için izlenir.  
  
 Bu, geliştirici çözemiyorsa özel izinler ile başlatılan programlar ayıklayabilirsiniz anlamına gelir. Geliştirici bile bu diğer kişi aynı güvenlik grubunun bir üyesi ise başka bir kullanıcı tarafından başlatılan işlemleri ayıklayabilirsiniz. Ve yalnızca gerekli kopyalamak için dosyaları uzak makine ve msvsmon.exe Başlat uzaktan hata ayıklamayı etkinleştirmek için bu gereklidir (bkz [uzaktan hata ayıklama](../../debugger/remote-debugging.md) daha fazla ayrıntı için).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama görevleri](../../extensibility/debugger/debugging-tasks.md)   
 [İşlem Hata Ayıklama Yöneticisi](../../extensibility/debugger/process-debug-manager.md)   
 [Uzaktan hata ayıklama](../../debugger/remote-debugging.md)