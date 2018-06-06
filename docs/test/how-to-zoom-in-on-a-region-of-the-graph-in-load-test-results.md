---
title: Visual Studio Yük testi sonuç grafikleri yakınlaştırmak
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.graphzoom
helpviewer_keywords:
- graphs, analyzing load tests
- load tests, zooming with graphs
ms.assetid: 729b4c30-4bc3-4698-91b3-17a676897443
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: a61d53e8dbdbbce9c5a09fc8f8cd180a8b312d2c
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750977"
---
# <a name="how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results"></a>Nasıl yapılır: Yük Testi Sonuçlarında Grafiğin Bir Bölgesine Yakınlaştırma Yapma

Bir yük testi tamamladıktan sonra yakınlaştırma ve kaydırma grafiğin bir bölgesine yakınlaştırma çubuklarını kullanabilirsiniz. Yakınlaştırma tarafından ince ayrıntılı olarak yürütülen bir yük testi sırasında oluşturulan veri inceleyebilirsiniz.

> [!NOTE]
> Yakınlaştırma, çalışan bir test sonuçlarını gözlerken değil yalnızca zaman, tamamlanmış bir yük testi sonuçlarını analiz kullanılabilir.

 Yakınlaştırma Denetimi, bir yük testi sonuç yakınlaştırma modunda görüntülediğinizde, yalnızca Yük Testi Çözümleyicisi'nde görünür olur. Yakınlaştırma modu Grafik görünümünde yük testi tamamlandı ya da daha önce çalışan bir yük testi yüklendiğinde kurulur. Göster veya araç çubuğundaki Yakınlaştır denetimlerini göster kullanarak grafikler üzerinde yakınlaştırma denetimlerini gizle.

 Yatay ekseni yakınlaştırma, belirli bir zamanda süreleri yük testi sırasında çözümlemek için ayarlanabilir. Dikey y ekseni yakınlaştırma grafiğe dahil sayaçları için belirli değer aralıklarını çözümlemek için ayarlanabilir.

 Zaman Çizelgesi yatay ve dikey değer aralığı yakınlaştırma denetimleri fare kullanılarak ayarlanabilir. Yatay zaman çizelgesi denetimi sol ve sağ ok tuşlarını kullanarak da ayarlanabilir. Yakınlaştırma denetimi ayarlamak için ok tuşlarını kullanarak, aynı anda 1 örnekleme aralığı tarafından windows aralığı ayarlayabilirsiniz. SHIFT ve ok tuşlarını kullanarak 10 örnekleme aralıkları düzeltmeleri yapar.

 Yakınlaştırma Denetimi ok tuşunu kullanarak ayarlamak için önce odağı yakınlaştırma denetimi için SEKME tuşunu kullanarak ayarlayın. Sol kaydırıcıyı odağa sahip olduğunda, ok tuşlarını yakınlaştırma penceresinin başlangıç sınır 1 aralığına göre sola veya sağa taşır. Odak merkezi kaydırıcı üzerinde olduğunda yakınlaştırma penceresi sola veya sağa 1 örnekleme aralığı yakınlaştırma pencere boyutunu değiştirmeden kaydırmak için ok tuşlarını kullanabilirsiniz. Ve son olarak, sağdaki kaydırıcı taşır, genişletme veya 1 ile yakınlaştırma penceresinin bitiş aralığını azaltmayı örnekleme aralığı.

 Tam zaman çizelgesi ve değer aralıklarını göstermek için yatay ve dikey yakınlaştırma denetimlerini dönmek için kullanabileceğiniz **Yatay Uzaklaştır** seçeneği **Dikey Uzaklaştır** seçeneğini veya **Uzaklaştır Her ikisi de** grafikte açılır menüde seçeneği.

> [!TIP]
> Kullanabileceğiniz **Yatay Yakınlaştırma Denetimlerini Eşitle** otomatik yatay yakınlaştırma eşitlemesini açmak veya kapatmak geçiş yapmak için araç çubuğunda. Üzerinde hiçbir yakınlaştırma eşitleme ile uygulanan diğer grafikleri grafikler görünümünde olması grafik için de geçerlidir.

 ![Grafik görünümü yakınlaştırma denetimi](../test/media/ltest_zoomcontrol.png) grafik görünümü yakınlaştırma denetimi

 Önceki çizimde, Test grafik altında sistem eşik sorunlarını araştırmak için seçeneğinde. Eşik ihlalleri kullanarak etkinleştirilmiş **Eşik İhlallerini Grafikte Göster** gelen **grafik seçenekleri** araç çubuğundaki açılan.

 Daha fazla bilgi için bkz: [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md).

