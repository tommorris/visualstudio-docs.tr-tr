---
title: "Kod ölçüm verileri ile çalışma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
ms.assetid: 988193ec-b4a3-4e11-b5a1-7334979807d5
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 39d45f5d43819dc418b6378d34a19e6af1d8ee12
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="working-with-code-metrics-data"></a>Kod Ölçüm Verileri ile çalışma
**Kod ölçümleri sonuçları** penceresi kod ölçümleri analiz tarafından oluşturulan veri görüntüler. Kod ölçüm verileri değerleri hakkında daha fazla bilgi için bkz: [kod ölçüm değerleri](../code-quality/code-metrics-values.md).  
  
 Bu konu aşağıdaki bölümleri içermektedir:  
  
-   [Kod ölçümleri sonuçları penceresi](../code-quality/working-with-code-metrics-data.md#BKMK_CodeMetricsResultsWindow)  
  
-   [Kod ölçümleri sonuçları görüntüleme](../code-quality/working-with-code-metrics-data.md#BKMK_DisplayingCodeMetricsResults)  
  
-   [Kod ölçümleri sonuçları filtresi](../code-quality/working-with-code-metrics-data.md#BKMK_FilteringCodeMetricsResults)  
  
-   [Ekleme, kaldırma ve veri sütunları yeniden düzenleme](../code-quality/working-with-code-metrics-data.md#BKMK_AddingRemovingandRearrangingDataColumns)  
  
-   [Pano veya Excel'e veri kopyalama](../code-quality/working-with-code-metrics-data.md#BKMK_Copying_Data_to_the_Clipboard_or_Excel)  
  
-   [Kod ölçüm sonuçlarına dayalı bir iş öğesi oluşturma](../code-quality/working-with-code-metrics-data.md#BKMK_Creating_a_Work_Item_Based_on_Code_Metric_Results)  
  
##  <a name="BKMK_CodeMetricsResultsWindow"></a>Kod ölçümleri sonuçları penceresi  
 **Kod ölçümleri sonuçları** penceresine sahip bir araç çubuğu üstünde ve hesaplanan sonuçları görüntülemek için sütun.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Hiyerarşisi**|**Hiyerarşi** sütun genişletmek veya daraltmak için istediğiniz ayrıntı düzeyini görmek kod hiyerarşi ağaç görünümünü içerir. Kalan sütunlar, hesaplanan sonuçları gösterir. İstediğiniz sonuç sütunları düzenlemek ya da gizleme.|  
|**Bakımı**|**Bakım** sütun sayısal sonuç yanı sıra bir simge içerir. Yeşil bir simge Bakımı göreceli olarak yüksek derecede gösterir. Sarı bir simge Bakımı Orta derecesini belirtir. Kırmızı bir simge düşük bakım ve olası bir sorun nokta gösterir. Bu renk göstergeleri AvoidUnmaintainableCode FxCop kural tarafından kullanılan önem derecesi kategorilerine karşılık gelir. Bakım dizin 10, 20'den daha yüksek bir dizindir dizini 10 ve 20 ve ne bir hata veya uyarı arasında ise bir uyarı değerinden daha düşük olduğunda bu kural bir hata gönderir. Birleştirici üç ölçümleri Bakımı dizindir: cyclomatic karmaşıklık, kod ve hesaplama karmaşıklık satırları. Değerlerini birimlerinde ifade değil.|  
  
##  <a name="BKMK_DisplayingCodeMetricsResults"></a>Kod ölçümleri sonuçları görüntüleme  
 Kod ölçümleri sonuçları penceresi otomatik olarak kod ölçümleri sonuçları oluşturma görüntülenir. Ayrıca, herhangi bir zamanda penceresinde görüntüleyebilirsiniz.  
  
#### <a name="to-display-the-code-metrics-results-window"></a>Kod ölçümleri sonuçları penceresi görüntülemek için  
  
-   Üzerinde **Çözümle** menüsünde tıklatın **Windows** ve ardından **kod ölçümleri sonuçları**.  
  
     \-veya -  
  
-   Üzerinde **Görünüm** menüsündeki **diğer pencereler** ve ardından **kod ölçümleri sonuçları**.  
  
     Hatta sonuç içerdiğinde kod ölçümleri sonuçları penceresi görüntülenir.  
  
#### <a name="to-view-code-metrics-details"></a>Kod ölçümleri ayrıntılarını görüntülemek için  
  
-   Kod ölçümleri sonuçları oluşturulduysa ağacında genişletin **hiyerarşi** sütun.  
  
##  <a name="BKMK_FilteringCodeMetricsResults"></a>Kod ölçümleri sonuçları filtresi  
 Görüntülenen sonuçları filtreleyebilirsiniz **kod ölçümleri sonuçları** üstündeki araç çubuğunu kullanarak penceresi. Örneğin, bir bakım dizin 65 aşağıda sahip sonuçları görmek isteyebilirsiniz.  
  
 **Filtre** açılan kutusu sonuçları sütunlarının adlarını içerir. Bir filtre tanımlandığında, listenin girinti birlikte eklenir. Listenin tanımlanan son on filtreleri içerebilir.  
  
#### <a name="to-filter-the-code-metrics-results"></a>Kod ölçümleri sonuçları filtrelemek için  
  
1.  Gelen **filtre** listesinde, sütun adı seçin.  
  
2.  İçinde **Min**, görüntülenecek en düşük değerini yazın.  
  
3.  İçinde **Max**, görüntülenecek maksimum değeri yazın.  
  
4.  Tıklatın **Filtre Uygula** düğmesi.  
  
5.  Sonucu ayrıntıları görmek için hiyerarşi ağacı genişletin.  
  
##  <a name="BKMK_AddingRemovingandRearrangingDataColumns"></a>Ekleme, kaldırma ve veri sütunları yeniden düzenleme  
 Ekleyebileceğiniz veya Kaldır sonuçları sütunlarından **kod ölçümleri sonuçları** penceresi. Ayrıca, böylece istediğiniz sırayla göründükleri sonuçları sütunları düzenleyebilirsiniz.  
  
#### <a name="to-remove-a-column"></a>Bir sütunu kaldırmak için  
  
1.  Tıklatın **Sütun Ekle/Kaldır** düğmesi.  
  
     \-veya -  
  
     Herhangi bir sütun başlığını sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.  
  
2.  İçinde **Sütun Ekle/Kaldır** iletişim kutusu, onay kutusunu temizleyerek sütunu için kaldırın ve ardından istediğiniz **Tamam**.  
  
#### <a name="to-add-a-previously-removed-column"></a>Önceden Kaldırılan sütun eklemek için  
  
1.  Tıklatın **Sütun Ekle/Kaldır** düğmesi.  
  
     \-veya -  
  
     Herhangi bir sütun başlığını sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.  
  
2.  İçinde **Sütun Ekle/Kaldır** iletişim kutusunda, eklemek ve ardından istediğiniz sütun için onay kutusunu seçin **Tamam**.  
  
#### <a name="to-rearrange-columns"></a>Sütunları yeniden düzenlemek için  
  
1.  Tıklatın **Sütun Ekle/Kaldır** düğmesi.  
  
     \-veya -  
  
     Herhangi bir sütun başlığını sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.  
  
2.  İçinde **Sütun Ekle/Kaldır** iletişim kutusunda, taşıyın ve sonra Yukarı veya aşağı oka tıklatın istediğiniz sütun seçin.  
  
3.  Sütun istediğiniz yerde konumlandırıldığında tıklatın **Tamam**.  
  
##  <a name="BKMK_Copying_Data_to_the_Clipboard_or_Excel"></a>Pano veya Excel'e veri kopyalama  
 Seçin ve kod ölçümleri verileri seçili satırını adını ve her veri sütununun değeri için bir satır içeren bir metin dizesi olarak panoya kopyalayın. Tıklatarak **Microsoft Excel'de Aç listesi** tüm kod ölçümleri sonuçları bir Excel elektronik tabloya dışarı aktarmak için  
  
##  <a name="BKMK_Creating_a_Work_Item_Based_on_Code_Metric_Results"></a>Kod ölçüm sonuçlarına dayalı bir iş öğesi oluşturma  
 Oluşturabileceğiniz bir [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] dayanır iş öğesi sonuçları **kod ölçüm sonuçlarını** penceresi. İş öğesi oluşturulduğunda, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak bir başlık girer **başlık** alan ve kod ölçümleri verileri altında **geçmişi** sekmesi.  
  
 İş öğeleri oluşturma hakkında daha fazla bilgi için bkz: [bir iş öğesi &#91;oluşturun; yeniden yönlendirilen &#93;](http://msdn.microsoft.com/en-us/24b2e064-16ac-4bf0-8de4-98a1f48b8c4b).  
  
#### <a name="to-create-a-work-item-based-on-a-result"></a>Bir sonuca bağlı bir iş öğesi oluşturmak için  
  
1.  Sonuca sağ tıklayın.  
  
2.  İşaret **iş öğesi oluşturma**ve ardından oluşturmak istediğiniz iş öğesi türü (**hata**, **görev**, vb.).  
  
3.  Tüm gerekli alanları doldurarak iş öğesi formunu tamamlayın.  
  
4.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** iş öğesini kaydetmek için.  
  
#### <a name="to-create-a-bug-based-on-a-result"></a>Bir sonuca bağlı bir hata oluşturmak için  
  
1.  Sonucun seçmek için tıklatın.  
  
2.  Tıklatın **iş öğesi oluşturma** düğmesi.  
  
3.  Tüm gerekli alanları doldurarak iş öğesi formunu tamamlayın.  
  
4.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** iş öğesini kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)   
 [Nasıl yapılır: kod ölçümleri verileri üretme](../code-quality/how-to-generate-code-metrics-data.md)