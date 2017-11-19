---
title: "Bir Program başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, launching
- programs, launching
ms.assetid: 6857e9c6-e44a-468a-afa4-f7c4a0b77844
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 29e05c7cef8b7bc8644ccbf7ea542e2f043547a6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="launching-a-program"></a>Bir Program başlatma
Bir program hata ayıklamak istediğiniz kullanıcılar hata ayıklayıcıda IDE içinden çalıştırmak için F5 tuşuna basabilirsiniz. Bu, bir dizi sonuçta IDE'nin sırayla bağlı veya bağlı, programa şu şekilde bir hata ayıklama altyapısı (DE) bağlanırken neden olay başlar:  
  
1.  IDE önce hata ayıklama ayarları çözümün etkin proje alınacak proje paket çağırır. Ayarları başlangıç dizinini, ortam değişkenleri, programın çalıştırılacağı bağlantı noktası ve programı oluşturmak için belirtilmişse kullanmak için DE içerir. Bu ayarlar, hata ayıklama paketi geçirilir.  
  
2.  SE belirtilmişse DE programını başlatmak için işletim sistemi çağırır. Program başlatma gruplarındaki sonucu olarak, programın çalışma zamanı ortamı yüklenir. Örneğin, bir program içinde MSIL yazılmışsa, ortak dil çalışma zamanı programı çalıştırmak için çağrılır.  
  
     veya  
  
     SE belirtilmezse, bağlantı noktası yüklenmesi programın çalışma zamanı ortamı neden programını başlatmak için işletim sistemi çağırır.  
  
    > [!NOTE]
    >  Bir programı başlatmak için SE kullandıysanız, aynı DE programına bağlı olasıdır.  
  
3.  Olup DE veya bağlantı noktası program başlatılan, bağlı olarak DE ya da çalışma zamanı ortamı sonra bir program açıklaması veya düğümü oluşturur ve program çalışırken bağlantı noktası bildirir.  
  
    > [!NOTE]
    >  Hata ayıklaması yapılabilir bir program basit bir gösterimini program düğümü olduğu için çalışma zamanı ortamı program düğümü oluşturmanız önerilir. Yalnızca oluşturmak ve bir program düğümü kaydetmek için tüm DE yüklemeye gerek yoktur. DE tasarlanmıştır, IDE, ancak hiçbir IDE sürecinde çalıştırmak için gerçekten çalıştıran, var. bir program düğümü bağlantı noktasına ekleyebilirsiniz bir bileşen olması gerekir.  
  
 Yeni oluşturulan program diğer programları ile birlikte ilgili ilgisiz, başlatılan veya aynı IDE içinden hata ayıklama oturumu oluşturmak için bağlı.  
  
 Program aracılığıyla, kullanıcı ilk bastığında **F5**, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]ait hata ayıklama paketini çağırır (, dağıtılma program türü ile ilişkili olan) proje paketi aracılığıyla <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> sırayla doldurur çıkışı yöntemi bir <xref:Microsoft.VisualStudio.Shell.Interop.VsDebugTargetInfo2> çözümün etkin proje hata ayıklama ayarlarıyla yapısı. Bu yapı için bir çağrı hata ayıklama paketi geçirilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugger2.LaunchDebugTargets2%2A> yöntemi. Hata ayıklama paket sonra hata ayıklaması ve tüm ilişkili hata ayıklama motorları programı başlatan oturum hata ayıklama Yöneticisi (SDM) başlatır.  
  
 SDM geçilen bağımsız değişkenlerden biri programını başlatmak için kullanılacak DE GUID'dir.  
  
 DE GUID değilse `GUID_NULL`, SDM DE birlikte oluşturur ve ardından çağırır kendi [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) yöntemi programı başlatın. Örneğin, bir program yerel kodda sonra yazılmışsa `IDebugEngineLaunch2::LaunchSuspended` büyük olasılıkla çağıracak `CreateProcess` ve `ResumeThread` (programı çalıştırmak için Win32 işlevleri).  
  
 Program başlatma gruplarındaki sonucu olarak, programın çalışma zamanı ortamı yüklenir. DE ya da çalışma zamanı ortamı oluşturur, ardından bir [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) program açıklamak için arabirim ve bu arabirime geçirir [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) program bağlantı noktası bildirmek için çalışıyor.  
  
 Varsa `GUID_NULL` gönderilir, ardından bağlantı noktası program başlatılır. Program çalışmaya başladıktan sonra çalışma zamanı ortamı oluşturur bir `IDebugProgramNode2` program açıklamak için arabirim ve buna ileten `IDebugPortNotify2::AddProgramNode`. Bu programı çalıştırmayı bağlantı noktası bildirir. Ardından SDM hata ayıklama altyapısı çalışan programa ekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Bağlantı noktası bildirme](../../extensibility/debugger/notifying-the-port.md)  
 Bir program başlatıldıktan sonra bağlantı noktası bildirilir ne olacağını açıklar.  
  
 [Başlatma sonra ekleme](../../extensibility/debugger/attaching-after-a-launch.md)  
 Hata ayıklama oturumu DE programına eklemek hazır olduğunda belgeler.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata ayıklama görevleri](../../extensibility/debugger/debugging-tasks.md)  
 Bir program başlatma ve ifadeleri değerlendirme gibi çeşitli hata ayıklama görevlere bağlantılar içerir.