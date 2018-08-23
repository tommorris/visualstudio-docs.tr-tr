---
title: 'Nasıl yapılır: örnekleme olayları seçme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.property.sampling
helpviewer_keywords:
- clock cycles sample event
- sample events, choosing
- profiling tools, sample events
- page faults sample event
- system calls sample event
- performance counter sample event
- performance tools, sample events
ms.assetid: ce7cb734-80ac-4930-a4ef-e24395e1cc07
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2e00dcc15633e9b62f5db02e321950e4f91814f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697311"
---
# <a name="how-to-choose-sampling-events"></a>Nasıl Yapılır: Örnekleme Olayları Seçme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: örnekleme olayları seçin](https://docs.microsoft.com/visualstudio/profiling/how-to-choose-sampling-events).  
  
Varsayılan olarak, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] profil oluşturma araçları profili oluşturulmuş bir işlem tarafından kullanılan işlemci döngülerini sayısı olarak belirtilen bir aralıkta performans verilerini toplar. Varsayılan döngüsü bir aralıkta 10,000,000, yaklaşık 1 GH bilgisayarda 0,01 saniye olan sayısıdır. Bir aralıktaki döngüsü sayısını değiştirebilirsiniz ve örnek olay değiştirebilirsiniz. Aşağıdaki örnek olayları kullanılabilir:  
  
-   Saat döngüsü - CPU bağımlı sorunları için.  
  
-   Sayfa hataları - bellek ile ilgili sorunlar için.  
  
-   Sistem çağrıları - ı GÇ ile ilgili sorunlar için.  
  
-   Performans sayacı - alt düzey performans sorunları için CPU sayaçları.  
  
> [!IMPORTANT]
>  .NET bellek verileri (ayırmalar veya nesne kullanım ömrü veya her ikisi de) örnekleme yöntemini kullanarak topladığınız gerekirse tüm kullanıcı tarafından belirtilen örnekleme olayları göz ardı edilir ve uygun bellek ayırmaları veya çöp toplama olayları veya her ikisi de, veri toplamak üzere kullanılır.  
  
### <a name="to-select-a-sample-event"></a>Örnek olay seçmek için  
  
1.  İçinde **performans Gezgini**performans oturumu sağ tıklayın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları**, tıklayın **örnekleme** özellikleri.  
  
3.  Gelen **örnek olay** aşağı açılan listesinde, uygulamanızın profilini için kullanmak istediğiniz örnek olayı seçin.  
  
    > [!NOTE]
    >  **Ulaşılabilir performans sayaçları** yalnızca seçerseniz etkin **performans sayacı** gelen **örnek olay** aşağı açılan listesi.  
  
4.  Seçerseniz **performans sayacı**, alınan belirli bir CPU sayaçlarını seçin **ulaşılabilir performans sayaçları** ağaç görünümü denetimi.  
  
    -   İçindeki sayaçları **taşınabilir olayları** düğüm tüm işlemcilerin türlerinde kullanılabilir.  
  
    -   İçindeki sayaçları **Platform olaylarını** düğümü geçerli bilgisayarda işlemci özgüdür ve diğer türde işlemci kullanılabilir olmayabilir.  
  
5.  Örnek olay seçtiğinizde, varsayılan bir örnekleme aralığı değeri görüntülenen **örnekleme aralığı** metin kutusu. Gerekirse, metin kutusuna istediğiniz değer girebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Nasıl yapılır: Koleksiyon metotları seçme](../profiling/how-to-choose-collection-methods.md)   
 [CPU ve Windows sayaçları](../profiling/cpu-and-windows-counters.md)   
 [Örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)   
 [Komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)



