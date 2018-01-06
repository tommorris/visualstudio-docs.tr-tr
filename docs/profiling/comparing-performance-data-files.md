---
title: "Performans veri dosyalarını karşılaştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, comparing profiling tools report files
- profiling tools reports, comparing
ms.assetid: e6fda144-f21d-4912-9d16-1b8d3555a210
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 734d0531cf1fbbbc2f7924cb1743cabf9e4a9578
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-performance-data-files"></a>Performans veri dosyalarını karşılaştırma
Profil oluşturma araçları veri dosyalarını karşılaştırma işlevlerini iki rapor dosyaları seçin olanak tanır (. VSP ya. VSPS) dosyaları ve farkları, performans gerileme ve diğer bir profil oluşturma oturumu oluştu iyileştirmeleri gösteren bir rapor oluşturun.  
  
 Bir karşılaştırma raporu veri dosyalarının [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları dosyasındaki bir profil oluşturma veri başka bir veri dosyasında temel analiz sonuçlarını analiz sonuçlarını karşılaştırır. Her iki veri dosyaları aynı profil oluşturma yöntemini kullanarak oluşturulmuş olmalıdır. Çözümlenen karşılaştırmaları rapor .vsps dosyası olarak kaydedilir.  
  
 Karşılaştırma rapor görünümü değiştirilen verileri içeren bir tablo görünümü gösterir. Tablo delta veya taban çizgisiyle değişiklik gösterir. Delta yeni analiz eski değer, taban çizgisi değeri ve sonuç değeri arasındaki farkı belirleyerek hesaplanır.  
  
 Profil Oluşturucu veri karşılaştırmaları temel işlevleri kodda, uygulama, satırları, yönerge işaretçileri (IP) ve türleri modülleri alabilir.  
  
 Karşılaştırma için mevcut olan verileri profil sütunlarında görüntülenen bilgiler içerir. Bu sütun adları tanımları için bkz: [performans rapor görünümlerini](../profiling/performance-report-views.md).  
  
 Bir eşik gürültü azaltmak ve herhangi bir veri değişip değişmediğini satır karşılaştırma Tablo görünümünde filtrelemek için belirli bir miktarda ayarlanabilir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: performans veri dosyalarını karşılaştırma](../profiling/how-to-compare-performance-data-files.md)