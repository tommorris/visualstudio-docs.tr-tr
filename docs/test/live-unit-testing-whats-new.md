---
title: Dinamik birim testi yenilikler | Microsoft Docs
ms.date: 10-11-2017
ms.technology: vs-devops-test
ms.topic: article
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
- Live Unit Testing What's New
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58e3d44e1644c8582ee423cc4c1572af21efe763
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="whats-new-in-live-unit-testing"></a>Dinamik birim testi yenilikler nelerdir?

Bu konuda dinamik birim testi için Visual Studio 2017 sürüm 15.3 başlangıç Visual Studio'nun her bir sürümde eklenen yeni özellikler listelenmiştir. Birim testi Canlı kullanma genel bakış için bkz: [Canlı birim testi Visual Studio 2017](live-unit-testing.md).

## <a name="whats-new-in-live-unit-testing-for-visual-studio-2017-version-154"></a>Canlı birim test etmek için Visual Studio 2017 sürüm 15.4 yenilikleri

Visual Studio 2017 sürüm 15.4 başlayarak, Canlı birim testi yenilikleri ve geliştirmeleri alanları sayısında içerir:

- **Geliştirilmiş bulunabilirliği**. Bilmiyorsanız kullanıcılar için Canlı birim özelliği yoksa, testi Visual Studio IDE Canlı birim testi birim testleri içeren bir çözüm kullanıcı açar ancak dinamik birim testi etkin olduğunda ilgili bir altın çubuğunu gösterir. Altın çubuğunda sunulan bilgiler Canlı birim testi hakkında daha fazla bilgi için ve etkinleştirmek için kullanıcının sağlar. Birim testi Canlı Önkoşullar karşılanmadı zaman altın çubuğu bilgileri de görüntüler. Bu güncelleştirmeler şunlardır:

   - Test bağdaştırıcıları eksik.
   - Test bağdaştırıcıları eski sürümleri mevcuttur.
   - Çözüm tarafından başvurulan NuGet paketleri geri yüklemeye gereklidir. 

- **Görev Merkezi bildirimlerini ile tümleştirme**. Visual Studio IDE artık kullanıcıların kolayca Canlı birim testi etkinleştirildiğinde neler yapıp yapmadığını bildirim görev Merkezi'nde bir canlı birim testi arka plan işlemleri gösterir. Bu, büyük bir çözüm üzerinde dinamik birim testi başlatma anahtar sorunu giderir. Kapsamı simgeler görünen kadar daha önce birkaç dakika kullanıcılar olup Canlı birim testi gerçekten etkinleştirildi ve olup çalıştığı belirlenemedi. Artık değil!

- **Mstest'i framework sürüm 1 desteği**: birim testi Canlı zaten üç popüler birim test çerçevelerini ile çalışır: xUnit, NUnit ve mstest'i. Mstest'i birim testi projelerini MS Test version 2 kullanıldığında daha önce Canlı birim testi yalnızca çalışmıştır. Visual Studio 2017 sürüm 15.4 başlayarak, şimdi de mstest'i sürüm 1 de destekler. 

- **Güvenilirlik ve performans**: birim testi Canlı şimdi sağlar sistem projeleri tam yüklemesi tamamlandı henüz daha iyi algılayabilir ve canlı birim testi kilitlenen önler. Performans derleme geliştirmeleri ayrıca kaçının MSBuild proje dosyası projeye hiçbir şey değişti sistem bilir zaman reevaluating.  

- **Çeşitli kullanıcı arabirimi iyileştirmelerini**: kafa karıştırıcı **Canlı Test ayarlama – ekleme/çıkarma** sağ tıklatma hareketi seçeneğinden adlandırılmıştır **Canlı birim testleri ekleme/çıkarma**. **Temiz sıfırlama** seçeneği **Test**, **Canlı birim testi** menü kaldırıldı. Şimdi seçerek erişilebilir olduğu **Araçları**, **seçenekleri**, **Canlı birim testi** ve seçerek **kalıcı verileri Sil**.

## <a name="whats-new-in-live-unit-testing-for-visual-studio-2017-version-153"></a>Canlı birim test etmek için Visual Studio 2017 sürüm 15.3 yenilikleri

Visual Studio 2017 sürüm 15.3, Canlı birim testi özellikleri geliştirmeleri ve iki ana alanlarda geliştirmeler başlatılıyor:

- .NET Core ve .NET standart desteği. C# veya Visual Basic yazılan .NET Core ve .NET standart çözümler hakkında Canlı birim testi'ı kullanabilirsiniz.
 
-  Performans iyileştirmeleri. İlk tam yapı ve test Canlı birim testi altında çalıştırdıktan sonra performansı önemli ölçüde daha hızlı olduğunu fark edeceksiniz. Ayrıca, önemli performans geliştirmesinden sonraki başlatır Canlı birim sınama aynı çözüm üzerinde görürsünüz. Biz artık canlı birim testi tarafından oluşturulan veri kalıcı hale getirmek ve güncel denetimlerle mümkün olduğunca yeniden. 
 
Başlıca Bu eklemeleri ek olarak birim testi Canlı aşağıdaki geliştirmeleri içerir: 

- Yeni bir beaker simgesi artık test yöntemi normal yöntemleri ayırt etmek için kullanılır. Boş beaker simge birim testine Canlı belirli test dahil edilmeyen gösterir. 

- Test yöntemi bir canlı birim testi kapsamı simgesinin açılır UI penceresinden tıklandığında, artık bu bağlam UI penceresi içinde ve Kod Düzenleyicisi'nden çıkmak zorunda kalmadan testten sağ hata ayıklama seçeneğiniz vardır. Bu, özellikle bir başarısız test ararken kullanışlıdır.  

- Birkaç ek yapılandırılabilir seçeneklerin Araçlar/Seçenekler/Canlı birim test/genel eklenmiştir. Canlı birim test etmek için kullanılan bellek cap. Açık çözümünüz için kalıcı birim testi canlı verileri için dosya yolu da belirtebilirsiniz. 

- Menü çubuğunda, Test/Canlı birim testi altında birkaç ek menü öğelerini eklenmiştir. **Temiz sıfırlama** kalıcı veri siler ve yeniden oluşturur. **Seçenek** Araçlar/Seçenekler/Canlı birim test/genel atlar.
  
- Aşağıdaki öznitelikler artık canlı birim testi hedeflenen test yöntemleri dışlamak istediğiniz kaynak kodunda belirtmek için de kullanabilirsiniz:
   - XUnit için:`[Trait("Category", "SkipWhenLiveUnitTesting")]`
   - NUnit için:`[Category("SkipWhenLiveUnitTesting")]`
   - Mstest'i için:`[TestCategory("SkipWhenLiveUnitTesting")]`

## <a name="see-also"></a>Ayrıca bkz.
[Dinamik birim testi Tanıtımı](live-unit-testing-intro.md)   
[Dinamik birim ile Visual Studio 2017 testi](live-unit-testing.md)

