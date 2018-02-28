---
title: "Hata ayıklayıcı kavramları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK]
ms.assetid: 2d371d38-f1a0-4a9a-8ea3-100e8c0149b7
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 920706adb86d79e635e4f5289ca010e03282853e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugger-concepts"></a>Hata ayıklayıcı kavramları
Visual Studio hata ayıklama paketi oluşturmak için paket tasarlarken kullanılan mimari kavramlarını tanımanız gerekir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Oturum Hatalarını Ayıklama](../../extensibility/debugger/debug-session.md)  
 Hata ayıklama mimarisinde oturumunun rol açıklanmaktadır.  
  
 [Sunucular](../../extensibility/debugger/servers-visual-studio-sdk.md)  
 Tanımlar hangi bir mimari, hem Özet hem de fiziksel koşullarında hata ayıklama açısından sunucusudur.  
  
 [Bağlantı Noktası Sağlayıcıları](../../extensibility/debugger/port-suppliers.md)  
 Ne tanımlayan bir bağlantı noktası sağlayıcı mimarisi hata ayıklama açısından değildir.  
  
 [Bağlantı Noktaları](../../extensibility/debugger/ports.md)  
 Tanımlar mimarisi hata ayıklama açısından ne bir bağlantı noktasıdır.  
  
 [İşlemler](../../extensibility/debugger/processes.md)  
 Tanımlar mimarisi hata ayıklama açısından ne bir işlem değildir.  
  
 [Program Düğümleri](../../extensibility/debugger/program-nodes.md)  
 Mimari kendisi ve bu çalışan işlemi nasıl tanımlamak de dahil olmak üzere, hata ayıklama açısından program düğümünü tanımlar.  
  
 [Programlar](../../extensibility/debugger/programs.md)  
 Hata ayıklama mimarisi bakımından bir program tanımlar.  
  
 [İş Parçacıkları](../../extensibility/debugger/threads.md)  
 Hata ayıklama mimarisi bakımından iş parçacığı özelliklerini tanımlar.  
  
 [Yığın Çerçeveleri](../../extensibility/debugger/stack-frames.md)  
 Hata ayıklama mimarisi bakımından yığın çerçevesi tanımlar. Yığın çerçevesi, bir iş parçacığı yürütme bağlamı sağlayan yığının bir soyutlamadır.  
  
 [Modüller](../../extensibility/debugger/modules.md)  
 Mimari, kodu, yürütülebilir bir dosyanın veya bir DLL gibi fiziksel bir kapsayıcı olarak hata ayıklama açısından bir modül tanımlar.  
  
 [Kesme noktaları](../../extensibility/debugger/breakpoints-visual-studio-sdk.md)  
 Kesme noktaları üç tür tanımlar — bekleyen, bağımlı ve hata — mimarisi hata ayıklama bakımından.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata Ayıklayıcı Bağlamları](../../extensibility/debugger/debugger-contexts.md)  
 Nasıl hata ayıklama altyapısı (DE) aynı anda kod, belgeler ve ifade değerlendirme bağlamı içinde çalıştığı açıklanmaktadır. , Her üç bağlamları, konum, konum veya değerlendirme için ilgili açıklar.  
  
 [Hata Ayıklayıcı Bileşenleri](../../extensibility/debugger/debugger-components.md)  
 Hata ayıklama altyapısı (DE), ifade değerlendiricisi (EE) ve simge işleyici (SH) içeren Visual Studio hata ayıklama bileşenleri genel bir bakış sağlar.  
  
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)  
 Bir program başlatma ve ifadeleri değerlendirme gibi çeşitli hata ayıklama görevlere bağlantılar içerir.