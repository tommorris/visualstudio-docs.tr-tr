---
title: "Nasıl yapılır: ek izleme seçeneklerini belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.advanced
helpviewer_keywords:
- instrumentation, options
- profiling tools, session options
- performance sessions, options
ms.assetid: 639afe26-8335-4bd4-8aa5-f2c607b81f07
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c663b4de5f35df1d0fb1bdcfda076502360361d5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-additional-instrumentation-options"></a>Nasıl yapılır: Ek İzleme Seçeneklerini Belirtme
İkili dosyaları gelen işaretleyebilir [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] tümleşik geliştirme ortamı (IDE) veya komut satırı araçlarını kullanarak. IDE içinden bir ikili izleme, izleme sırasında ek izleme seçeneklerini belirtme tarafından toplanan verilerin hacmi denetleyebilirsiniz [Vsınstr](../profiling/vsinstr.md) aracı. Bu seçenekler, oturumun veya hedef düzeyinde kullanılabilir. Örneğin, dahil etmek veya izleme işlemi sırasında belirli işlevleri dışlamak için hedef düzeyinde ek izleme seçeneği kullanın.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!IMPORTANT]
>  Eklenen her araştırma biraz özgün programın davranışını değiştirir. Bu değişikliği analiz aynı anda ek yükü neden olur. Bu ek yükü yaklaşık çıkarılır olsa bile, yine birden çok iş parçacıklı uygulamalar üzerinde Zarif zamanlama etkilere sahiptir. [Vsınstr](../profiling/vsinstr.md) aracı profili oluşturma sırasında seçenekleri Yardım denetim veri koleksiyonu.  
  
### <a name="to-specify-additional-instrumentation-option"></a>Ek izleme seçeneği belirtmek için  
  
1.  İçinde **performans Gezgini**seçin **Performans oturumunu** ve ardından sağ tıklatın ve seçin **özellikleri**.  
  
2.  İçinde **özellikler sayfalarına**, tıklatın **Gelişmiş** özellikleri.  
  
3.  Tür seçeneklerinde **ek izleme seçeneklerini** kutusu.  
  
     Örneğin, /CONTROL:THREAD profil düzeyini belirtmek için kullanın. Seçenekler tam bir listesi için bkz: [Vsınstr](../profiling/vsinstr.md).  
  
4.  **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)