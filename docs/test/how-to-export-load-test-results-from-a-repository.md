---
title: Visual Studio Yük testi sonuçlarını dışarı aktarma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load tests, exporting results
- Load Test Results Repository
- load test results, exporting
ms.assetid: 716c2af5-8737-4d31-956f-a0273f7c5c0c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 3da70b7c8c476125478fef2497f084ba4a638a03
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31969635"
---
# <a name="how-to-export-load-test-results-from-a-repository"></a>Nasıl yapılır: Yük Testi Sonuçlarını bir Depodan Dışarı Aktarma

Bir yük testi çalıştırdığınızda, çalışma sırasında toplanan bilgiler yük testi sonuçları deposunda saklanır. Yük testi sonuçları havuzu performans sayacı verilerini ve hatalar hakkında bilgi içerir. Daha fazla bilgi için bkz: [yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md).

Yük testi sonuçlarını kullanarak Yük Testi Düzenleyicisi'nden yönetebilirsiniz **yük testi sonuçlarını yönetme ve Aç** iletişim kutusu. Açın, içeri aktarma, dışarı aktarma ve yük testi sonuçlarını kaldırın.

## <a name="to-export-results-from-a-repository"></a>Sonuçlarını bir depodan dışarı aktarmak için

1.  Bir Web performansı ve yük testi projesinden, bir yük testi açın.

2.  Katıştırılmış araç çubuğunda seçin **açın ve sonuçlarını yönetme**.

     **Açın ve yük testi sonuçlarını yönetme** iletişim kutusu görüntülenir.

3.  İçinde **yük testi sonuçlarını bulmak için bir denetleyici adı girin**, bir denetleyici seçin. Seçin  **\<yerel - denetleyicisi yok >** yerel olarak depolanan sonuçlara ulaşmak için.

4.  İçinde **göstermek için aşağıdaki yük testi sonuçları**, sonuçları görüntülemek istediğiniz yükleme testini seçin. Seçin  **\<tüm testleri için sonuçları göstermek >** tüm testler için tüm sonuçları görmek için.

     Yük testi sonuçlarını varsa, görüntülendikleri **yük testi sonuçlarını** listesi. Sütunlar **zaman**, **süresi**, **kullanıcı**, **sonucu**, **Test**, ve  **Açıklama**. **Test** test adını içerir ve **açıklama** testini çalıştırmadan önce eklemiş isteğe bağlı bir açıklama içerir. **Açıklama** sütunu içindeki girilen kısa açıklamaları görüntüler **çözümleme açıklamaları** bu test sonucu.

5.  İçinde **yük testi sonuçlarını** listesinde, bir sonuç seçin. Birden fazla sonuç seçmek için SHIFT tuşunu, Ctrl tuşunu veya her ikisini de kullanın ve tek bir dosyaya dışarı aktarabilirsiniz.

6.  Seçin **verme**.

     **Yük testi sonuçlarını dışarı** iletişim kutusu görüntülenir.

7.  İçinde **dosya adı** kutusuna bir ad yazın ve ardından **kaydetmek**.

     Sonuçları bir arşiv dosyasına dışarı aktarılır.

    > [!NOTE]
    > **Açın ve yük testi sonuçlarını yönetme** sonuçlar göründükten sonra iletişim kutusunu açık kalır.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Nasıl yapılır: yük testi sonuçlarını bir depodan silme](../test/how-to-delete-load-test-results-from-a-repository.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Nasıl yapılır: yük testi sonuçlarını bir depoya içeri aktarma](../test/how-to-import-load-test-results-into-a-repository.md)