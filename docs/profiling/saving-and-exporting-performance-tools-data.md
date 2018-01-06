---
title: "Araçları verilerini kaydetme ve performans dışarı aktarma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: performance tools, saving and exporting reports
ms.assetid: 2e9b28fe-3ed2-4e1d-b9cb-0a5e384380b0
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 37306636da74637cb950ca1502b94a750a51ccba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="saving-and-exporting-performance-tools-data"></a>Araçları verilerini kaydetme ve performans dışarı aktarma
Bu konu, kaydetme ve performans veri dosyaları dışarı aktarma açıklar.  
  
##  <a name="BKMK_Save_Profiler_Data_Files_As_Analyzed_Report_Files"></a>Nasıl yapılır: performans veri dosyalarına çözümlenen rapor dosyaları olarak Kaydet  
 Profil oluşturma veri (.vsp) dosyaları çözümlenen rapor (.vsps) dosyaları olarak filtrelenmiş veya filtrelenmemiş görünümlerini kaydedebilirsiniz. Çözümlenen rapor dosyası rapor görünümü penceresinde görüntülenebilir ve önemli ölçüde özgün .vsp dosyadan daha küçüktür. Ancak, bir .vsps dosya verileri için bir filtre uygulayamazsınız. Tümleşik geliştirme ortamı (IDE) dosyasını açmadan performans Gezgini'nden çözümlenen rapor dosyası oluşturabilir veya açabilir ve .vsp dosyasında filtre ve sonuçları kaydedin.  
  
#### <a name="to-save-an-analyzed-performance-report-from-the-performance-explorer"></a>Performans Gezgini'nden bir çözümlenen performans raporu kaydetmek için  
  
1.  Altında **raporları**, analiz edin ve ardından istediğiniz profil oluşturma veri dosyasını sağ tıklatın **Kaydet analiz**.  
  
2.  İçinde **analiz verilerini Kaydet** iletişim kutusunda, dizini belirtin ve sonra dosya adı yazın.  
  
3.  Tıklatın **kaydedin.**  
  
#### <a name="to-save-an-analyzed-performance-report-from-the-report-view-window"></a>Rapor Görünümü penceresinden çözümlenen performans raporu kaydetmek için  
  
1.  Profil oluşturma veri (.vsp) dosyası rapor görünümü penceresi açın.  
  
2.  (İsteğe bağlı) Filtre verileri uygulayın. Daha fazla bilgi için bkz: [performans Rapor Görünümü Filtresi](../profiling/performance-report-view-filter.md).  
  
3.  Tıklatın **Kaydet analiz** rapor görünümü penceresi araç çubuğunda.  
  
4.  İçinde **analiz verilerini Kaydet** iletişim kutusunda, dizini belirtin ve sonra dosya adı yazın.  
  
5.  Tıklatın **kaydedin.**  
  
## <a name="how-to-export-profiling-tools-reports-to-an-xml-or-csv-file"></a>Nasıl yapılır: verme profil oluşturma araçları raporları bir. XML veya. CSV dosyası  
 Bir veya daha fazla rapor görünümlerini .vsp dosya veya bir .vsps profil oluşturma veri dosyası da bir virgülle ayrılmış olarak veya bir XML dosyasına aktarabilirsiniz. Rapor görünümü penceredeki verileri vermeniz ya da tüm veri dosyasından rapor görünümlerini verebilirsiniz önce filtreleyebilirsiniz **performans Gezgini** penceresi.  
  
> [!NOTE]
>  Ayrıca, kopyalamak ve rapor görünümü penceresinde seçili satırlar sekmeyle ayrılmış değerler olarak Yapıştır.  
  
#### <a name="to-export-performance-reports-from-the-performance-explorer-window"></a>Performans raporları performans Gezgini penceresinden dışarı aktarmak için  
  
1.  İçinde **performans Gezgini**, raporu seçin ve ardından sağ tıklatın ve seçin **verme**.  
  
     **Raporu ver** iletişim kutusu görüntülenir.  
  
2.  Dışarı aktarmak istediğiniz rapor görünümleri seçin.  
  
3.  Altında **önek raporla**, rapor adı eklemek istediğiniz öneki belirtin.  
  
4.  Altında **dışarı rapor konumu**, dizini belirtin.  
  
5.  Altında **verilebilir rapor biçiminde**, (virgülle ayrılmış) seçeneğini belirleyin (\*.csv\), veya XML verilerini (\*.xml\).  
  
6.  Tıklatın **verme**.  
  
     Her rapor görünümü adlı ayrı bir dosyaya kaydedilir \<öneki > _\<rapor görünümü adı >.\< CSV &#124; xml >  
  
#### <a name="to-export-performance-reports-from-the-report-view-window"></a>Performans raporları rapor görünümü penceresinden dışarı aktarmak için  
  
1.  .Vsp dosya rapor görünümü penceresi açın.  
  
2.  (İsteğe bağlı) Filtre verileri uygulayın. Daha fazla bilgi için bkz: [performans Rapor Görünümü Filtresi](../profiling/performance-report-view-filter.md).  
  
3.  Tıklatın **raporu ver** rapor görünümü penceresi araç çubuğunda.  
  
4.  Dışarı aktarmak istediğiniz rapor görünümleri seçin.  
  
5.  Altında **önek raporla**, rapor adı eklemek istediğiniz öneki belirtin.  
  
6.  Altında **dışarı rapor konumu**, dizini belirtin.  
  
7.  Altında **verilebilir rapor biçiminde**, (virgülle ayrılmış) seçeneğini belirleyin (\*.csv), veya XML verilerini (\*.xml).  
  
8.  Tıklatın **verme**.  
  
     Her rapor görünümü adlı ayrı bir dosyaya kaydedilir \<öneki > _\<rapor görünümü adı >.\< CSV &#124; xml >  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans Gezgini](../profiling/performance-explorer.md)   
 [Araçları verilerini performansını analiz etme](../profiling/analyzing-performance-tools-data.md)   
 [Performans veri dosyalarını karşılaştırma](../profiling/comparing-performance-data-files.md)   
 [VSPerfReport](../profiling/vsperfreport.md)