## <a name="displaying-graphs"></a>Grafik görüntüleme
 Yakınlaştırma veya uzaklaştırma veya kaydırma bir grafik görüntüsünü değiştirmeden önce grafikleri görüntülemek için bu yordamı izleyin.

### <a name="to-display-graphs"></a>Grafik görüntülemek için

1.  Tamamlanıncaya kadar bir yük testi çalıştırın.

2.  Yük testi sonunda seçin **Evet** yük testi sonuçlarını sonuçlarını görüntülemek isteyip istemediğinizi soran bir iletişim kutusu depolayın.

     \- veya -

     Daha önce çalıştırılan bir yük testine ayrıntılarını görüntüleyin. Daha fazla bilgi için bkz: [nasıl yapılır: erişim yük testi sonuçlarını çözümleme için](../test/how-to-access-load-test-results-for-analysis.md).

3.  Seçin **grafikleri** , grafikleri görüntülenmiyorsa.

4.  Yakınlaştırma çubukları görüntülenmiyorsa seçin **yakınlaştırma denetimlerini göster**.

     İki yakınlaştırma çubukları her grafik için kullanılabilir. Dikey ölçeği denetleyen yakınlaştırma çubuğu grafiğinin sol görünür. Yatay Ölçek denetleyen yakınlaştırma çubuğu grafiğin altında görünür.

     Her yakınlaştırma çubuğu iki tanıtıcıları sahiptir. Dikdörtgen bir yakınlaştırma çubuğunun her iki ucunda işleyicisidir.

## <a name="zooming-and-scrolling"></a>Yakınlaştırma ve kaydırma
 Birden çok grafik görüntüleniyorsa sahip olduğunuzda, böylece yük testi aynı bölümünü görüntüler eşitlenme kullanmaya devam edebilir.

### <a name="to-synchronize-zooming-and-scrolling"></a>Yakınlaştırma ve kaydırma eşitlemek için

1.  Yük Testi Çözümleyicisi'seçin **Yatay Yakınlaştırma Denetimlerini Eşitle**.

     Yatay Yakınlaştırma Denetimlerini Eşitle düğmesi seçildiğinde, yakınlaştırma ve kaydırma bireysel bir grafiğin zaman ölçeğini yakınlaştırır da diğer grafikleri zaman ölçeğini kaydırır.

2.  Tekrar Yatay Yakınlaştırma Denetimlerini Eşitle seçeneğini seçin.

     Yatay Yakınlaştırma Denetimlerini Eşitle düğmesi seçili olmadığında, yakınlaştırma ve kaydırma bireysel bir grafiğin zaman ölçeğini yalnızca o grafiği etkiler.

### <a name="to-zoom-and-scroll-to-a-region-of-the-graph"></a>Yakınlaştırma ve grafiğin bir bölgesine kaydırma

1.  Bir grafik altında yakınlaştırma çubuğu üzerinde sağ tarafta sol taraftaki tutamacını sürükleyin.

     Bu test çalışmasının ikinci bölümü yakınlaştırır. Benzer şekilde, sağ taraftaki tutamacı sola sürükleyerek test çalışması önceki bölümlerine yakınlaştırır.

2.  Belirli bir alanı yakınlaştırmak için bir grafik merkezine slayt hem işler.

     Yakınsa iki birbirine ne kadar fazla, yük testi kısa, hassas parçalarını görüntülemek için yakınlaştırmak tanıtıcılarıdır.

     Yakınlaştırma çubuğunun orta kısmını seçin ve ardından onu sürükleyerek yük testinde belirli bir noktaya kaydırın.

### <a name="to-zoom-to-a-region-of-the-graph-by-choosing-and-dragging"></a>Seçip sürükleyerek grafiğin belirli bir bölgesine yakınlaştırmak için

1.  Yakınlaştırma alanının bir ucunda bulunan bir grafiği seçin.

2.  Fare işaretçisini Yakınlaştırma alanının diğer ucundaki sürükleyin.

3.  Fare düğmesini bırakın.

     Bu, seçip sürükleyerek tanımladığınız alanı büyütür.

 Aşağıdaki yordam yakınlaştırma çubuğu uçlarından ayarlamak zorunda kalmadan hızla Uzaklaştır açıklar.

### <a name="to-zoom-out"></a>Uzaklaştırmak için

1.  Yakınlaştırılmış grafiğe sağ tıklayın.

2.  Kısayol menüsünden seçin **Yatay Uzaklaştır**.

     Bu yük testi süresini çalışma göstermek için uzaklaştırır.

## <a name="see-also"></a>Ayrıca bkz.

- [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Nasıl yapılır: grafiklerde sayaç ekleme ve silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)