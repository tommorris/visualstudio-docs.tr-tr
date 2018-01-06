---
title: "Nasıl yapılır: Windows (ETW) toplamak için olay izleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.events
helpviewer_keywords:
- event trace providers, performance tools
- profiling tools, event trace providers
- performance tools, enabling event trace providers
ms.assetid: aa2261fe-d5f5-49fc-a171-d18842e1dc7d
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a720bf57c8668d956a1036d73a264a4936142cd4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-collect-event-tracing-for-windows-etw-data"></a>Nasıl yapılır: Windows için Olay İzleme (ETW) Verileri
Olay izleme için Windows (ETW) profil oluşturucu günlük çekirdek veya uygulama tarafından tanımlanan olayları sağlayan bir verimli çekirdek düzeyi izleme özelliğidir. Olay sağlayıcıdan toplanan veriler yalnızca kullanılarak görüntülenebilir /**özeti: ETW** seçeneği [VSPerfReport](../profiling/vsperfreport.md) komut satırı aracı. Performans sorunlarını uygulamada gerçekleştiği belirlemek için bu raporu kullanın.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
### <a name="to-enable-event-trace-providers"></a>Olay İzleme sağlayıcıları etkinleştirmek için  
  
1.  İçinde **performans Gezgini**, performans oturumu sağ tıklatın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları**, tıklatın **Windows olaylarını** özellikleri.  
  
3.  İçinde **verileri toplamak için Select olayı izleme sağlayıcısı** listesinde, uygulamanıza profil için kullanmak istediğiniz olay sağlayıcıları seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)