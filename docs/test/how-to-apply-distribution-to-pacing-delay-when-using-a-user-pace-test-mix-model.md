---
title: "Dağıtım gecikmesine için Visual Studio'da Test yük için Uygula. | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, test mix model
ms.assetid: ae8b35f9-d465-4d72-8d7d-7b56ae6ffd22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 047a8fd8dea60ca86c39922f8cd0aed6e65ec6d3
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-apply-distribution-to-pacing-delay-when-using-a-user-pace-test-mix-model"></a>Nasıl yapılır: Kullanıcı Adım Testi Karışım Modeli Kullanılırken Adım Gecikmesine Dağıtım Uygulama

Yeni Yük Testi Sihirbazı'nı kullanarak yük testi oluşturduktan sonra senaryonun özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için Yük Testi Düzenleyicisi'ni kullanabilirsiniz.

**Dağıtım gecikmesine Uygula** özelliği, Özellikler penceresini kullanarak ayarlanır. Yük Testi Düzenleyicisini kullanarak yük testi senaryosu özellikleri değiştirilmiştir.

> [!NOTE]
> **Dağıtım gecikmesine Uygula** özelliği, yalnızca uygulanır *yük test karışımı* kullanıcı adına dayalı olarak yapılandırılır. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

Değeri **dağıtım gecikmesine Uygula** true veya false ayarlayabilirsiniz:

-   **True**: Senaryo değeri tarafından belirtilen normal istatistiksel dağıtım gecikmeler uygulanacak **saatte kullanıcı başına testler** Test Karışımını Düzenle iletişim kutusunda sütun. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Örneğin, sahip olduğunuz varsayılmıştır **saatte kullanıcı başına testler** saat başına iki kullanıcı testi için Test Karışımını Düzenle iletişim kutusunda değeri. Varsa **dağıtım gecikmesine Uygula** özelliği ayarlanmış **doğru**, testler arasındaki bekleme süresine normal istatistiksel dağılım uygulanır. Testler hala saatte iki test çalışır, ancak aralarında 30 dakikalık bir gecikmeyle mutlaka olmaz. İlk test dört dakika sonra ikinci test 45 dakika sonra çalışabilir.

-   **Yanlış**: testleri değeri için belirtilen hızda çalışır **saatte kullanıcı başına testler** Test Karışımını Düzenle iletişim kutusunda sütun. Daha fazla bilgi için bkz: [bir sanal kullanıcı çalışan bir Test olasılığını belirtmek için metin karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Örneğin, sahip olduğunuz varsayılmıştır **saatte kullanıcı başına testler** saat başına iki kullanıcı testi için Test Karışımını Düzenle iletişim kutusunda değeri. Varsa **dağıtım gecikmesine Uygula** özelliği ayarlanmış **yanlış**, testlerinizi çalıştırdığınızda, hiçbir yaratmamış olursunuz. Test 30 dakikada bir çalışır. Bu, saat başına iki testleri çalıştırmanızı sağlar.

## <a name="to-specify-the-apply-distribution-to-pacing-delay-property-setting-for-a-scenario"></a>Dağıtım senaryosu için gecikmesine özellik ayarı Uygula belirtmek için

1.  Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görüntülenir. Yük testi ağacı görüntülenir.

2.  İçinde **senaryoları** yük testi ağacı klasörü kullanılacak aracıları belirtmek istediğiniz senaryo düğümünü seçin.

3.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Kategoriler ve Özellikler senaryonun görüntülenen **özellikleri** penceresi.

4.  İçin özellik değerinde **dağıtım gecikmesine Uygula**, şunlardan birini seçin **True** veya **False**.

5.  Özelliği değiştirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından, yeni kullanarak yük testlerini çalıştırabilirsiniz **dağıtım gecikmesine Uygula** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [İzlenecek yol: Oluşturma ve bir yük testi çalıştırma](../test/walkthrough-create-and-run-a-load-test.md)
- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)