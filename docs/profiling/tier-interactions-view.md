---
title: "Katman etkileşimleri görünümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.tierinteraction
helpviewer_keywords: Tier Interactions view
ms.assetid: bb4fb21c-f3f7-473a-8b5e-442da4c2c445
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a42e748e45d7db0606d585d774be254a7358d6b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="tier-interactions-view"></a>Katman Etkileşimleri Görünümü
Katman etkileşim profil sağlar, veritabanları ile iletişim kuran çok uygulamaları işlevlerinde yürütme sürelerinin hakkında ek bilgi [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]. Verileri yalnızca zaman uyumlu işlev çağrıları için toplanır.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)]  
  
 Etkileşimleri görünümü iki bölmelerinde katman etkileşim verileri görüntüler:  
  
-   Hiyerarşik bir ana bölmesidir. En üst düzey satırın veritabanı bağlantılarını toplanan verileri içeren bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sayfası veya bir işlem. Alt düğümler üst veritabanı bağlantıları için toplanan veriler içerir.  
  
-   Bir veritabanı çağrısı düğüm ana bölmede tıkladığınızda, verileri bir veritabanı çağrısı örneği için Ayrıntılar bölmesinde görüntülenir.  
  
 Milisaniye sayısını veya CPU saat sayısı olarak görüntülenir. Görüntülenen zaman birimi değiştirmek için tıklatın. **Araçları** menüsünde tıklatın **seçenekleri**ve ardından aşağıdakilerden birini seçin **Saat gösterme değerleri olarak** seçenekleri.  
  
## <a name="master-pane"></a>Ana bölmesi  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|-Bir üst düzey satır, profili işlem veya Web sayfası adı için.<br />-Veritabanı bağlantısı için bir satır, veritabanını barındıran sunucunun adı.|  
|**Veritabanı**|(Yalnızca veritabanı bağlantısı satırlar) veritabanının adı.|  
|**Sayısı**|İşlem, Web sayfası veya veritabanı bağlantısı tarafından oluşturulan isteklerinin toplam sayısı.|  
|**Geçen toplam süre**|Herhangi bir istek işleme, Web sayfası veya veritabanı bağlantısı yürütmek için geçen toplam süre.|  
|**En fazla geçen süre**|İşlem, Web sayfası veya veritabanı bağlantısı herhangi bir istek yürütülürken harcanan maksimum zamanı.|  
|**Min geçen süre**|İşlem, Web sayfası veya veritabanı bağlantısı herhangi bir istek yürütülürken harcanan en düşük saat.|  
|**Ortalama süre**|İstek işleme, Web sayfası veya veritabanı bağlantısı yürütmek için geçen ortalama süre.|  
  
## <a name="database-connection-details-pane"></a>Veritabanı bağlantı ayrıntıları bölmesi  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Komut metni**|İsteğin SQL sorgusu.|  
|**Sorgu sayısı**|Sorgu çalıştırılma sayısı.|  
|**Geçen toplam süre**|Sorgu örnekleri yürütmek için geçen toplam süre.|  
|**En fazla geçen süre**|Herhangi bir örnek sorgu yürütmek için geçen en uzun süre.|  
|**Min geçen süre**|Herhangi bir örnek sorgu yürütmek için geçen en düşük saat.|  
|**Ortalama süre**|Sorgu örneği yürütmek için geçen ortalama süre.|