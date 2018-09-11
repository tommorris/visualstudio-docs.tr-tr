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
ms.openlocfilehash: 40e265e5bdc453ec658de16f288e9c184979975f
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44321261"
---
# <a name="using-the-code-metrics-results-window"></a>Kod ölçümleri sonuçları penceresini kullanma

**Kod ölçümleri sonuçları** penceresi kod ölçümleri analiz tarafından oluşturulan verileri görüntüler. Kod ölçüm verileri değerleri hakkında daha fazla bilgi için bkz: [kod ölçüm değerleri](../code-quality/code-metrics-values.md).

## <a name="displaying-code-metrics-results"></a>Kod ölçümleri sonuçları görüntüleme

**Kod ölçümleri sonuçları** penceresinde kod ölçümleri sonuçları oluşturduğunuzda otomatik olarak görüntülenir. Ayrıca, herhangi bir zamanda penceresinde görüntüleyebilirsiniz.

### <a name="to-display-the-code-metrics-results-window"></a>Kod ölçümleri sonuçları penceresini görüntülemek için

- Üzerinde **Çözümle** menüsünde seçin **Windows** > **kod ölçümleri sonuçları**.

   \- veya -

- Üzerinde **görünümü** menüsünde seçin **diğer Windows** > **kod ölçümleri sonuçları**.

**Kod ölçümleri sonuçları** penceresi görüntülenirse, bile hiçbir sonuç içermiyor.

### <a name="to-view-code-metrics-details"></a>Kod ölçümleri görüntülemek için ayrıntıları

Kod ölçümleri sonuçları oluşturulduysa ağacında genişletin **hiyerarşi** sütun.

## <a name="filtering-code-metrics-results"></a>Kod ölçümleri sonuçlarını filtreleme

Görüntülenen sonuçlarını filtreleyebilirsiniz **kod ölçümleri sonuçları** üstündeki araç çubuğunu kullanarak pencere. Örneğin, bir bakım dizini 65 aşağıda olan sonuçları görmek isteyebilirsiniz.

**Filtre** açılan kutusu sonuçları sütun adlarını içerir. Bir filtre tanımlandığında, listenin bir girinti birlikte eklenir. Liste, tanımlanan son on filtreler içerebilir.

### <a name="to-filter-the-code-metrics-results"></a>Kod ölçümleri sonuçları filtrelemek için

1.  Gelen **filtre** listesinde, sütun adı seçin.

2.  İçinde **Min**, görüntülenecek en düşük değerini yazın.

3.  İçinde **Max**, görüntülenecek maksimum değeri yazın.

4.  Tıklayın **Filtre Uygula** düğmesi.

5.  Sonuç ayrıntıları görmek için hiyerarşi ağacı genişletin.

## <a name="adding-removing-and-rearranging-data-columns"></a>Ekleme, kaldırma ve veri sütunlarını yeniden düzenleme

Ekleyebilir ve sütunları Kaldır sonuçları **kod ölçümleri sonuçları** penceresi. Ayrıca, istediğiniz sırayla görünecekleri sonuçları sütunları yeniden düzenleyebilirsiniz.

### <a name="to-remove-a-column"></a>Bir sütunu kaldırmak için

1. Tıklayın **sütunları Ekle/Kaldır** düğmesi.

     \- veya - herhangi bir sütunun başlığına sağ tıklayın ve ardından **sütunları Ekle/Kaldır**.

1. İçinde **sütunları Ekle/Kaldır** iletişim kutusu, onay kutusunu temizleyerek sütunu kaldırın ve ardından istediğiniz **Tamam**.

### <a name="to-add-a-previously-removed-column"></a>Önceden kaldırılan bir sütun eklemek için

1. Tıklayın **sütunları Ekle/Kaldır** düğmesi.

     \- veya -

     Herhangi bir sütunun başlığına sağ tıklayın ve ardından **sütunları Ekle/Kaldır**.

1. İçinde **sütunları Ekle/Kaldır** iletişim kutusunda, eklemek ve ardından istediğiniz sütun için onay kutusunu seçin **Tamam**.

### <a name="to-rearrange-columns"></a>Sütunları yeniden sıralamak için

1. Tıklayın **sütunları Ekle/Kaldır** düğmesi.

     \- veya -

     Herhangi bir sütunun başlığına sağ tıklayın ve ardından **sütunları Ekle/Kaldır**.

1. İçinde **sütunları Ekle/Kaldır** iletişim kutusunda, taşıyabilir ve ardından yukarı veya aşağı oka tıklayın istediğiniz sütunu seçin.

1. Sütun, istediğiniz yerde konumlandırıldığında tıklayın **Tamam**.

## <a name="copying-data-to-the-clipboard-or-excel"></a>Pano veya Excel veri kopyalama

Seçin ve seçili bir satır kod ölçümleri verileri, adı ve her veri sütununun değeri için bir satır içeren bir metin dizesi olarak panoya kopyalayın. Ayrıca **Microsoft Excel'de Seçimi Aç** tüm kod ölçümleri sonuçları bir Excel elektronik tablosuna dışarı aktarmak için.

## <a name="creating-a-work-item-based-on-code-metric-results"></a>Kod ölçüm sonuçlarına göre iş öğesi oluşturma

Oluşturabileceğiniz bir [Azure panoları](/azure/devops/boards/index?view=vsts) temel alan iş öğesi sonuçlanıyor **kod ölçüm sonuçlarını** penceresi. İş öğesi oluşturulduğunda, Visual Studio otomatik olarak bir başlık girer **başlık** alan ve kod ölçümleri verileri altında **geçmişi** sekmesi.

Azure panoları hakkında daha fazla bilgi için iş öğeleri, bkz: [iş öğelerini](/azure/devops/boards/work-items/index?view=vsts).

### <a name="to-create-a-work-item-based-on-a-result"></a>Bir sonuca bağlı bir iş öğesi oluşturmak için

1.  Bir sonuca sağ tıklayın.

2.  İşaret **iş öğesi oluştur**ve ardından oluşturmak istediğiniz iş öğesinin türüne tıklayın (**hata**, **görev**, vb.).

3.  Tüm gerekli alanları doldurarak iş öğesi formu tamamlayın.

4.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** iş öğesini kaydetmek için.

### <a name="to-create-a-bug-based-on-a-result"></a>Bir sonuca bağlı bir hata oluşturmak için

1.  Seçmek için sonuca tıklayın.

2.  Tıklayın **iş öğesi oluşturma** düğmesi.

3.  Tüm gerekli alanları doldurarak iş öğesi formu tamamlayın.

4.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** iş öğesini kaydetmek için.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod ölçüm değerleri](../code-quality/code-metrics-values.md)
- [Nasıl yapılır: kod ölçümleri verileri üretme](../code-quality/how-to-generate-code-metrics-data.md)