---
title: "DA0018: 32 bitlik uygulama işlem sırasında çalışan yönetilen bellek sınırları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.18
- vs.performance.DA0018
- vs.performance.rules.DA0018
ms.assetid: 98eb2d96-f92f-42f9-915c-e5ac2330ffbf
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: e826619a9b8b6b9109c28381b6b9f05cb37b4094
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0018-32-bit-application-running-at-process-managed-memory-limits"></a>DA0018: 32 bitlik Uygulama işlem tarafından yönetilen bellek sınırlarında çalışıyor
|||  
|-|-|  
|Kural Kimliği|DA0018|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemi|Örnekleme|  
|İleti|Bellek ayırma 32 bitlik bir işlem için varsayılan sınırına yaklaşılıyor yönetilen. Uygulamanızı bellek bağlı olabilir.|  
|Kural türü|Uyarı|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma çalışması sırasında toplanan sistem verilerini, .NET Framework bellek yığınlardaki Yönetilen yığın bir 32 bit işlemde ulaşabileceği en büyük boyutu yaklaşıldığında gösterir. Bu maksimum boyutu varsayılan değerdir. Özel bayt için ayrılan işlem adres alanının toplam miktarını dayanır. Bildirilen değer profili işlem etkinken maksimum yığın değerini gözlenir. .NET bellek profili oluşturma yöntemi kullanarak yeniden ve uygulama tarafından yönetilen kaynaklarının kullanımını en iyi duruma getirme profil göz önünde bulundurun.  
  
 Varsayılan sınır yönetilen boyutunu yığınlardaki yaklaşımını olduğunda otomatik atık toplama işlemi daha sık çağrılacak olabilir. Bu bellek yönetim yükünü artırır.  
  
 Kuralın yalnızca 32-bit makine üzerinde çalışan 32-bit uygulamalar için ateşlenir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Microsoft .NET ortak dil çalışma zamanı (CLR) uygulama artık kullanır nesneleri belleği geri almasını atık toplayıcı kullanan bir otomatik bellek yönetimi mekanizması sağlar. Çöp toplayıcı nesil odaklı birçok ayırmaları kısa süreli duymadığını ' dir. Yerel değişkenler, örneğin, kısa süreli olmalıdır. Yeni oluşturulan nesneleri oluşturma 0 (gen 0) başlatın ve bunlar uygulama hala bunları kullanıyorsa, ne zaman bunlar bir atık toplama çalıştırın ve son olarak 2. nesil geçiş varlığını sürdürmesini 1. nesil için ilerleme durumu.  
  
 85 KB'den büyük yönetilen nesneler üzerinde daha az sıklıkta çöp toplama ve daha küçük nesneleri sıkıştırma tabi oldukları büyük nesne yığın ayrılır. Daha fazla kalıcı ve kalıcı ve büyük karıştırma çünkü nesneleri sık ayrılmış küçük nesnelerle öbek en kötü atama parçalanma üretebilir varsayıldığından büyük nesneler ayrı olarak yönetilir.  
  
 Yönetilen toplam boyutunu yığınlardaki yaklaşımını varsayılan sınır, bellek yönetim yükünü genellikle, yanıtlama ve uygulama ölçeklenebilirliğini etkileyen başlayabileceğiniz noktasına artar.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Gitmek için hata listesi penceresini iletisinde çift [işaretleri](../profiling/marks-view.md) görünümü. Bul **.NET CLR bellek\\# yığınlardaki bayt** ve **# kaydedilmiş bayt toplam** sütun. Olup olmadığını program yürütme belirli aşamaları yönetilen bellek ayırma diğer aşamalar ağır olduğu belirler. Değerleri Karşılaştır **# yığınlardaki bayt** çöp toplama oranını sütununa bildirilen **.NET CLR bellek\\# Gen 0 koleksiyonları**, **.NET CLR bellek\\# Gen 1 koleksiyonları**, ve **.NET CLR bellek\\# Gen 2 koleksiyonları** sütunları yönetilen bellek ayırmaları desenini çöp oranını söz konusu belirlemek için koleksiyonu.  
  
 Bir .NET Framework uygulamasında ortak dil çalışma zamanı yönetilen yığınlardaki biraz daha az toplam boyutu sınırlar uzunluğunun yarısı işlem adres alanı özel alanı kısmı en büyük boyutunu daha. Bir 32-bit makine üzerinde çalışan 32 bit işlemler için işlem adres alanı özel bölümünü sayısı üst sınırı 2 GB temsil eder. Yönetilen yığın toplam boyutu, varsayılan sınırına yaklaşımlardan başladığında, bellek yönetme ek yükünü artırabilir ve uygulama performansının düşmesine neden olur.  
  
 Aşırı yönetilen bellek yükü bir sorun varsa, bu seçeneklerden birini göz önünde bulundurun:  
  
-   uygulamanın yönetilen bellek kaynaklarının kullanımını en iyi duruma getirme  
  
     veya  
  
-   sanal bellek 32 bitlik bir işlem için en büyük boyutunu mimari kısıtlamalar hafifletmek için adımları alma  
  
 Uygulamanın yönetilen bellek kaynaklarının kullanımını en iyi duruma getirmek için bir çalıştırmak, .NET bellek ayırma profil yönetilen bellek ayırma verileri toplayın. Gözden geçirme [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md) bellek ayırma uygulama desenini anlamak için raporlar.  
  
 Kullanım [nesne ömrü görünümü](../profiling/object-lifetime-view.md) hangi programın veri nesneleri oluşturma ve ardından buradan iadesi halinde sürdüren belirleme.  
  
 Kullanım [ayırmalar görünümü](../profiling/dotnet-memory-allocations-view.md) bu ayırma sonuçlandı yürütme yolu belirlenemedi.  
  
 .NET Framework teknik makalesi, atık toplama performansı hakkında daha fazla bilgi için bkz: [atık toplayıcı temel kavramları ve performans ipuçları](http://go.microsoft.com/fwlink/?LinkId=177946) MSDN Web sitesinde.  
  
 Bir işlem adres alanı özel kısmının boyutu sanal bellek kısıtlamaları gelen mimari Tahliye kazanmak için bu 32-bit işlem bir 64-bit makine üzerinde çalışan deneyin.  Bir 64-bit makine üzerindeki 32-bit işlem en fazla 4 GB özel sanal bellek elde edebilirsiniz.  
  
 64 bitlik bir işlem bir 64-bit makine üzerinde çalışan sanal bellek 8 TB'ye kadar elde edebilirsiniz. Yerel 64 bitlik bir uygulama çalıştırmak için uygulamayı yeniden derlemeyi düşünün. Bu kural, yalnızca bilgi amaçlıdır ve düzeltme eylemi gerektirmeyebilecek.