---
title: Visual Studio Yük testi çalıştırma ayarlarını ekleyin
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, adding
- load tests, run settings
ms.assetid: 257d2a24-d582-4cfe-8b2b-51f51ba9cc84
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: eee7f66c9df199a0ec2b7decb2f56ee70485870e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-additional-run-settings-to-a-load-test"></a>Nasıl yapılır: Bir Yük Testine Ek Çalışma Ayarları Ekleme

Bir yük testi çalıştırma ayarları çeşitli diğer ayarları belirler. Bu test, sonuç koleksiyonu ayrıntı düzeyi ve test çalıştığında toplanan sayaç kümeleri süresini içerir. Oluşturun ve her yük testi için birden çok çalışma ayarları depolamak ve testi çalıştırdığınızda kullanmak için belirli bir ayar seçin. Yeni Yük Testi Sihirbazı'nı kullanarak yük testi oluşturduğunuzda, yük testi için bir ilk çalıştırma ayarı eklenir.

 Yük testi farklı koşullar altında çalıştırabilmeniz için daha fazla yük testinizle farklı özellik ayarları için çalışma ayarları ekleyebilirsiniz. Örneğin, yeni bir test ayarı ekleyin ve farklı bir örnek hızı kullanabilir veya bir artık çalışma süresini belirtin. Etkin olarak işaretleyerek kullanmak için ayarı çalıştırılacağı belirtmeniz gerekir ve aynı anda yalnızca bir çalışma ayarı kullanabilirsiniz.

## <a name="to-add-another-run-setting"></a>Başka bir çalıştırma ayarı eklemek için

1.  Bir yük testi açın.

2.  (İsteğe bağlı) Genişletme **çalıştırma ayarları** klasör.

3.  Sağ **çalıştırma ayarları** klasörü ve select **çalıştırma ayarları Ekle**.

     Yeni bir çalışma ayarı eklenen **çalıştırma ayarları** klasör.

4.  Üzerinde **Görünüm** menüsünde seçin **Özellikler penceresini**.

     Özellikler penceresinde seçili çalışma ayarı için özellikleri birlikte görüntülenir.

5.  Metin kutusu için Özellikler penceresini kullanın **adı** özelliği bir adı ayarlama yeni çalıştırma vermek için çalışma ayarı amacı açıklar (örneğin, **Çalıştır ayarı: beş dakika çalıştırma**).

6.  Çalıştırma ayarlarını değiştirmek için Özellikler penceresini kullanın. Örneğin, çalışma süresini **00:05:00** beş dakika için testinizi çalıştırmak için.

    > [!NOTE]
    > Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).

     Şimdi, eklenen çalıştırma ayarını, etkin kullanmak istediğinizi belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: yük testi için etkin çalışma ayarı seçin](../test/how-to-select-the-active-run-setting-for-a-load-test.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)
- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)