---
title: "Çağrı ağacı görünümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.view.calltree
helpviewer_keywords:
- Call Tree view
- profiling tools reports, Call Tree view
- performance reports, Call Tree view
- profiling tools, Call Tree view
ms.assetid: b2dbc033-bf95-4d10-8e51-f9462979133e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0e55e469112053d7a78416c21a685d423a6bfa31
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="call-tree-view"></a>Çağrı Ağacı Görünümü
Çağrı ağacı görünümü profili uygulamada geçiş işlevi yürütme yollarını görüntüler. Ağaç kök uygulama veya bileşenin giriş noktasıdır. Her işlevi düğüm tüm adlı işlevleri ve bu işlev çağrıları hakkında performans verilerini listeler.  
  
 Çağrı ağacı görünümü de genişletin ve en uzun süre tüketilen veya sık örneklenen bir işlev yürütme yolunu vurgulayın. En ucuz performans yolunu görüntülemek için işlevi sağ tıklayın ve ardından **genişletin etkin yolunuzda**.  
  
 Profil oluşturma Çalıştır her işlem, bir kök düğümü olarak görüntülenir. Çağrı ağacı görünümü başlangıç düğümünün başlangıç düğümü olarak ayarlamak istediğiniz düğümünü sağ tıklayıp ardından seçerek ayarlayabilirsiniz **ayarlamak kök**.  
  
 Kök düğüm kümesi olduğunda, Seçili düğümün alt ağacı dışında görünümünden diğer tüm girişleri kaldırın. Kök düğüm görüntülemekte olduğunuz düğüme geri sıfırlayabilirsiniz. Çağrı ağacı Görünümü penceresi sağ tıklatın ve ardından **sıfırlama kök**.  
  
 Çağrı ağacı görünümü sütun eklemek veya kaldırmak için özelleştirilebilir. Sağ **sütun adı başlık çubuğu**ve ardından **Sütun Ekle/Kaldır**.  
  
 Çağrı ağacı görünümü sunulan veri miktarını sınırlayarak gürültü azaltma için yapılandırılabilir. Gürültü azaltma kullanarak, performans sorunlarını görünümünde daha belirgin. Performans sorunlarını ayırt etmek kolay analiz daha kolay olur. Daha fazla bilgi için bkz: [nasıl yapılır: rapor görünümlerinde gürültü azaltmayı yapılandırma](../profiling/how-to-configure-noise-reduction-in-report-views.md).  
  
> [!NOTE]
>  Gürültü azaltma etkin olduğunda bir uyarı görüntüleyecek şekilde yapılandırılmışsa, rapora bir bilgi çubuğu görüntülenir.  
  
 Çağrı ağacı görünümü sütunlar için tanımları hakkında daha fazla bilgi için aşağıdakilere bakın:  
  
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-sampling-data.md)  
  
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-instrumentation-data.md)  
  
 [Çağrı ağacı görünümü - örnekleme](../profiling/call-tree-view-dotnet-memory-sampling-data.md)  
  
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-contention-data.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans rapor görünümleri](../profiling/performance-report-views.md)   
 [İzleme veri değerlerini anlama](../profiling/understanding-instrumentation-data-values.md)   
 [Örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)