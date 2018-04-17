---
title: Performans Rapor Görünümü Filtresi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, Profiler Report view filter
- Profiler Report View filter, profiling tools
ms.assetid: 35f89d86-4683-4db1-aa0c-ae0ce65fa524
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47c4a754b680b032b790f225b1cbc4a75a69fc08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="performance-report-view-filter"></a>Performans Rapor Görünümü Filtresi
Profil Oluşturucusu Rapor Görünümü Filtresi penceresi performans raporu penceresinin en üstünde yer alır. Göremiyorsanız, tıklatın **Göster filtre** düğmesi.  
  
 Sonuçlarınızı daraltmak için her filtre yan tümcesi değiştirebilirsiniz. Aşağıdaki sütunlar filtresi Oluşturucu'da kullanılabilir.  
  
|Filtre öğesi|Açıklama|  
|-----------------|-----------------|  
|Ve/veya|Seçin **ve** bir sonuç eşleşiyorsa bu yan tümce sonraki yan tümcesi hem de girintili için olmalıdır. Seçin **veya** bir sonuç eşleşiyorsa bu yan tümcesi veya sonraki yan tümcesi girintili olabilir.|  
|Alan|Alanın filtre yan tümcesi geçerli rapor dosyasında kullanılabilir veri alanları listesinden kullanmak için seçin.|  
|İşleç|Alan ve değer arasında istediğiniz ilişkiyi belirten işleci seçin.<br /><br /> = Eşittir<br /><br /> <> Eşit değildir<br /><br /> < Küçüktür<br /><br /> > Büyüktür<br /><br /> < = küçüktür veya eşittir<br /><br /> > = büyüktür veya eşittir|  
|Değer|Aranacak bir değer girin veya seçin. Bazı alanları alan için kullanılabilir değerleri listeler.|  
  
 Filtre en iyi sonuçlar verir düşündüğünüz kadar filtre yan tümcesi ekleyebilirsiniz. Tıklatın **yürütme filtre** veri dosyasına filtre uygulamak için.  
  
 Gelen **işaretleri** rapor görünümü, verileri iki işaretleri arasında toplanan veriler için rapor görünümlerini sınırlandırmak için filtre yan tümcesi oluşturabilir. Başlangıç ve bitiş verileri, sonra sağ tıklatın ve seçin raporu istediğiniz işaretleri seçin **işaretleri üzerinde filtre Ekle** veya **zaman damgaları üzerinde filtre Ekle**. Her iki süzgeçleri aynı aralığa geçerli veri dosyasındaki verilerin sınırlar; **İşaretleri üzerinde filtre Ekle** diğer .vsp dosyalara uygulanabilir.  
  
 Filtre kaydetmek için tıklatın **verme filtresi** performans raporu araç çubuğunda ve .vspf dosyanın konumu ve dosya adını belirtin. Daha önce kaydedilen bir filtreyi yüklemek için tıklayın **alma filtresi** ve kaydedilmiş filtre dosyasını bulun. Filtre dosyalar, veri dosyalarını bağımsız profil oluşturma araçları yüklü olan bilgisayarlarda filtre uygulamak için de kullanılabilir. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araçları verilerini performansını analiz etme](../profiling/analyzing-performance-tools-data.md)   
 [VSPerfReport](../profiling/vsperfreport.md)