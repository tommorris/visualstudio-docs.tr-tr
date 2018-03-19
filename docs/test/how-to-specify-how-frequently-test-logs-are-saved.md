---
title: "Kaydetme yük testi Visual Studio'da oturum | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, scenarios
- load tests, logging
ms.assetid: 9ac88d8a-4777-462c-aa0e-244dadb2cfd1
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 0178be52299183a072532d62f323a4612a93f531
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-specify-how-frequently-test-logs-are-saved-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini Kullanarak Test Günlüklerinin Hangi Sıklıkla Kaydedileceğini Belirtme

Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** yük değiştirmek için test gereksinimleri ve hedeflerinizi karşılamak için özellikler sınar. Daha fazla bilgi için bkz: [izlenecek yol: oluşturma ve bir yük testi çalıştırma](../test/walkthrough-create-and-run-a-load-test.md).

> [!NOTE]
> Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).

Test günlük değiştirmek için Yük Testi Düzenleyicisini kullanarak bir yük testinde kaydedilir ne sıklıkta belirtebilirsiniz **tamamlanmış testler için günlük sıklığını Kaydet** Özellikleri penceresinde özelliği.

## <a name="to-specify-the-frequency-for-saving-the-test-log-in-a-load-test"></a>Bir yük testinde test günlüğüne kaydetme sıklığını belirtmek için

1.  Bir yük testi açın.

     Yük Testi Düzenleyicisi görüntülenir. Yük testi ağacı görüntüler.

2.  Ağaçları yük testi **çalıştırma ayarları** klasörü, ne sıklıkta test günlüğüne kaydedildiğini belirtmek istediğiniz çalışma ayarı düğümünü seçin.

3.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Senaryonun kategoriler ve Özellikler Özellikler penceresinde görüntülenir.

4.  Metin kutusunda **tamamlanmış testler için günlük sıklığını Kaydet** özelliği, hangi test günlüğüne yazılır sıklığı belirtmek için bir sayıyı yazın. Bir sınama girilen her sayısı dışı test günlüğe kaydedilecek sayıyı belirtir. Örneğin, on değerini girmek onuncu, 20, otuzuncu ve benzeri test günlüğüne yazılacağını belirtir.

    > [!NOTE]
    > İçin 0 değerini kullanarak **tamamlanmış testler için günlük sıklığını Kaydet** özellik belirtir hiçbir test günlüklerine kaydedilir.

5.  Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü.

     Günlüğe kaydedilen veri Yük Testi Çözümleyicisinin Tablo görünümü kullanılarak görüntülenebilir. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [İzlenecek yol: Oluşturma ve bir yük testi çalıştırma](../test/walkthrough-create-and-run-a-load-test.md)
- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Nasıl yapılır: Test başarısızlıklarının Test günlüklerine kaydedilip kaydedilmediği belirleme](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)
- [Nasıl yapılır: sanal kullanıcı etkinlik grafiğini etkinleştirmek için tüm ayrıntıların toplanmasını yapılandırma](../test/how-to-configure-load-tests-to-collect-full-details.md)