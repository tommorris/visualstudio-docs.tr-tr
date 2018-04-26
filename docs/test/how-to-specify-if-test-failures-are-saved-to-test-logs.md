---
title: Visual Studio'da test başarısızlıklarının için yük testi günlüğüne kaydet
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, logging
ms.assetid: 08a7fe98-a7f7-4b8d-94a3-ec82b65a2aaf
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e184fbab591698404bde4593f4ad7b61fa1815ae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-if-test-failures-are-saved-to-test-logs-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini Kullanarak Test Başarısızlıklarının Test Günlüklerine Kaydedilip Kaydedilmediği Belirleme

Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** test gereksinimlerini ve hedeflerinizi karşılamak için yük testi özelliklerini değiştirmek için. Bkz: [izlenecek yol: oluşturma ve bir yük testi çalıştırma](../test/walkthrough-create-and-run-a-load-test.md). Değiştirerek bir yük testinde test başarısız olursa kaydedilen test günlüklerine isteyip istemediğinizi belirtebilirsiniz **Test Başarısızlığı Oturumunu Kaydet** özelliği.

> [!NOTE]
> Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).


## <a name="to-specify-if-the-test-log-is-saved-when-a-test-fails-in-a-scenario"></a>Bir senaryoda bir test başarısız olduğunda sınama günlük kaydedilirse belirtmek için

1.  Bir yük testi açın.

     Yük Testi Düzenleyicisi görüntülenir. Yük testi ağacı görüntülenir.

2.  Ağaçları yük testi **çalıştırma ayarları** klasörü için test yineleme sayısını belirtmek istediğiniz çalışma ayarları düğümünü seçin.

3.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Çalıştırma ayarlarını kategoriler ve Özellikler Özellikler penceresinde görüntülenir.

4.  İçinde **Test Başarısızlığı Oturumunu Kaydet** özelliği, seçin ya da True veya False testini kaydetmek isteyip istemediğinizi belirtmek için oturum senaryosunda bir sınama hatası olayı içinde.

     Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü.

     Günlüğe kaydedilen veri Yük Testi Çözümleyicisinin Tablo görünümü kullanılarak görüntülenebilir. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [İzlenecek yol: Yük testi oluşturma ve çalıştırma](../test/walkthrough-create-and-run-a-load-test.md)
- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Nasıl yapılır: sanal kullanıcı etkinlik grafiğini etkinleştirmek için tüm ayrıntıların toplanmasını yapılandırma](../test/how-to-configure-load-tests-to-collect-full-details.md)
- [Nasıl yapılır: Test günlüklerinin hangi sıklıkla kaydedileceğini belirtin](../test/how-to-specify-how-frequently-test-logs-are-saved.md)