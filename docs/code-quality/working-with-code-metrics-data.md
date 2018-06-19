---
title: Visual Studio'da kod ölçümleri sonuçları penceresi
ms.date: 12/12/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c5e6fdff99a8fc28e83fe4848fa4f31788cda76f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31923875"
---
# <a name="using-the-code-metrics-results-window"></a>Kod ölçümleri sonuçları penceresi kullanma

**Kod ölçümleri sonuçları** penceresi kod ölçümleri analiz tarafından oluşturulan veri görüntüler. Kod ölçüm verileri değerleri hakkında daha fazla bilgi için bkz: [kod ölçüm değerleri](../code-quality/code-metrics-values.md).

## <a name="displaying-code-metrics-results"></a>Kod ölçümleri sonuçları görüntüleme

**Kod ölçümleri sonuçları** penceresi kod ölçümleri sonuçları oluşturduğunuzda otomatik olarak görüntülenir. Ayrıca, herhangi bir zamanda penceresinde görüntüleyebilirsiniz.

### <a name="to-display-the-code-metrics-results-window"></a>Kod ölçümleri sonuçları penceresi görüntülemek için

- Üzerinde **Çözümle** menüsünde seçin **Windows** > **kod ölçümleri sonuçları**.

   \- veya -

- Üzerinde **Görünüm** menüsünde seçin **diğer pencereler** > **kod ölçümleri sonuçları**.

**Kod ölçümleri sonuçları** penceresi görüntülenir, hiçbir sonuç içerse bile.

### <a name="to-view-code-metrics-details"></a>Kod ölçümleri ayrıntılarını görüntülemek için

Kod ölçümleri sonuçları oluşturulduysa ağacında genişletin **hiyerarşi** sütun.

## <a name="filtering-code-metrics-results"></a>Kod ölçümleri sonuçları filtresi

Görüntülenen sonuçları filtreleyebilirsiniz **kod ölçümleri sonuçları** üstündeki araç çubuğunu kullanarak penceresi. Örneğin, bir bakım dizin 65 aşağıda sahip sonuçları görmek isteyebilirsiniz.

**Filtre** açılan kutusu sonuçları sütunlarının adlarını içerir. Bir filtre tanımlandığında, listenin girinti birlikte eklenir. Listenin tanımlanan son on filtreleri içerebilir.

### <a name="to-filter-the-code-metrics-results"></a>Kod ölçümleri sonuçları filtrelemek için

1.  Gelen **filtre** listesinde, sütun adı seçin.

2.  İçinde **Min**, görüntülenecek en düşük değerini yazın.

3.  İçinde **Max**, görüntülenecek maksimum değeri yazın.

4.  Tıklatın **Filtre Uygula** düğmesi.

5.  Sonucu ayrıntıları görmek için hiyerarşi ağacı genişletin.

## <a name="adding-removing-and-rearranging-data-columns"></a>Ekleme, kaldırma ve veri sütunları yeniden düzenleme

Ekleyebileceğiniz veya Kaldır sonuçları sütunlarından **kod ölçümleri sonuçları** penceresi. Ayrıca, böylece istediğiniz sırayla göründükleri sonuçları sütunları düzenleyebilirsiniz.

### <a name="to-remove-a-column"></a>Bir sütunu kaldırmak için

1. Tıklatın **Sütun Ekle/Kaldır** düğmesi.

     \- veya - herhangi bir sütun başlığını sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.

1. İçinde **Sütun Ekle/Kaldır** iletişim kutusu, onay kutusunu temizleyerek sütunu için kaldırın ve ardından istediğiniz **Tamam**.

### <a name="to-add-a-previously-removed-column"></a>Önceden Kaldırılan sütun eklemek için

1. Tıklatın **Sütun Ekle/Kaldır** düğmesi.

     \- veya -

     Herhangi bir sütun başlığını sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.

1. İçinde **Sütun Ekle/Kaldır** iletişim kutusunda, eklemek ve ardından istediğiniz sütun için onay kutusunu seçin **Tamam**.

### <a name="to-rearrange-columns"></a>Sütunları yeniden düzenlemek için

1. Tıklatın **Sütun Ekle/Kaldır** düğmesi.

     \- veya -

     Herhangi bir sütun başlığını sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.

1. İçinde **Sütun Ekle/Kaldır** iletişim kutusunda, taşıyın ve sonra Yukarı veya aşağı oka tıklatın istediğiniz sütun seçin.

1. Sütun istediğiniz yerde konumlandırıldığında tıklatın **Tamam**.

## <a name="copying-data-to-the-clipboard-or-excel"></a>Pano veya Excel'e veri kopyalama

Seçin ve kod ölçümleri verileri seçili satırını adını ve her veri sütununun değeri için bir satır içeren bir metin dizesi olarak panoya kopyalayın. Tıklatarak **Microsoft Excel'de Aç seçimi** tüm kod ölçümleri sonuçları bir Excel elektronik tabloya vermek için.

## <a name="creating-a-work-item-based-on-code-metric-results"></a>Kod ölçüm sonuçlarına dayalı bir iş öğesi oluşturma

Oluşturabileceğiniz bir [Visual Studio Team Services (VSTS)](/vsts/index) dayanır iş öğesi sonuçları **kod ölçüm sonuçlarını** penceresi. İş öğesi oluşturulduğunda, Visual Studio otomatik olarak bir başlık girer **başlık** alan ve kod ölçümleri verileri altında **geçmişi** sekmesi.

VSTS hakkında daha fazla bilgi için iş öğelerini, bkz: [iş öğeleri (VSTS)](/vsts/work/work-items/index).

### <a name="to-create-a-work-item-based-on-a-result"></a>Bir sonuca bağlı bir iş öğesi oluşturmak için

1.  Sonuca sağ tıklayın.

2.  İşaret **iş öğesi oluşturma**ve ardından oluşturmak istediğiniz iş öğesi türü (**hata**, **görev**, vb.).

3.  Tüm gerekli alanları doldurarak iş öğesi formunu tamamlayın.

4.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** iş öğesini kaydetmek için.

### <a name="to-create-a-bug-based-on-a-result"></a>Bir sonuca bağlı bir hata oluşturmak için

1.  Sonucun seçmek için tıklatın.

2.  Tıklatın **iş öğesi oluşturma** düğmesi.

3.  Tüm gerekli alanları doldurarak iş öğesi formunu tamamlayın.

4.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** iş öğesini kaydetmek için.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod ölçüm değerleri](../code-quality/code-metrics-values.md)
- [Nasıl yapılır: kod ölçümleri verileri üretme](../code-quality/how-to-generate-code-metrics-data.md)