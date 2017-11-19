---
title: "İşlem modları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debug engines, modes
ms.assetid: f69972d0-809d-40df-9da3-04738791391c
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 205837bc5bfdf9476839ea1e54a53dc57dbf9a72
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="operational-modes"></a>İşlem modları
IDE, aşağıdaki gibi çalışabilir üç modu vardır:  
  
-   [Tasarım modu](#vsconoperationalmodesanchor1)  
  
-   [Çalıştırma modu](#vsconoperationalmodesanchor2)  
  
-   [Kesme modu](#vsconoperationalmodesanchor3)  
  
 Nasıl özel hata ayıklama altyapınız (DE) Bu modlar arasında geçiş ile geçiş mekanizmaları hakkında bilgi sahibi olmanız gerektiren bir uygulama bir karardır. DE olabilir veya doğrudan bu modların kullanmayabilir. Bu modların gerçekten kullanıcı eylemi DE olaylarından göre geçiş hata ayıklama paket modları'dır. Örneğin, kesme modu için çalışma modunda geçiş DE durdurma olayından tarafından instigated. Adım veya yürütme gibi işlemleri gerçekleştiren kullanıcı tarafından ya da modunda veya adım modunda çalışacak şekilde sonu geçiş instigated. DE geçişleri hakkında daha fazla bilgi için bkz: [denetim, yürütme](../../extensibility/debugger/control-of-execution.md).  
  
##  <a name="vsconoperationalmodesanchor1"></a>Tasarım modu  
 Tasarım, hangi sırada özellikleri, uygulamanızda hata ayıklama ayarlayabilirsiniz Visual Studio hata ayıklama, nonrunning durumunu modudur.  
  
 Yalnızca birkaç hata ayıklama özellikleri Tasarım modunda kullanılır. Bir geliştirici kesme noktalarını ayarlayın veya izleme deyimleri oluşturmak tercih edebilirsiniz. DE hiçbir zaman yüklü veya IDE Tasarım modunda çalışırken çağrılır. DE ile etkileşim yalnızca çalışma ve sonu modlarında gerçekleşir.  
  
##  <a name="vsconoperationalmodesanchor2"></a>Çalıştırma modu  
 IDE içinde hata ayıklama oturumunda bir program çalıştırıldığında çalışma modunda oluşur. Uygulama, bir kesme noktası isabet kadar veya bir özel durum kadar sonlandırma kadar çalışır. Sonlandırma, Tasarım modunda DE geçişleri için uygulama çalıştırıldığında. Bir kesme noktası isabet veya bir özel durum, kesme modu için DE geçer.  
  
##  <a name="vsconoperationalmodesanchor3"></a>Kesme modu  
 Kesme modu, hata ayıklama programın yürütülmesini askıya oluşur. Kesme modu sonu zamanında uygulamanın bir anlık görüntü Geliştirici sunar ve uygulama durumunu analiz etmek ve uygulama nasıl çalışacağını değiştirmek Geliştirici sağlar. Geliştirici görüntülemek ve kod düzenleme, inceleyin veya verileri değiştirme, uygulamayı yeniden başlatın, yürütme bitiş veya aynı noktasından yürütme devam edebilirsiniz.  
  
 Kesme modu DE zaman uyumlu durdurma olay gönderdiğinde girilir. Zaman uyumlu durdurma olayları, durdurma olayları olarak da bilinir bildir oturum hata ayıklama Yöneticisi'ni (SDM) ve ayıklanacak uygulama kodu yürütme durduruldu IDE. [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) ve [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) arabirimleri durdurma olayların örnekler verilmiştir.  
  
 Durdurma olayları çağrısı sonunu modundan modu adımı veya çalıştırmak için hata ayıklayıcı geçiş aşağıdaki yöntemlerden birini ile devam ettirilen:  
  
-   [Yürütme](../../extensibility/debugger/reference/idebugprocess3-execute.md)  
  
-   [Adım](../../extensibility/debugger/reference/idebugprocess3-step.md)  
  
-   [Devam etmek](../../extensibility/debugger/reference/idebugprocess3-continue.md)  
  
###  <a name="vsconoperationalmodesanchor4"></a>Adım modu  
 Adım modu, programın kodunu veya içine, üzerinden veya bir işlev dışında bir sonraki satıra adımları oluşur. Yöntemini çağırarak bir adım yürütülen [adım](../../extensibility/debugger/reference/idebugprocess3-step.md). Bu yöntem gerektirir `DWORD`belirtin s [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) ve [STEPKIND](../../extensibility/debugger/reference/stepkind.md) numaralandırmalar giriş parametresi olarak.  
  
 Program başarıyla sonraki satıra kodu veya bir işlevine adımları ya da imleci veya kümesi kesme noktası çalıştıran DE geri kesme modu için otomatik olarak geçiş yapar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme denetimi](../../extensibility/debugger/control-of-execution.md)