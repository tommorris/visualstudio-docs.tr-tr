---
title: "Katman etkileşimleri görünümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.view.tierinteraction
helpviewer_keywords:
- Tier Interactions view
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7246d9ac119885e8a6f736d853cf0b842b84f8c9
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="tier-interactions-view"></a>Katman Etkileşimleri Görünümü

Katman etkileşim profil sağlar, veritabanları ile iletişim kuran çok uygulamaları işlevlerinde yürütme sürelerinin hakkında ek bilgi [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]. Verileri yalnızca zaman uyumlu işlev çağrıları için toplanır.

**Gereksinimler**

- Visual Studio Enterprise

Etkileşimleri görünümü iki bölmelerinde katman etkileşim verileri görüntüler:

- Hiyerarşik bir ana bölmesidir. En üst düzey satırın veritabanı bağlantılarını toplanan verileri içeren bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sayfası veya bir işlem. Alt düğümler üst veritabanı bağlantıları için toplanan veriler içerir.

- Bir veritabanı çağrısı düğüm ana bölmede tıkladığınızda, verileri bir veritabanı çağrısı örneği için Ayrıntılar bölmesinde görüntülenir.

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