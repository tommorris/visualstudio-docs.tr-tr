---
title: "Nasıl yapılır: izleme eklenmiş ikili dosyaları yeniden konumlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.binaries
helpviewer_keywords:
- binaries, instrumented
- instrumentation, instrumented binaries
- instrumented binaries and relocating
- profiling tools, instrumented binaries
ms.assetid: 258f49e8-4b09-477e-a132-8fad685b66f4
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 72c15bfc5449a1dab516be217da4a76276312fd3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-relocate-instrumented-binaries"></a>Nasıl yapılır: Araç Haline Getirilmiş İkili Dosyaları Yeniden Konumlandırma
İzleme sırasında araştırmalar uygulama performansını ölçmek için ikili olarak eklenir. İzleme eklenmiş ikili taşıyabilir seçerek, özgün ikili bir kopyasını işaretlenir ve belirtilen konuma yerleştirin. Bu seçenek, özgün ikili dosyanız yeniden adlandırmak için profil oluşturucu istemiyorsanız yararlıdır. İkili yeniden konumlandırılmasını değil, ikili özgün sürümünün üzerine yazılır.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
### <a name="to-relocate-instrumented-binary"></a>İzleme eklenmiş ikili konumunu değiştirmek için  
  
1.  İçinde **performans Gezgini**, performans oturumu sağ tıklatın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları**, tıklatın **ikili** özellikleri.  
  
3.  Seçin **izleme eklenmiş ikili dosyaları yeniden konumlandırma** onay kutusu.  
  
4.  İzleme eklenmiş ikili dosya konumunu belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [VSInstr](../profiling/vsinstr.md)