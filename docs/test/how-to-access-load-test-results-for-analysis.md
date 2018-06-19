---
title: Visual Studio Yük testi sonuçlarını çözümleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load test results, accessing
- Load Test Viewer
- load tests, accessing
- load tests, analyzing
- load tests, results
- Load Test Viewer, viewing
ms.assetid: b0a3e694-2894-479b-b270-7e61e9fafacd
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: d20754bc61a003b1b7f6d1eb84ce419c2c6e442b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31966693"
---
# <a name="how-to-access-load-test-results-for-analysis"></a>Nasıl yapılır: Çözümleme için Yük Testi Sonuçlarına Erişme

Yük Testi Düzenleyicisi'nden bir yük testi çalıştırdığınızda yük testi sonuçları otomatik olarak açılır ve çalışan yük testi Yük Testi Çözümleyicisi'nde görüntülenir. Komut satırından bir yük testi çalıştırdığınızda, yük testi sonuçlarını el ile erişmeniz gerekir.

Yük testi sonucu Tamamlanan yük testi için performans sayacı örneklerinin ve düzenli olarak test altında bilgisayarlardan toplanan hata bilgilerini içerir. Çok sayıda performans sayacı örneklerinin bir yük testi süresince toplanabilir. Toplanan performans veri miktarı, örnekleme aralığı, test bilgisayar sayısı, toplanmakta olan sayaç sayısı, yapılandırılan veri toplayıcıları ve günlük düzeylerini testi uzunluğuna bağlıdır. Büyük yük testi için toplanan performans veri miktarı kolayca birkaç gigabayt olabilir. Daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

## <a name="to-access-a-load-test-result"></a>Bir yük testi sonuç erişmek için

1.  Bir Web performansı ve yük testi projesinden, bir yük testi açın.

2.  Yük Testi Düzenleyicisi araç çubuğunda seçin **açın ve sonuçlarını yönetme** düğmesi.

     **Açın ve sonuçlarını yönetme** iletişim kutusu görüntülenir.

3.  İçinde **yük testi sonuçlarını bulmak için bir denetleyici adı girin**, bir denetleyici seçin. Seçin  **\<yerel >-hiçbir denetleyicisi** yerel olarak depolanan sonuçlara ulaşmak için.

4.  İçinde **göstermek için aşağıdaki yük testi sonuçları**, sonuçları görüntülemek istediğiniz yükleme testini seçin. Seçin  **\<tüm testleri için sonuçları göstermek >** tüm testler için tüm sonuçları görmek için.

     Yük testi sonuçlarını yoksa görüntülendikleri **yük testi sonuçlarını** listesi. Sütunlar **zaman**, **süresi**, **kullanıcı**, **sonucu**, **Test**, ve  **Açıklama**. **Test** test adını içerir ve **açıklama** testini çalıştırmadan önce eklemiş isteğe bağlı bir açıklama içerir.

    > [!NOTE]
    > Listenin başındaki en son sonuçlarla sonuçları görüntülenir.

5.  İçinde **yük testi sonuçlarını** listesinde, istediğiniz çözümlemek ve seçmek için yük testi sonuçlarını seçin **açık**.

6.  Yük Testi Çözümleyicisi görünür. Seçili yük testi sonucu Özet görünümünde görüntülenir. Daha fazla bilgi için bkz: [yük testi sonuçları özeti genel bakış](../test/load-test-results-summary-overview.md).

     Yük testi sonuçlarını içeri aktarma, dışarı aktarma ve yük testi sonuçlarını kaldırma dahil sonuçları Aç ve Yönet iletişim kutusunda diğer yönlerini yönetebilirsiniz. Daha fazla bilgi için bkz: [yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)