---
title: "Nasıl yapılır: Visual Studio'da bir yük testi çalışma ayarı için örnek hızı belirtme"
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings
ms.assetid: 51cbe7d6-5dfd-4842-bca3-f7f8a665dc84
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 18fa71396caa0c164ef7f37183cda28c701cf4f8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-the-sample-rate-for-a-load-test-run-setting"></a>Nasıl yapılır: Yük Testi Çalışma Ayarı için Örnek Hızı Belirtme

Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için.

Kullanarak **Yük Testi Düzenleyicisi**, bir çalışma ayarın düzenleyebilirsiniz **örnek hızı** özellik değerine **özellikleri** penceresi. Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).

Uygun bir değer seçin **örnek hızı** özelliği yük testi çalışma ayarı için temel yük testi uzunluğu. Varsayılan değer olarak beş saniye gibi daha küçük bir örnek hızı yük testi sonuçları veritabanında daha fazla alan gerektirir. Uzun yük testleri için örnek hızı artırma topladığınız veri miktarını azaltır. Daha fazla bilgi için bkz: [nasıl yapılır: yük testi çalıştırma ayarı için örnek hızı belirtme](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Örnek hızları ilgili bazı kurallar şunlardır:

|Yük Test süresi|Örnek hızı önerilir|
|------------------------|-----------------------------|
|\< 1 saat|5 saniye|
|1 - 8 saatte bir|15 saniye|
|8 - 24 saat|30 saniye|
|> 24 saat|60 saniye|

## <a name="to-specify-performance-counter-sampling-rate-in-a-run-setting"></a>Bir çalışma ayarında performans sayacı örnekleme hızını belirtmek için

1.  Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görüntülenir. Yük testi ağacı görüntülenir.

2.  Ağaç, test yük **çalıştırma ayarları** klasörü, örnek hızı için belirtmek istediğiniz çalışma ayarı seçin.

3.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Yük ayarın kategoriler ve Özellikler çalışma Özellikleri penceresinde görüntülenir.

4.  İçinde **örnek hızı** özelliği, hangi yük testi performans sayaç verileri toplama sıklığı belirten bir saat değeri girin.

5.  Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından yeni kullanarak yük testlerini çalıştırabilirsiniz **örnek hızı** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)