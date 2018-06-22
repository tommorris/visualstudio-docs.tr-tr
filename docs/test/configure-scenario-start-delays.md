---
title: Yük testi için Senaryo Başlatma Gecikmelerini Yapılandırma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios, start delays
ms.assetid: 2f634fba-8dfa-4c7a-a8b9-be867b78d16a
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 30a19e786894a9722e6843a5c1c69cdf1f038e58
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36296381"
---
# <a name="configure-scenario-start-delays-in-load-tests"></a>Yük testlerinde Senaryo Başlatma Gecikmelerini Yapılandırma

Yük Testi Düzenleyicisini kullanarak bir yük testinde senaryo başlamadan önce bir gecikme belirtin ve **özellikleri** penceresi.

Örneğin, kullanmak isteyebilirsiniz **gecikme başlangıç zamanı** başka bir senaryonun tükettiği öğeleri oluşturmaya başlamak için bir senaryo gerekiyorsa özelliği. Bazı verileri doldurmak üretmeye senaryosunu sağlamak üzere tüketim senaryosunu geciktirebilir.

Yalnızca günün belirli bir saatte çalışacak bir senaryo sahip olabileceğiniz başka bir örnektir. Bu nedenle, bu benzetmek için senaryonun başlangıcı geciktirmek istersiniz.

## <a name="specify-the-delay-start-time-of-a-scenario"></a>Bir senaryo gecikme başlangıç saatini belirtin

Değiştirmek için Yük Testi Düzenleyicisi'ni kullanarak bir yük testinde senaryo başlamadan önce bir gecikme belirtebilirsiniz **gecikme başlangıç zamanı** özelliğinde **özellikleri** penceresi.

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

     Kategoriler ve Özellikler senaryonun görüntülenen **özellikleri** penceresi.

4. Metin kutusunda **gecikme başlangıç zamanı** özelliği, yük testi sonra beklenecek süreyi belirten bir zaman değeri başlatır yük testi çalıştırdığınızda senaryoyu başlatmadan önce türü.

    > [!NOTE]
    > Varsa değeri **Isınma sırasında devre dışı bırak** özelliği senaryo için ayarlanmış **True**, sonra **gecikme başlangıç zamanı** özellikleri zaman değeri Isınma sonra uygulanır süre. Hangi senaryoları kullanarak Isınma içinde bulunan denetleyebilirsiniz **Isınma sırasında devre dışı bırak** senaryo özelliği.

5. Özelliği değiştirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından, yeni kullanarak yük testlerini çalıştırabilirsiniz **gecikme başlangıç zamanı** değeri.

## <a name="enable-and-disable-whether-a-scenario-runs-during-the-warm-up-period"></a>Etkinleştirme ve devre dışı bir senaryo Isınma süresi boyunca çalıştırıldığını

**Isınma sırasında devre dışı bırak** özelliği kullanılarak ayarlanmış **özellikleri** penceresi. Yük testi senaryosu özellikleri düzenleme Yük Testi Düzenleyicisi tarafından ayarlanır.

 **Isınma sırasında devre dışı bırak** özelliği senaryo çalıştırmak veya belirtilen Isınma süresi sırasında çalışmayabilir belirtmek için kullanılır **gecikme başlangıç zamanı** özelliği. Daha fazla bilgi için önceki yordamda gözden [gecikme başlangıç saati bir senaryonun belirtin](#specify-the-delay-start-time-of-a-scenario).

> [!NOTE]
> Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

### <a name="to-enable-or-disable-the-warm-up-period-for-a-scenario"></a>Etkinleştirme veya devre dışı bir senaryo için Isınma Süresi

1. Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görüntülenir. Yük testi ağacı görüntülenir.

2. Ağaçları yük testi **senaryoları** klasörünü Isınma davranışını değiştirmek istediğiniz senaryo düğümünü seçin.

3. Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Senaryonun kategoriler ve özellikler görüntülenir **özellikleri** penceresi.

     İçinde **Isınma sırasında devre dışı bırak** özelliği, şunlardan birini seçin **True** veya **False.**

4. Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından yeni kullanarak yük testlerini çalıştırabilirsiniz **Isınma sırasında devre dışı bırak** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Test aracıları yapılandırma ve test denetleyicileri yükleme testleri için](../test/configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)