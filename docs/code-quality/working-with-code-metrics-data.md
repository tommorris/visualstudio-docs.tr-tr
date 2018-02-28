---
title: "Kod ölçümleri sonuçları Visual Studio'da | Microsoft Docs"
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c259a1d303c741d4e36af46250073b0378a65f8b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="working-with-code-metrics-data"></a>Kod ölçüm verileri ile çalışma

**Kod ölçümleri sonuçları** penceresi kod ölçümleri analiz tarafından oluşturulan veri görüntüler. Kod ölçüm verileri değerleri hakkında daha fazla bilgi için bkz: [kod ölçüm değerleri](../code-quality/code-metrics-values.md).

## <a name="displaying-code-metrics-results"></a>Kod ölçümleri sonuçları görüntüleme

**Kod ölçümleri sonuçları** penceresi kod ölçümleri sonuçları oluşturduğunuzda otomatik olarak görüntülenir. Ayrıca, herhangi bir zamanda penceresinde görüntüleyebilirsiniz.

### <a name="to-display-the-code-metrics-results-window"></a>Kod ölçümleri sonuçları penceresi görüntülemek için

- Üzerinde **Çözümle** menüsünde seçin **Windows** > **kod ölçümleri sonuçları**.

   \-veya -

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

     \-veya - herhangi bir sütun başlığını sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.

1. İçinde **Sütun Ekle/Kaldır** iletişim kutusu, onay kutusunu temizleyerek sütunu için kaldırın ve ardından istediğiniz **Tamam**.

### <a name="to-add-a-previously-removed-column"></a>Önceden Kaldırılan sütun eklemek için

1. Tıklatın **Sütun Ekle/Kaldır** düğmesi.

     \-veya -

     Herhangi bir sütun başlığını sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.

1. İçinde **Sütun Ekle/Kaldır** iletişim kutusunda, eklemek ve ardından istediğiniz sütun için onay kutusunu seçin **Tamam**.

### <a name="to-rearrange-columns"></a>Sütunları yeniden düzenlemek için

1. Tıklatın **Sütun Ekle/Kaldır** düğmesi.

     \-veya -

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

[Kod ölçüm değerleri](../code-quality/code-metrics-values.md)  
[Nasıl yapılır: Kod Ölçümleri Verileri Üretme](../code-quality/how-to-generate-code-metrics-data.md)