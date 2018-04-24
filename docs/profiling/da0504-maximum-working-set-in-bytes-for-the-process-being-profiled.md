---
title: 'DA0504: En büyük çalışma kümesinin profili oluşturuluyor işlem için bayt cinsinden | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0504
- vs.performance.504
- vs.performance.rules.DA0504
ms.assetid: 36e71603-ece7-4000-85fc-9da4eed61bf2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6bb6c62a785815db0c678d0a1f0ff38ebea14d70
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="da0504-maximum-working-set-in-bytes-for-the-process-being-profiled"></a>DA0504: İşlem için izin verilen Bayt Cinsinden En Büyük Çalışma Kümesinin profili oluşturuluyor
|||  
|-|-|  
|Kural Kimliği|DA0504|  
|Kategori|Kaynak Yönetimi|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Bu bilgiler yalnızca bilgi toplandı. İşlem çalışma kümesi sayaç profil işlem tarafından fiziksel bellek kullanımını ölçer. Değer, en fazla tüm ölçüm aralıklarında gözlenir bildirdi.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu ileti en fazla işlem şu anda kullandığı bayt cinsinden fiziksel bellek miktarını raporlar. İşlem çalışma kümesi şu anda fiziksel bellekte bulunan işlem adres alanından sayfaları temsil eder. Profil oluşturma etkinken bu kural işlemin çalışma kümesi için maksimum değeri bildirir.  
  
 Bildirilen değeri işlem başvurmuş paylaşılan bellek kesimleri yerleşik sayfalarından içerir. İşlem başvuruları sayılan paylaşılan bellek segmentlerinde bulunan paylaşılan dll dosyaları. Değer işlemin çalışma kümesi paylaşılan bellek kesimler nedeniyle işlemin ayırdığı sanal bellek miktarından daha yüksek olabilir.  
  
 İşlemin çalışma kümesi boyutu işlem etkin olarak kullanan ne kadar sanal bellek yansıtır. Fiziksel bellek (veya RAM) miktarı etkilenir uygulama ve fiziksel belleğin için Çekişme diğer çalışan işlemlerini çalıştırmak kullanılabilir. İşlem çalışma kümeleri hakkında daha fazla bilgi için bkz: [çalışma kümesi](http://go.microsoft.com/fwlink/?LinkId=177830) MSDN Windows bellek yönetimi belgelerinde.  
  
## <a name="how-to-use-rule-data"></a>Kural verileri kullanma  
 Kural Windows Performans tesis izleme Bu ölçüm verilerini toplar ve yalnızca bilgi raporlar. Farklı sürümlerini performansını veya programın derlemeleri karşılaştırmak için veya farklı bir test senaryoları altında uygulamanın performansını anlamak için kullanın.  
  
 Gitmek için hata listesi penceresini iletisinde çift [işaretleri Görünüm](../profiling/marks-view.md) profil oluşturma veri. Bul **Process\Working ayarlamak** ve **Bellek\Sayfa/sn** sayaç sütun. En büyük değerini bulmak **Process\Working ayarlamak** ve kendisine karşılaştırma **Bellek\Sayfa/sn** değeri. Özellikle makine bellek kısıtlı sık maksimum küme çalışma azalmasına sayfalama g/ç etkinliğini olduğu zaman aralığı ile ilişkili ise.