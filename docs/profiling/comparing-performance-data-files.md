---
title: Performans veri dosyalarını karşılaştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, comparing profiling tools report files
- profiling tools reports, comparing
ms.assetid: e6fda144-f21d-4912-9d16-1b8d3555a210
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b56982cdef9c27beb4e5aeb82fa9d9741e87fbd7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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