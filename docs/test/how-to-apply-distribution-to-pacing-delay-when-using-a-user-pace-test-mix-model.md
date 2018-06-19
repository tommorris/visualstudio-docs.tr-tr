---
title: Yük testi için dağıtım gecikmesine için geçerlidir
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, test mix model
ms.assetid: ae8b35f9-d465-4d72-8d7d-7b56ae6ffd22
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 268578638524ab4f5e5db605c3d394d28414547a
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34448525"
---
# <a name="how-to-apply-distribution-to-pacing-delay-for-a-user-pace-test-mix-model"></a>Nasıl yapılır: kullanıcı adım testi karışım modeli için Gecikmesine Dağıtım uygulama

Kullanarak yük testi oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, senaryonun özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için Yük Testi Düzenleyicisi'ni kullanabilirsiniz.

**Dağıtım gecikmesine Uygula** özelliği kullanılarak ayarlanmış **özellikleri** penceresi. Yük Testi Düzenleyicisini kullanarak yük testi senaryosu özellikleri değiştirilmiştir.

> [!NOTE]
> **Dağıtım gecikmesine Uygula** özelliği, yalnızca uygulanır *yük test karışımı* kullanıcı adına dayalı olarak yapılandırılır. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

Değeri **dağıtım gecikmesine Uygula** true veya false ayarlayabilirsiniz:

- **Doğru**: Senaryo değeri tarafından belirtilen normal istatistiksel dağıtım gecikmeler geçerlidir **saatte kullanıcı başına testler** Test Karışımını Düzenle iletişim kutusunda sütun. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Örneğin, sahip olduğunuz varsayılmıştır **saatte kullanıcı başına testler** saat başına iki kullanıcı testi için Test Karışımını Düzenle iletişim kutusunda değeri. Varsa **dağıtım gecikmesine Uygula** özelliği ayarlanmış **doğru**, testler arasındaki bekleme süresine normal istatistiksel dağılım uygulanır. Testler hala saatte iki test çalışır, ancak aralarında 30 dakikalık bir gecikmeyle mutlaka olmaz. İlk test dört dakika sonra ikinci test 45 dakika sonra çalışabilir.

- **Yanlış**: testler değeri için belirtilen hızda **saatte kullanıcı başına testler** sütununda **Test Karışımını düzenleme** iletişim kutusu. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Örneğin, sahip olduğunuz varsayılmıştır **saatte kullanıcı başına testler** değeri **Test Karışımını düzenleme** Ayarla iletişim kutusu test için saat başına iki kullanıcı. Varsa **dağıtım gecikmesine Uygula** özelliği ayarlanmış **yanlış**, testlerinizi çalıştırdığınızda, hiçbir yaratmamış olursunuz. Test 30 dakikada bir çalışır. Bu, saat başına iki testleri çalıştırmanızı sağlar.

## <a name="to-specify-the-apply-distribution-to-pacing-delay-property-setting-for-a-scenario"></a>Dağıtım senaryosu için gecikmesine özellik ayarı Uygula belirtmek için

1. Bir yük testi açın.

   **Yük Testi Düzenleyicisi** görüntülenir. Yük testi ağacı görüntülenir.

2. İçinde **senaryoları** klasörü yük testi ağacının hız dağıtım için uygulamak istediğiniz senaryo düğümünü seçin.

3. Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

   Kategoriler ve Özellikler senaryonun görüntülenen **özellikleri** penceresi.

4. İçin özellik değerinde **dağıtım gecikmesine Uygula**, şunlardan birini seçin **True** veya **False**.

5. Seçin **dosya** > **kaydetmek**. Şimdi yük testi yeni çalıştırabilirsiniz **dağıtım gecikmesine Uygula** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [İzlenecek yol: Yük testi oluşturma ve çalıştırma](../test/walkthrough-create-and-run-a-load-test.md)
- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)