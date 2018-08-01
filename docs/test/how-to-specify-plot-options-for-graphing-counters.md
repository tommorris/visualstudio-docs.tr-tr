---
title: Visual Studio'da yük testleri için sayaçları grafiğe aktarmak için çizim seçenekleri
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, graphing counters
ms.assetid: 1969c20b-e0eb-48f6-a49f-a9090cd86008
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 5df33a8cf05e4ad73b1643e2948392e49a32356e
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382327"
---
# <a name="how-to-specify-plot-options-for-graphing-counters"></a>Nasıl yapılır: belirtin çizim seçenekleri sayaçları grafiğe aktarmak için

**Çizim Seçenekleri** iletişim kutusu, bir grafikte çizilen bir sayaç renk ve çizgi stilini değiştirmek sağlar. Ayrıca, belirli bir değerin aralığı düzeltin veya örneklenen verileri temel alan otomatik olarak ayarlanması için aralığı ayarlayın.

![Çizim Seçenekleri iletişim kutusu](../test/media/ltest_plotoptions.png)

## <a name="to-specify-plotting-options-for-graphs"></a>Graflar için çizim seçenekleri belirtmek için

1.  İçinde **Yük Testi Çözümleyicisi**, seçin **grafikleri** araç.

     Bu, bir grafik görünümünde yük testi sonuçları görüntüler.

2.  Gösterge veya grafik üzerinde sağ satır ya da geçerli çizim satırı çizim seçeneğini değiştirin ve ardından istediğiniz performans sayacı **Çizim Seçenekleri**.

     **Çizim Seçenekleri** iletişim kutusu görüntüler.

3.  Kullanma **renk** aşağı açılan liste ve performans sayacı çizmek için kullanmak istediğiniz rengi seçin.

4.  Kullanma **stili** aşağı açılan liste ve performans sayacı çizmek için kullanmak istediğiniz stili seçin.

5.  Aşağıdakilerden birini yapın:

     Seçin **aralığı otomatik olarak ayarla** (varsayılan)

     \- veya -

     NET **aralığı otomatik olarak ayarla** ve **aralığı** performans sayacı çizmek için kullanmak istediğiniz aralığını belirtmek için açılır liste.

6.  Seçin **Tamam**.

     Belirtilen değişikliklerle graftaki seçeneklerini değişen performans sayacı görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

- [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md)
