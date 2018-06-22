---
title: Visual Studio'da Test yük için test yinelemelerini yapılandırma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios, iterations
- load test, iterations
- load tests, sceanrios
ms.assetid: ac480fb7-f4f7-47dc-9ae5-98be3aca4fba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 1892afefa7840910c51f184ca16ef2a6c6cd771a
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302916"
---
# <a name="configure-test-iterations-in-a-load-test-scenario"></a>Bir yük testi senaryosunda test yinelemelerini yapılandırma

Test yineleme ayarlarını yapılandırmak için Yük Testi Düzenleyicisini kullanarak yük testi senaryosuna düzenleyin ve **özellikleri** penceresi. Varsayılan olarak, bir yük testi senaryosu en yüksek test yinelemeleri belirtilmeden ayarlanır. Yineleme sayısı senaryoda ve bunlar arasında duraklatmak için ne kadar süreyle yapılandırma seçeneğiniz vardır.

## <a name="specify-the-maximum-test-iterations-for-a-scenario"></a>Bir senaryo için yüksek test yinelemeleri sayısını belirtin

Değiştirmek için Yük Testi Düzenleyicisini kullanarak Çalıştırılacak testleri bir senaryo için istediğiniz maksimum sayısı belirtebilirsiniz **en yüksek Test Yinelemeleri** özelliğinde **özellikleri** penceresi.

**En yüksek Test Yinelemeleri** özelliği bu senaryo için çalıştırmak için test yinelemeleri sayısını denetler. Yalnızca olarak için **Test Yinelemeleri** özelliğinde yük testi çalıştırma ayarları, bu en fazla tüm aracıları, tüm kullanıcılar arasında değil bir kullanıcı ayarı başına.

> [!NOTE]
> Yük testi senaryosu özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

 Sıralı test karışımı için bir yineleme karışımında tüm testleri bir geçiş ' dir. Diğer tüm test karışımları için her test yürütmesi bir yineleme olarak sayılır. Daha fazla bilgi için bkz: [karışımı denetimi hakkında](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).

 Yük testi süre tabanlı yük testi ise ve yineleme sayısı tamamlanmadan önce süre sona, test yine durdurur. Test yineleme dayalıdır ve test yinelemeleri Senaryo yineleme önce karşılandığında, test durur. Süre kullanılarak yapılandırılan **çalışma süresi** özelliğinde **özellikleri** yük testi çalışma ayarı ile ilişkili penceresi.

 Senaryo yineleme sayısı karşılandığında senaryo çalışmayı durdurur, ancak diğer tüm etkin senaryolar çalışmaya devam eder.

> [!NOTE]
> İlgili özellik **benzersiz** hangi ilerler sırayla verileri, satır temelinde, ancak yalnızca bir kez her kayıt için bir Web testi veri kaynağı özelliği. Daha fazla bilgi için bkz: [bir veri kaynağı bir web performans testine ekleme](../test/add-a-data-source-to-a-web-performance-test.md).

 **En yüksek Test Yinelemeleri** özelliği çeşitli durumlar için yararlıdır. Bazı yükleme sınayıcıları yineleme tabanlı testleri, diğer yükleme sınayıcıları süre tabanlı testleri yürütün tercih ancak yürütün tercih edilir.

 ![Bir senaryosunda test yinelemelerini belirtme](../test/media/loadtest_prop.png)

### <a name="to-specify-the-maximum-test-iterations"></a>Yüksek test yinelemeleri sayısını belirtmek için

1. Bir yük testi açın.

2. Yük Testi Düzenleyicisi görüntülenir. Yük testi ağacı görüntülenir.

3. Ağaçları yük testi **senaryoları** klasörü, test yineleme sayısını belirtmek istediğiniz senaryo düğümünü seçin.

4. Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Kategoriler ve Özellikler senaryonun görüntülenen **özellikleri** penceresi.

5. Metin kutusunda **en yüksek Test Yinelemeleri** özelliği, bir yük testi çalıştırdığınızda, testi senaryosu için en fazla sayısını belirten bir değer yazın.

    > [!NOTE]
    > İçin 0 değerini kullanarak **en yüksek Test Yinelemeleri** özelliği, hiç en fazla yineleme belirtir.

6. Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından, yeni kullanarak yük testlerini çalıştırabilirsiniz **en yüksek Test Yinelemeleri** değeri.

## <a name="specify-think-times-between-test-iterations-for-a-scenario"></a>Bir senaryo için test yinelemeleri arasındaki düşünme sürelerini belirtme

**Test Yinelemeleri Arasındaki Düşünme süresi** özelliği kullanılarak ayarlanmış **özellikleri** Yük Testi Düzenleyicisi'nde yük testi senaryosu özellikleri düzenlerken penceresi.

**Test Yinelemeleri Arasındaki Düşünme süresi** özelliği, bir test yineleme başlatmadan önce beklenecek saniye miktarını belirlemek için kullanılır.

> [!NOTE]
> Yük testi senaryosu özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

### <a name="to-specify-the-think-time-between-test-iterations"></a>Test yinelemeleri arasındaki düşünme süresi belirtmek için

1. Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görüntülenir. Yük testi ağacı görüntülenir.

2. Ağaçları yük testi **senaryoları** klasörü için düşünme süresi belirtmek istediğiniz senaryo düğümünü seçin.

3. Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Senaryonun kategoriler ve özellikler görüntülenir **özellikleri** penceresi.

4. İçin değer **Test Yinelemeleri Arasındaki Düşünme süresi** özelliği, bir sonraki test yinelemesini başlatmadan önce beklenecek saniye sayısını temsil eden bir sayı girin.

5. Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından yeni kullanarak yük testlerini çalıştırabilirsiniz **Test Yinelemeleri Arasındaki Düşünme süresi** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Test aracıları yapılandırma ve test denetleyicileri yükleme testleri için](../test/configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)
- [Web sitesi insan etkileşimi gecikmelerini benzetmek için Düşünme zamanlarını düzenleme](../test/edit-think-times-in-load-test-scenarios.md)