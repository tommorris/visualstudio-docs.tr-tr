---
title: "Rapor görünümlerini filtreleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: profiling tools, configuring
ms.assetid: 820cf192-7fd6-4bee-9a51-aa69154aca85
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b4e82450286d5da47a11217401ebbc17133530b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="filtering-report-views"></a>Rapor Görünümlerini Filtreleme
Profil oluşturma veri dosyalarıyla performans raporu görünümlerde görüntülenmesi ve verilen rapor dosyaları için profil oluşturma verileri sınırlamak için için filtreler uygulayabilirsiniz. Belirli işlemleri ve iş parçacıklarını verileri sınırlayabilir ve zaman damgası değerlerini arasındaki verileri için bir rapor sınırlayabilirsiniz. Dosya filtreleri Kaydet ve kaydedilmiş filtre içeri aktararak Bu filtre farklı bir profil oluşturma veri dosyası oluşturun.  
  
 Özet görünümü grafik bir zaman çizelgesi kullanarak da zaman diliminin rapor sınırlandırabilirsiniz. Bkz: [nasıl yapılır: Özet zaman çizelgesinden rapor görünümlerini filtreleme](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
 Sistem ve üçüncü taraf kodu rapordan dışlamak için bkz: [nasıl yapılır: Filtre profil oluşturma Araçlar rapor görünümlerini görüntüleme sadece kendi kodumu için](../profiling/how-to-filter-profiling-tools-report-views-to-display-just-my-code.md)  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-create-a-profiler-report-filter"></a>Profil Oluşturucusu rapor filtresi oluşturmak için  
  
1.  Performans Rapor Görünümü Filtresi penceresi görüntülenmiyorsa tıklatın **Göster filtre** performans rapor görünümü araç çubuğunda.  
  
     Performans Rapor Görünümü Filtresi bir tablodur. Tablodaki her satır bir filtre yan tümcesi temsil eder. Bir filtre için istediğiniz sayıda yan tümceleri ekleyebilirsiniz.  
  
2.  Filtre eklemek istediğiniz her yan tümcesi, seçin veya bir satır aşağıdaki alanlarına değerleri girin.  
  
    |Alan|Açıklama|  
    |-----------|-----------------|  
    |**Ve/veya**|Seçin **ve** bir sonuç eşleşiyorsa bu yan tümce sonraki yan tümcesi hem de girintili için olmalıdır. Seçin **veya** bir sonuç eşleşiyorsa bu yan tümcesi veya sonraki yan tümcesi girintili olabilir.|  
    |**Alan**|Filtre yan tümcesi veri alanları görüntülenen listesinden kullanmak için rapor alanı seçin.|  
    |**İşleci**|Alan ve değer arasında yan tümcesinde istediğiniz ilişkiyi belirten işleci seçin.<br /><br /> = Eşittir<br /><br /> <> Eşit değildir<br /><br /> < Küçüktür<br /><br /> > Büyüktür<br /><br /> < = küçüktür veya eşittir<br /><br /> > = büyüktür veya eşittir|  
    |**Değer**|Aranacak bir değer girin veya seçin. Bazı alanları alan için kullanılabilir değerleri listeler.|  
  
3.  
  
#### <a name="to-create-a-profiler-report-filter-from-the-marks-report-view"></a>Profil Oluşturucusu rapor filtresi işaretleri rapor görünümünden oluşturmak için  
  
1.  Seçin **işaretleri** gelen **Geçerli Görünüm** performans rapor görünümü araç çubuğunda listesi.  
  
     İşaretleri Profil Oluşturucusu rapor görüntülenir.  
  
2.  ETW veya örnekleme bile, raporun başlangıç noktası olarak kullanmak istediğiniz seçin.  
  
3.  Tuşuna basın ve CTRL basılı tutun ve rapor bitiş noktası olarak kullanmak istediğiniz olay'ı tıklatın.  
  
4.  Sağ tıklayın ve ardından aşağıdaki seçeneklerden birini tıklatın:  
  
    -   **Filtre işaretleri eklemek** işareti sütun filtre alanı olarak kullanma filtre yan tümcesi oluşturur.  
  
    -   **Filtre damgalarının eklemek** milisaniye içinde zaman damgası sütunu filtre alanı olarak kullanma filtre yan tümcesi oluşturur.  
  
     İki seçenek, aynı başlangıç ve bitiş noktaları geçerli veri dosyası filtreleyin. Her iki seçenek diğer raporlarda kullanmak için filtrenin verirseniz daha iyi olabilir.  
  
#### <a name="to-load-an-existing-filter-from-a-file"></a>Bir dosyadan varolan bir filtreyi yüklemek için  
  
1.  Performans rapor görünümü araç çubuğunda tıklatın **alma filtresi**.  
  
     **Yük filtre** iletişim kutusu görüntülenir.  
  
2.  Yüklemek için filtre (.vspf) dosya konumu ve dosya adını belirtin.  
  
#### <a name="to-execute-a-filter"></a>Bir filtre yürütmek için  
  
-   Performans rapor görünümü araç çubuğunda tıklatın **yürütme filtre**.  
  
#### <a name="to-stop-a-filter-that-is-taking-too-long-to-execute"></a>Yürütülmesi çok uzun sürüyor bir filtre durdurmak için  
  
-   Performans rapor görünümü araç çubuğunda tıklatın **durdurmak filtre**.  
  
#### <a name="to-remove-a-filter-on-a-report-view"></a>Rapor görünümünde bir filtreyi kaldırmak için  
  
1.  Performans Rapor Görünümü Filtresi yan tümcelerinde satırlarını silin.  
  
2.  Performans rapor görünümü araç çubuğunda tıklatın **yürütme filtre**.  
  
#### <a name="to-save-a-filter-to-a-file"></a>Bir filtre bir dosyaya kaydetmek için  
  
1.  Performans rapor görünümü araç çubuğunda tıklatın **verme filtresi**.  
  
     **Süzgeci Kaydet** iletişim kutusu görüntülenir.  
  
2.  Kaydetmek için filtre (.vspf) dosya konumu ve dosya adını belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Rapor görünümlerini özelleştirme performans araçları](../profiling/customizing-performance-tools-report-views.md)