---
title: "Özet görünümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.summary
helpviewer_keywords:
- performance reports, summary view
- profiling tools reports, Summary view
- profiling tools, Summary view
- Summary view
ms.assetid: 98a1eb71-bbf5-4ce7-8559-cdc29f082c4b
caps.latest.revision: "37"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f07b924c5af117f39e19dc5add6046a14be22a6b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="summary-view"></a>Özet Görünümü
Özet görünümü profil çalıştırılmasıyla en performans pahalı işlevleri veya nesneler hakkındaki bilgileri görüntüler. Bu görünüm bir zaman çizelgesi grafik sağlar ve iki veya daha fazla listesi en pahalı işlevleri veya nesneler profil oluşturma yöntemi, performans ölçümleri temelinde. Bu görünümde veri kullanılan profil yöntemine bağlıdır (örnekleme, izleme veya eşzamanlılık) ve .NET bellek ayırma olup toplanan.  
  
 Eşzamanlılık verileri Özet görünümünü dışındaki tüm Özet görünümleri için Özet görünümü zaman çizelgesi grafiğinde profil oluştu zamanla profili uygulama işlemci (CPU) kullanımını gösterir.  
  
-   Grafikte zaman kesimini belirtirseniz, bu kesimi için verileri yeniden Çözümle ya da belirttiğiniz kesim zaman çizelgesi görüntü Yakınlaştır. Daha fazla bilgi için bkz: [nasıl yapılır: Özet zaman çizelgesi filtre rapor görünümleri](../profiling/how-to-filter-report-views-from-the-summary-timeline.md)  
  
-   Bir işlev işlevi için işlev Ayrıntıları görünümü açmak için bir Özet görünümü listesinde tıklatabilirsiniz. Ayrıca, diğer görünüm seçeneklerini işlevi sağ.  
  
-   Özet görünümü listelerinde görüntülenen öğe sayısını değiştirmek için açık **Araçları** menüsündeki **seçenekleri**ve ardından **performans araçları**. Altında **genel ayarları**, değişiklik **Özet görünümü işlevlerde sayısı** ayarı.  
  
## <a name="notifications-links"></a>Bildirimleri bağlantılar  
 Rapor için görüntüleme seçeneklerini ayarlamak için bildirim listesinde bağlantıları tıklatabilirsiniz. Zaman Çizelgesi grafiğin sağına listesidir.  
  
|||  
|-|-|  
|**Kullanıcı olmayan kod Göster**<br /><br /> **Yalnızca kendi kodum Göster**|Yerel kod veya izleme metodunu kullanarak toplanan verileri profil için mevcut değil. Yalnızca kullanıcı kodu verileri görüntüleme arasında geçiş yapar (**Göster sadece kendi kodumu**) ve sistem kodu da dahil olmak üzere tüm kodundan verileri görüntüleme (**Göster kullanıcı olmayan kod**). Varsayılan olarak, veriler için kullanıcı kodu sınırlıdır. Ayarını değiştirmek için bkz: [nasıl yapılır: görüntü sadece kendi kodumu için filtre profil oluşturma Araçlar rapor görünümlerini](../profiling/how-to-filter-profiling-tools-report-views-to-display-just-my-code.md).|  
|**Görünüm Kılavuzu**|Performans kuralı uyarıları görüntüler **hata listesi** penceresi. Daha fazla bilgi için bkz: [verileri çözümlemek için performans kurallarını kullanma](../profiling/using-performance-rules-to-analyze-data.md)|  
  
## <a name="report"></a>Rapor  
 Farklı görünümleri açmak için ve karşılaştırmak, kaydetmek veya raporu filtrelemek için rapor listesi bağlantılara tıklayabilirsiniz. Zaman Çizelgesi grafiğin sağına listesidir.  
  
|||  
|-|-|  
|**Bölünen çağrı ağacı Göster**|En ucuz yürütme yollarını çağrı ağaç görünümünde görüntüler. Daha fazla bilgi için bkz: [çağrı ağacı görünümü](../profiling/call-tree-view.md).|  
|**Etkin satırları göster**|Profil oluşturma araçları yöntemi kullanılarak toplanan veriler için kullanılamaz. En ucuz kaynak kod satırlarını satırları görünümünde görüntüler. Daha fazla bilgi için bkz: [satırlar görünümü](../profiling/lines-view.md).|  
|**Raporları Karşılaştır**|Görüntüler **karşılaştırma için analiz dosyaları seçin** geçerli dosyasına karşılaştırmak için başka bir profil oluşturma veri dosyası belirtebileceğiniz iletişim kutusu. Daha fazla bilgi için bkz: [performans veri dosyalarını karşılaştırma](../profiling/comparing-performance-data-files.md).|  
|**Rapor verilerini dışa aktarma**|Görüntüler **raporu ver** virgülle ayrılmış değer (.csv) veya .xml dosyaları olarak kaydetmek için bir veya daha fazla rapor görünümlerini belirtebileceğiniz iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: profil oluşturma araçları raporları verme](http://msdn.microsoft.com/en-us/174b5bd3-df9b-4fd4-88d4-76032ab90451).|  
|**Çözümlenen raporu kaydedin**|Geçerli profil oluşturma veri dosyası arabirimdeki daha hızlı açılır .vsps dosyası olarak kaydeder [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: kayıt analiz profil oluşturma veri dosyaları](http://msdn.microsoft.com/en-us/0340ddde-caf4-48ac-8af3-d15dcdade556).|  
|**Rapor verileri filtreleme**|Rapor görünümünde verileri sınırlandırmak için ölçüt belirtebileceğiniz profil oluşturma rapor Filtre bölmesini görüntüler. Daha fazla bilgi için bkz: [performans Rapor Görünümü Filtresi](../profiling/performance-report-view-filter.md)|  
|**İki durumlu tam ekran**|Rapor görünümü için tam ekran moduna geçiş yapar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özet görünümü](../profiling/summary-view-sampling-data.md)   
 [Özet görünümü](../profiling/summary-view-instrumentation-data.md)   
 [Özet görünümü](../profiling/summary-view-dotnet-memory-data.md)