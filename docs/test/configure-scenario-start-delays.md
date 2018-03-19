---
title: "Visual Studio'da Test yük Senaryo Başlatma Gecikmelerini Yapılandırma | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, scenarios, start delays
ms.assetid: 2f634fba-8dfa-4c7a-a8b9-be867b78d16a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 2802172d3ba959b489e5449351d40395abe712a6
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="configure-scenario-start-delays-in-load-tests"></a>Yük testlerinde Senaryo Başlatma Gecikmelerini Yapılandırma

Yük Testi Düzenleyicisi'ni ve Özellikler penceresini kullanarak bir yük testinde senaryo başlamadan önce bir gecikme belirtin.

Örneğin, kullanmak isteyebilirsiniz **gecikme başlangıç zamanı** başka bir senaryonun tükettiği öğeleri oluşturmaya başlamak için bir senaryo gerekiyorsa özelliği. Bazı verileri doldurmak üretmeye senaryosunu sağlamak üzere tüketim senaryosunu geciktirebilir.

Yalnızca günün belirli bir saatte çalışacak bir senaryo sahip olabileceğiniz başka bir örnektir. Bu nedenle, bu benzetmek için senaryonun başlangıcı geciktirmek istersiniz.

## <a name="specifying-the-delay-start-time-of-a-scenario"></a>Bir senaryonun gecikme başlangıç zamanını belirtme

Değiştirmek için Yük Testi Düzenleyicisi'ni kullanarak bir yük testinde senaryo başlamadan önce bir gecikme belirtebilirsiniz **gecikme başlangıç zamanı** Özellikleri penceresinde özelliği.

> [!NOTE]
> Yük testi senaryosu özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

 Bir örnek kullanmak isteyebileceğiniz bir örneğinin **gecikme başlangıç zamanı** özelliktir başka bir senaryonun tükettiği öğeleri oluşturmaya başlamak için bir senaryo gerektiğinde. Bazı verileri doldurmak üretmeye senaryosunu sağlamak üzere tüketim senaryosunu geciktirebilir.

 Yalnızca belirli bir süre günün sonunda çalıştırılan bir senaryo sahip olabileceğiniz başka bir örnektir. Bu nedenle, bu benzetmek için senaryonun başlangıcı geciktirmek istersiniz.

> [!NOTE]
> Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

### <a name="to-specify-the-delay-start-time-for-a-scenario"></a>Bir senaryo için gecikme başlangıç zamanını belirtmek için

1. Bir yük testi açın.

     Yük Testi Düzenleyicisi görüntülenir. Yük testi ağacı görüntülenir.

2. Ağaçları yük testi **senaryoları** klasörü, gecikme başlangıç zamanı belirtmek istediğiniz senaryo düğümünü seçin.

3. Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Kategoriler ve Özellikler senaryonun Özellikler penceresinde görüntülenir.

4. Metin kutusunda **gecikme başlangıç zamanı** özelliği, yük testi sonra beklenecek süreyi belirten bir zaman değeri başlatır yük testi çalıştırdığınızda senaryoyu başlatmadan önce türü.

    > [!NOTE]
    > Varsa değeri **Isınma sırasında devre dışı bırak** özelliği senaryo için ayarlanmış **True**, sonra **gecikme başlangıç zamanı** özellikleri zaman değeri Isınma sonra uygulanır süre. Hangi senaryoları kullanarak Isınma içinde bulunan denetleyebilirsiniz **Isınma sırasında devre dışı bırak** senaryo özelliği.

5. Özelliği değiştirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından, yeni kullanarak yük testlerini çalıştırabilirsiniz **gecikme başlangıç zamanı** değeri.

## <a name="enabling-and-disabling-whether-a-scenario-runs-during-the-warm-up-period"></a>Etkinleştirme ve bir senaryo Isınma süresi boyunca çalıştırıldığını devre dışı bırakma

**Isınma sırasında devre dışı bırak** özelliği, Özellikler penceresini kullanarak ayarlanır. Yük testi senaryosu özellikleri düzenleme Yük Testi Düzenleyicisi tarafından ayarlanır.

 **Isınma sırasında devre dışı bırak** özelliği senaryo çalıştırmak veya belirtilen Isınma süresi sırasında çalışmayabilir belirtmek için kullanılır **gecikme başlangıç zamanı** özelliği. Daha fazla bilgi için önceki yordamda gözden [gecikme başlangıç zamanı bir senaryonun belirtme](../test/configure-scenario-start-delays.md#ConfiguringScenarioStartDelayHowTo).

> [!NOTE]
> Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

### <a name="to-enable-or-disable-the-warm-up-period-for-a-scenario"></a>Etkinleştirme veya devre dışı bir senaryo için Isınma Süresi

1. Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görüntülenir. Yük testi ağacı görüntülenir.

2. Ağaçları yük testi **senaryoları** klasörü, kullanılacak aracıları belirtmek istediğiniz senaryo düğümünü seçin.

3. Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Senaryonun kategoriler ve Özellikler Özellikler penceresinde görüntülenir.

     İçinde **Isınma sırasında devre dışı bırak** özelliği, şunlardan birini seçin **True** veya **False.**

4. Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından yeni kullanarak yük testlerini çalıştırabilirsiniz **Isınma sırasında devre dışı bırak** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Test aracıları yapılandırma ve test denetleyicileri yükleme testleri için](../test/configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)