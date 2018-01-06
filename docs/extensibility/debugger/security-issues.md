---
title: "Güvenlik sorunları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 753f916d148675afd7313afc8673232f22280b7d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="security-issues"></a>Güvenlik sorunları
Visual Studio kullanarak bir program hata ayıklamak için gereken tek izinleri olanları programı çalıştırmak için geliştiricinin ihtiyacı aynıdır. Bu, çoğu durumlarda (Internet bilgi hizmeti gibi başka hizmetleri içeren bazı durumlarda izinler daha yüksek düzeyde gerektirebilir) uzaktan hata ayıklama içerir.  
  
 Visual Studio çalışırken, işlem hata ayıklama Yöneticisi'ni (PDM) yerel makine üzerinde hata ayıklama işlemleri izler. Uzaktan msvsmon.exe adlı bir programı uzaktan hata ayıklama işlemek ve PDM kullanılabilmesi için geliştirici tarafından başlatılır. (Unutmayın. Bu msvsmon.exe hizmet değildir ve bu makinede uzaktan hata ayıklamayı etkinleştirmek için el ile başlatılması gerekir.) Visual Studio (veya msvsmon.exe) çalışmadığında, hiçbir işlem hata ayıklama için izlenir.  
  
 Bu, geliştirici çözemiyorsa özel izinler ile başlatılan programlar ayıklayabilirsiniz anlamına gelir. Geliştirici bile bu diğer kişi aynı güvenlik grubunun bir üyesi ise başka bir kullanıcı tarafından başlatılan işlemleri ayıklayabilirsiniz. Ve yalnızca gerekli kopyalamak için dosyaları uzak makine ve msvsmon.exe Başlat uzaktan hata ayıklamayı etkinleştirmek için bu gereklidir (bkz [uzaktan hata ayıklama](../../debugger/remote-debugging.md) daha fazla ayrıntı için).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama görevleri](../../extensibility/debugger/debugging-tasks.md)   
 [İşlem Hata Ayıklama Yöneticisi](../../extensibility/debugger/process-debug-manager.md)   
 [Uzaktan hata ayıklama](../../debugger/remote-debugging.md)