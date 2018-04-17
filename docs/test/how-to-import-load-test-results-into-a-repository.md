---
title: "Nasıl yapılır: Visual Studio'da havuzunda yük testi sonuçlarını alma | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load test results, importing
- Load Test Results Repository
- load tests, importing results
ms.assetid: a955b3d2-c8ad-40dd-8ea3-9f1a271e1eed
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 5a4646578299895c0988522d871ba727d80f063c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-import-load-test-results-into-a-repository"></a>Nasıl yapılır: Yük Testi Sonuçlarını bir Depoya Aktarma

Bir yük testi çalıştırdığınızda, çalışma sırasında toplanan bilgiler yük testi sonuçları deposunda saklanır. Yük testi sonuçları havuzu performans sayacı verilerini ve hatalar hakkında bilgi içerir. Daha fazla bilgi için bkz: [yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md).

 Yük testi sonuçlarını kullanarak Yük Testi Düzenleyicisi'nden yönetebilirsiniz **yük testi sonuçlarını yönetme ve Aç** iletişim kutusu. Açın, içeri aktarma, dışarı aktarma ve yük testi sonuçlarını kaldırın.

## <a name="to-import-results-into-a-repository"></a>Sonuçları bir depoya içeri aktarmak için

1.  Bir Web performansı ve yük testi projesinden, bir yük testi açın.

2.  Katıştırılmış araç çubuğunda seçin **açın ve sonuçlarını yönetme**.

     **Açın ve yük testi sonuçlarını yönetme** iletişim kutusu görüntülenir.

3.  İçinde **yük testi sonuçlarını bulmak için bir denetleyici adı girin**, bir denetleyici seçin. Seçin  **\<yerel >** yerel olarak depolanan sonuçlara ulaşmak için.

     Yük testi sonuçlarını yoksa görüntülendikleri **yük testi sonuçlarını** listesi. Sütunlar **zaman**, **süresi**, **kullanıcı**, **sonucu**, **Test**, ve  **Açıklama**. **Test** test adını içerir ve **açıklama** testini çalıştırmadan önce eklemiş isteğe bağlı bir açıklama içerir.

4.  Seçin **alma**.

     **Alma yük testi sonuçlarını** iletişim kutusu görüntülenir.

5.  İçinde **dosya adı** kutusuna arşivlenmiş test sonuçları dosyasının adını yazın ve ardından **açık**.

     \- veya -

     Dosyaya gidin ve ardından **açık**.

    > [!NOTE]
    > Bu adımda belirttiğiniz arşivlenmiş test sonuçları dosyasının dışarı aktarma işlemi gerçekleştirilerek oluşturulmuş olması gerekir.

     Sonuçları alınır ve görüntülenmesini **yük testi sonuçlarını** listesi.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Nasıl yapılır: yük testi sonuçlarını bir depodan dışarı aktarma](../test/how-to-export-load-test-results-from-a-repository.md)