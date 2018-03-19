---
title: "Nasıl yapılır: Visual Studio'da bir depodan yük testi sonuçlarını silme | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- results, load test
- load tests, deleting results
- load test results, removing
- Load Test Results Repository
- load tests, removing results
- load test results, deleting
ms.assetid: c2afe36b-d061-4f0e-9580-c18569ec08f9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 0bdcc566b17d642ba4de2f476c2e8a96994da6f9
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-delete-load-test-results-from-a-repository"></a>Nasıl yapılır: Bir Depodan Yük Testi Sonuçlarını Silme

Bir yük testi çalıştırdığınızda, çalışma sırasında toplanan bilgiler yük testi sonuçları deposunda saklanır. Yük testi sonuçları havuzu performans sayacı verilerini ve hatalar hakkında bilgi içerir. Daha fazla bilgi için bkz: [yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md).

 Yük testi sonuçlarını kullanarak Yük Testi Düzenleyicisi'nden yönetebilirsiniz **yük testi sonuçlarını yönetme ve Aç** iletişim kutusu. Açın, içeri aktarma, dışarı aktarma ve yük testi sonuçlarını kaldırın.

## <a name="to-delete-results-from-a-repository"></a>Sonuçları bir depodan silmek için

1.  Bir Web performansı ve yük testi projesinden, bir yük testi açın.

2.  Katıştırılmış araç çubuğunda seçin **açın ve sonuçlarını yönetme**.

     **Açın ve yük testi sonuçlarını yönetme** iletişim kutusu görüntülenir.

3.  İçinde **yük testi sonuçlarını bulmak için bir denetleyici adı girin**, bir denetleyici seçin. Seçin  **\<yerel - denetleyicisi yok >** yerel olarak depolanan sonuçlara ulaşmak için.

4.  İçinde **göstermek için aşağıdaki yük testi sonuçları**, sonuçları görüntülemek istediğiniz yükleme testini seçin. Seçin  **\<tüm testleri için sonuçları göstermek >** tüm testler için tüm sonuçları görmek için.

     Yük testi sonuçlarını varsa, görüntülendikleri **yük testi sonuçlarını** listesi. Sütunlar **zaman**, **süresi**, **kullanıcı**, **sonucu**, **Test**, ve  **Açıklama**. **Test** test adını içerir ve **açıklama** testini çalıştırmadan önce eklemiş isteğe bağlı bir açıklama içerir. **Açıklama** sütunu içindeki girilen kısa açıklamaları görüntüler **çözümleme açıklamaları** bu test sonucu.

5.  İçinde **yük testi sonuçlarını** listesinde, bir sonuç seçin. Birden fazla sonuç seçmek için SHIFT tuşunu, Ctrl tuşunu veya her ikisini kullanabilirsiniz.

6.  Seçin **kaldırmak**.

     Sonuçları depodan kaldırılır.

    > [!NOTE]
    > **Açın ve yük testi sonuçlarını yönetme** sonuçlar kaldırıldıktan sonra iletişim kutusunu açık kalır.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: yük testi sonuçlarını bir depodan dışarı aktarma](../test/how-to-export-load-test-results-from-a-repository.md)
- [Yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Nasıl yapılır: yük testi sonuçlarını bir depoya içeri aktarma](../test/how-to-import-load-test-results-into-a-repository.md)