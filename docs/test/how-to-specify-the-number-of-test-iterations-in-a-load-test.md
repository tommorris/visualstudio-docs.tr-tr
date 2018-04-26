---
title: Yük testi çalışma ayarı Visual Studio'da Test yineleme sayısını belirtin
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, properties
- load tests, run settings
ms.assetid: 45a625db-b3e7-4d64-beda-b9a76248096d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: ec11561a3ebe084517d1a30266f9caa6491544a7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-the-number-of-test-iterations-in-a-load-test-run-setting"></a>Nasıl yapılır: Yük Testi Çalışma Ayarlarında Test Yineleme Sayısını Belirtme

Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** senaryoları özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için. Daha fazla bilgi için bkz: [izlenecek yol: oluşturma ve bir yük testi çalıştırma](../test/walkthrough-create-and-run-a-load-test.md).

Kullanarak **Yük Testi Düzenleyicisi**, düzenleyebileceğiniz **Test Yinelemeleri** Özellikler penceresinde çalışma ayarları değerinin özelliği. **Test Yinelemeleri** özelliği, tüm Web performansı ve birim testleri tüm senaryolarda kullanarak yük testi çalıştırmak için yineleme sayısını belirtir **Yük Testi Düzenleyicisi**.

> [!NOTE]
> Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).


## <a name="to-specify-the-number-of-test-iterations-in-a-run-setting"></a>Bir çalışma ayarında test yineleme sayısını belirtmek için

1.  Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görünür ve yük testi ağacı görüntüler.

2.  Ağaç, test yük **çalıştırma ayarları** klasörü, bir çalışma ayarı seçin.

3.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini** yük ayarın kategoriler ve Özellikler çalışma görüntülemek için.

4.  Ayarlama **Test Yinelemeleri Kullan** özelliğine **doğru**.

5.  İçinde **Test Yinelemeleri** özelliği, yük testi sırasında çalıştırmak için test yineleme sayısını belirten bir sayı girin.

6.  Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından yeni kullanarak yük testlerini çalıştırabilirsiniz **Test Yinelemeleri** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)