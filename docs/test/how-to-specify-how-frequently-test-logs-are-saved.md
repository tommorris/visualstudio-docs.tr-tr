---
title: Kaydetme yük testi Visual Studio'da günlüğe kaydeder.
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, logging
ms.assetid: 9ac88d8a-4777-462c-aa0e-244dadb2cfd1
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 3464ffc1db1a757ac20e3f77d0d901ec731a7cab
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39381940"
---
# <a name="how-to-specify-how-frequently-test-logs-are-saved-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini kullanarak test günlüklerinin hangi sıklıkla kaydedileceğini belirtme

İle yükleme testinizi oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** yük değiştirmek için test ihtiyaçlarınızı ve hedeflerinizi karşılamak için özellikler sınar. Daha fazla bilgi için [izlenecek yol: bir yük testi oluşturma ve çalıştırma](../test/walkthrough-create-and-run-a-load-test.md).

> [!NOTE]
> Çalıştırma ayarları özellikleri ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).

Test günlüğü kullanarak bir yük testi içinde kaydedildiğini ne sıklıkta belirtebilirsiniz **Yük Testi Düzenleyicisi** değiştirmek için **tamamlanmış testler için günlük sıklığını Kaydet** özelliğinde **özellikleri** penceresi.

## <a name="to-specify-the-frequency-for-saving-the-test-log-in-a-load-test"></a>Bir yük testinde test günlüğü kaydetmek için sıklığını belirtmek için

1.  Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görünür. Yük testi ağacında gösterir.

2.  Ağacı'nın yük testi **çalıştırma ayarları** klasörünü ne sıklıkta test günlüğe kaydedildiğini belirtmek istediğiniz çalışma ayarı düğümünü seçin.

3.  Üzerinde **görünümü** menüsünde **Özellikler penceresi**.

     Senaryonun kategoriler ve özellikler görüntülenir **özellikleri** penceresi.

4.  Metin kutusunda **tamamlanmış testler için günlük sıklığını Kaydet** özelliği, hangi test günlüğü yazılır sıklığı belirtmek için sayı yazın. Girilen her test sayısı yetersiz bir test günlüğüne kaydedilecek sayıyı belirtir. Örneğin, on değerinin girilmesi onda, 20, otuzuncu ve benzeri test günlüğüne yazılacağını belirtir.

    > [!NOTE]
    > Bir değer için 0'ı kullanarak **tamamlanmış testler için günlük sıklığını Kaydet** özelliği, hiçbir test günlüğü kaydedildiğini belirtir.

5.  Özelliği değiştirmeyi bitirdikten sonra seçin **Kaydet** üzerinde **dosya** menüsü.

     Yük Testi Çözümleyicisinin Tablo görünümü kullanarak günlüğe kaydedilen verileri görüntülenebilir. Daha fazla bilgi için [yük testi sonuçlarını ve hatalarını Tablo görünümünde çözümlemek](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [İzlenecek yol: Yük testi oluşturma ve çalıştırma](../test/walkthrough-create-and-run-a-load-test.md)
- [Nasıl yapılır: test başarısızlıklarının test günlüklerini kaydedilip kaydedilmediği belirleme](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)
- [Nasıl yapılır: sanal kullanıcı etkinlik grafiğini etkinleştirmek için tüm ayrıntıların toplanmasını yapılandırma](../test/how-to-configure-load-tests-to-collect-full-details.md)