---
title: Kod Haritası çözümleyicilerini kullanarak olası sorunları bulma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
f1_keywords:
- vs.progression.codemapanalyzers
helpviewer_keywords:
- code analysis, dependency graphs
- dependency graphs, analyzing code
- graph documents, analyzing
ms.assetid: 9dd799a7-f7eb-42ff-8612-b19dde7ff4eb
caps.latest.revision: 13
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: b15a6d95e2a64aa09d57cb4fba02ab0369be5799
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630402"
---
# <a name="find-potential-problems-using-code-map-analyzers"></a>Kod haritası çözümleyicilerini kullanarak olası sorunları bulma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kod kullanarak olası sorunları bulma harita Çözümleyicileri](https://docs.microsoft.com/visualstudio/modeling/find-potential-problems-using-code-map-analyzers).  
  
Fazla karmaşık olabilecek kod tanımlamanıza yardımcı olması için kod haritalarını Çözümleyicileri çalıştırın veya geliştirme ihtiyaç duyabilirsiniz. Örneğin, bu Çözümleyicileri kullanabilirsiniz:  
  
|**Sahip kodu bulmak için**|**Bu alanları görmek için inceleyin olmadığını**|  
|-------------------------------|--------------------------------------------|  
|Döngüler veya döngüsel bağımlılıklar|Bunları basitleştirin ve bu döngüleri kesme olup olmadığını göz önünde bulundurun.|  
|Çok fazla bağımlılıkları|Çok fazla işlevleri gerçekleştirdiği veya bu alanları değiştirmenin etkilerini belirlemek için. İyi biçimlendirilmiş bir kod haritası, en az bir bağımlılık sayısı gösterilir. Kod korumak, Değiştir, test edin ve yeniden, olup olmadığını ve böylece daha net bir şekilde tanımlanan bu alanları yeniden düzenleyebilirsiniz ya da benzer işlevler gerçekleştiren kod birleştirmek için göz önünde bulundurun daha kolay hale getirmek için.|  
|Hiçbir bağımlılık|Gerekli veya bu kodu kaldırmanız gerekir.|  
  
## <a name="analyze-code-maps"></a>Kod haritaları analiz edin  
  
1.  Harita araç çubuğunda **Düzen**, **Çözümleyicileri**ve sonra çalıştırmak istediğiniz Çözümleyicisi:  
  
    |**Çözümleyici**|**Düğümleri tanımlamak için**|  
    |------------------|--------------------------------|  
    |**Döngüsel başvuru Çözümleyicisi**|Döngüsel bağımlılıklar birbirleri üzerinde sahip. **Not:** bulunan döngüsel bağımlılıklar **genel türler** grubu grubu genişlettiğinizde haritada gösterilmez.|  
    |**Merkez çözümleyicisini Bul**|Yüksek oranda bağlı düğümlerin üst %25 olan<br /><br /> **Harita üzerinde tüm düğümleri gizlemek için**<br /><br /> -Map için kısayol menüsünü açın, **Gelişmiş**, **seçin**, **gizlemek için seçilmeyen**.<br />     Seçili olmayan düğümleri eşlemesi gizler ve hub'ları olarak yeni düğümler Çözümleyicisi belirler.|  
    |**Başvurulmamış düğümler Çözümleyicisi**|Diğer düğümlerden başvuruları yok. **Dikkat:** varsayarak kod kullanılmayan her durumda önce doğrulayın. XAML ve çalışma zamanı iç bağımlılıkları gibi belirli bağımlılıkları kod statik olarak bulunamıyor.|  
  
 Kod Haritası çözümleyicilerini uygulamadan sonra çalışmaya devam eder. Harita değiştirirseniz, uygulanan çözümleyiciler güncelleştirilmiş haritanın otomatik olarak işleyecektir. Harita araç çubuğunda bir çözümleyici durmaya tercih **Düzen**, **Çözümleyicileri**. Seçili Çözümleyicisi devre dışı bırakın.  
  
> [!TIP]
>  Çok büyük bir eşlemesi varsa, çalışan bir çözümleyiciyi bir yetersiz bellek özel durumu neden olabilir. Bu meydana gelirse, kapsamını azaltın veya daha küçük bir tane oluşturmak için harita düzenleyin ve ardından Çözümleyicisi çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)   
 [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Hata ayıklarken çağrı yığınında yöntemler eşleştirme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)



