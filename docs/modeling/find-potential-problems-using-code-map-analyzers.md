---
title: Kod Haritası çözümleyicilerini kullanarak olası sorunları bulma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.progression.codemapanalyzers
helpviewer_keywords:
- code analysis, dependency graphs
- dependency graphs, analyzing code
- graph documents, analyzing
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 99ee711922cd7f486373ef4aa2703483adb91347
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="find-potential-problems-using-code-map-analyzers"></a>Kod haritası çözümleyicilerini kullanarak olası sorunları bulma
Çözümleyiciler, fazla karmaşık olabilir ya da geliştirme gerekebilir kodu tanımlamanıza yardımcı olması için kod haritalarını çalıştırın. Örneğin, bu çözümleyiciler kullanabilirsiniz:  

|**Sahip code bulmak için**|**Bu alanları görmek için inceleyin olup olmadığını**|  
|-------------------------------|--------------------------------------------|  
|Döngüler veya döngüsel bağımlılıklar|Bunları basitleştirmeye ve bu döngüsü sonu olup olmadığını düşünün.|  
|Çok fazla bağımlılıkları|Çok fazla işlev gerçekleştirip veya bu alanları değiştirmenin etkisini belirlemek için. Doğru biçimlendirilmiş kod Haritası olabildiğince az sayıda bağımlılık gösterecektir. Kod korumak, Değiştir, test ve yeniden, olup daha net bir şekilde tanımlanan böylece bu alanları yeniden düzenlemeniz veya kodları birleştirip düşünün daha kolay hale getirmek için benzer işlevler gerçekleştirir.|  
|Hiçbir bağımlılık|Gerekli olan veya bu kod kaldırmanız gerekir.|  

## <a name="analyze-code-maps"></a>Kod haritaları Çözümle  

1.  Map araç çubuğunda seçin **düzeni**, **çözümleyiciler**ve ardından çalıştırmak istediğiniz Çözümleyicisi:  

    |**Çözümleyicisi**|**Düğümleri tanımlamak için**|  
    |------------------|--------------------------------|  
    |**Döngüsel başvuru Çözümleyicisi**|Döngüsel bağımlılıklar birbirine vardır. **Not:** bulunan döngüsel bağımlılıklar **genel türler** Grup grubu genişlettiğinizde haritada gösterilmez.|  
    |**Hub çözümleyici Bul**|Yüksek oranda bağlı düğümlerden üst %25 olan<br /><br /> **Harita üzerinde tüm diğer düğümlere gizlemek için**<br /><br /> -Harita kısayol menüsünü açın, seçin **Gelişmiş**, **seçin**, **Gizle seçilmemiş**.<br />     Harita seçilmemiş düğümleri gizler ve çözümleyici yeni düğümleri hub olarak tanımlar.|  
    |**Başvurulmayan düğümler Çözümleyicisi**|Diğer düğümlerden başvuruları yok. **Dikkat:** kodu kullanılmaz varsayılarak önce bu durumların her birinde doğrulayın. XAML bağımlılıkları ve çalışma zamanı bağımlılıkları gibi belirli bağımlılıklar statik olarak kod içinde bulunamıyor.|  

 Kod Haritası çözümleyicilerini onları uyguladıktan sonra çalışmaya devam eder. Harita değiştirirseniz, uygulanan çözümleyiciler otomatik olarak güncelleştirilen harita işleyecektir. Map araç çubuğunda çalışan bir çözümleyiciyi durdurmak için tercih **düzeni**, **çözümleyiciler**. Seçili Çözümleyicisi devre dışı bırakın.  

> [!TIP]
>  Çok büyük bir eşleme varsa, çalışan bir çözümleyiciyi bir bellek yetersiz özel durumuna neden olabilir. Bu meydana gelirse, kapsamını azaltmak ya da daha küçük bir belirteç oluşturmak için harita düzenleyin ve ardından Çözümleyicisi çalıştırın.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)   
 [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Hata ayıklarken çağrı yığınında yöntemler eşleştirme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
