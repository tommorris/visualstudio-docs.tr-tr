---
title: 'DA0023: Yüksek GC CPU süresi | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.DA0023
- vs.performance.23
- vs.performance.rules.DA0023
ms.assetid: aba875fe-9cbc-418d-a2c4-6eb47519a5bb
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5cdb5e3ea9e01e6444cf05709138984091c36a6d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689466"
---
# <a name="da0023-high-gc-cpu-time"></a>DA0023: Yüksek GC CPU süresi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DA0023: yüksek GC CPU süresi](https://docs.microsoft.com/visualstudio/profiling/da0023-high-gc-cpu-time).  
  
Kural Kimliği | DA0023 |  
| Kategori |. NET Framework kullanım |  
| Profil oluşturma yöntemi | Tüm |  
| İleti | % gc'de zaman oldukça yüksek. Bu çöp toplama taşması aşırı miktarda göstergesi uygulamanızın yanıt hızını etkiliyor. Uygulamanızın kullandığı daha iyi bellek ayırma desenini anlamak için .NET bellek ayırma verileri ve nesne yaşam süresi bilgilerini toplayabilirsiniz. |  
| Kural türü | Bilgilendirme |  
  
 Örnekleme, .NET bellek ve kaynak çekişmesi yöntemleri kullanılarak profili, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma sırasında toplanan sistem performansı verilerini toplam uygulama işleme süresi ile karşılaştırıldığında, çöp toplamaya harcanan süreyi önemli olduğunu gösterir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Microsoft .NET ortak dil çalışma zamanı (CLR) nesnelerden artık uygulamanın kullandığı belleği geri kazanmak için atık Toplayıcıya kullanan bir otomatik bellek yönetimi mekanizması sağlar. Atık toplayıcı nesil odaklı birçok ayırmaları ömürlüdür varsayımına dayanır. Örneğin, yerel değişkenler, kısa süreli olmalıdır. Yeni oluşturulan nesneleri nesil 0 (gen 0) başlatın ve bunların uygulama yine de bunları kullanıyorsa, ne zaman, bir çöp toplama çalıştırın ve son olarak 2. nesil geçiş varlığını sürdürmesini nesil 1 ilerleme durumu.  
  
 Nesil 0'daki nesneleri, sık ve genellikle çok verimli bir şekilde toplanır. 1. nesil nesneler, daha az sıklıkta ve daha az verimli bir şekilde toplanır. Son olarak, uzun süreli nesneler nesil 2 içinde bile daha az sık toplanması. Tam çöp toplama çalıştırmak olan 2. nesil koleksiyonu da en pahalı bir işlemdir.  
  
 Bu kural, çöp toplamaya harcanan süreyi toplam uygulama işleme süresi ile karşılaştırıldığında önemli olduğunda tetikler.  
  
> [!NOTE]
>  Toplam uygulama işleme süresi ile karşılaştırıldığında oranı çöp toplamaya harcanan süresinin aşırı olduğunda [DA0024: aşırı GC CPU zamanı](../profiling/da0024-excessive-gc-cpu-time.md) yerine bu kural uyarı ateşlenir.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarı araştırma  
 Hata Listesi penceresindeki iletiyi gitmek için çift tıklatın [işaret görünümü](../profiling/marks-view.md) profil oluşturma verilerinin. Bulma **.NET CLR bellek\\% gc'de zaman** sütun. Varsa belirli program yürütme aşamaları çöp toplamanın yönetilen bellek yükü diğer aşamaları ağır olduğu belirleyin. Gc'de zaman % değerlerini değer çöp toplama oranını karşılaştırma bildirilen içinde **Gen 0 toplamaları sayısı**, **Gen 1 toplamaları sayısı**, **Gen 2 toplamaları sayısı** değerleri .  
  
 Bir uygulama işleme toplam tutarı orantılı gerçekleştirme çöp toplama için harcadığı süreyi bildirmek % GC değerindeki zamanı çalışır. Bazı durumlarda % GC değerindeki zamanı çok yüksek bir değere bildirebilirsiniz, ancak nedeniyle aşırı çöp toplama değil unutmayın. % GC değerindeki zamanı hesaplanır biçimi hakkında daha fazla bilgi için bkz. [fark arasındaki performans verileri tarafından bildirilen farklı araçları – 4](http://go.microsoft.com/fwlink/?LinkId=177863) girişi **Maoni'nın blog** MSDN'de. Sayfa hataları ortaya çıkan veya uygulama tarafından diğer daha yüksek öncelikli iş makinede çöp toplama sırasında geçersiz kılınırsa, GC sayacı zaman % bu ek gecikmelere ücreti yansıtılır.



