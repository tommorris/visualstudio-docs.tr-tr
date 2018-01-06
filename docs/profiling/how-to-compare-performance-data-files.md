---
title: "Nasıl yapılır: performans veri dosyalarını karşılaştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vsperf.choosediffbinaries
helpviewer_keywords:
- profiling tools, how to compare profiler result files
- profiler result files, how to compare
ms.assetid: 1905b45d-c6b3-43c8-87b1-1aee734f37f9
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 09e16202fb1b35a48925297e35840a60b65f0488
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-compare-performance-data-files"></a>Nasıl yapılır: performans veri dosyalarını karşılaştırma
Bir karşılaştırma ("fark") raporu ya da görünüm oluşturarak iki farklı profil oluşturucu veri dosyalarını (.vsp veya .vsps) sonuçlarını karşılaştırabilirsiniz. Karşılaştırma farkları, performans gerileme ve diğer bir profil oluşturma oturumu oluştu iyileştirmeleri gösterir.  
  
 Diff rapor verileri içeren bir tablo görünümü gösterir. Tablo delta veya taban çizgisiyle değişiklik gösterir. Bu, yeni analiz eski değer, taban çizgisi değeri ve sonuç değeri arasındaki farkı belirleyerek hesaplanır.  
  
 Profil Oluşturucu veri karşılaştırmaları temel işlevleri kodda, uygulama, satırları, yönerge işaretçileri (IP) ve türleri modülleri alabilir.  
  
 Bir eşik gürültü azaltmak ve herhangi bir veri değişip değişmediğini satır Tablo görünümünde filtrelemek için belirli bir miktarda ayarlanabilir.  
  
### <a name="to-create-comparison-file-view-for-a-project-in-performance-explorer"></a>Performans Gezgini içinde bir proje için karşılaştırma dosya görünümü oluşturmak için  
  
1.  İçinde **performans Gezgini**altında **raporları**, karşılaştırma için temel değerleri olarak kullanmak istediğiniz .vsp veya .vsps rapor dosyası seçin.  
  
2.  Karşılaştırmak istediğiniz .vsp veya .vsps rapor dosyaları seçin.  
  
3.  Seçili dosyaları birine sağ tıklayın ve ardından **karşılaştırmak raporları**.  
  
### <a name="to-compare-values"></a>Değerleri karşılaştırmak için  
  
1.  Seçin **Karşılaştırma raporu** rapor görünümü penceresi sekmesindedir.  
  
2.  İçinde **tablo** aşağı açılan listesinde, işlev veya karşılaştırmak için modülleri seçin.  
  
3.  İçinde **sütun** aşağı açılan listesinde, karşılaştırmak istediğiniz değeri seçin.  
  
4.  (isteğe bağlı) İçin bir değer yazın **eşik**.  
  
5.  Tıklatın **uygulamak**.  
  
### <a name="to-compare-report-files"></a>Rapor dosyalarını karşılaştırma  
  
1.  Üzerinde **Çözümle** menüsünde, select **karşılaştırmak performans raporları**.  
  
2.  İçinde **karşılaştırma için analiz dosyaları seçin** penceresi, göz atma ve seçme **temel dosya** analiz dosyası (.vsp veya .vsps) ve **karşılaştırma dosya** (.vsp veya .vsps).  
  
3.  **Tamam**'ı tıklatın.