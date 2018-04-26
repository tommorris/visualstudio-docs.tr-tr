---
title: Visual Studio Yük testi senaryolarında kullanılacak Test aracıları belirtme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- test agents, load tests
- load tests, scenarios
- load tests, specifying for load tests
- tests agents, load tests, specifying
- load tests, test agents
ms.assetid: e86806dd-5897-4e4c-bfd4-8d687fb72a6e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: a4aacbd31516e6a3e55f1b543a3cc8f49ea6ce4d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-test-agents-to-use-in-load-test-scenarios"></a>Nasıl yapılır: Yük Testi Senaryolarında Kullanılacak Test Aracılarını Belirtme

Kullanarak yük testi oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** senaryoları özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için.

> [!NOTE]
> Yük testi senaryosu özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

Aracıları değiştirmek için Yük Testi Düzenleyicisini kullanarak belirtilen **kullanılacak aracılar** Özellikleri penceresinde özelliği.

Senaryonuzun denetleyicileri kullanıyorsanız ve test aracıları yükü çalıştırmak için uzaktan kullanmasını istediğiniz aracıları belirtebilirsiniz. Örneğin, performans eğilimlerini analiz ederken tutarlılığını korumak için belirli bir aracı kümesi belirtmek isteyebilirsiniz. Benzeşim var. böylece arasında hangi betikleri çalışırlar ve aracı bulunduğu Ayrıca, aracılar coğrafi olarak, dağıtılabilir.

> [!TIP]
> Bir aracı uzak siteye fiziksel olarak koyma yerine, başka bir seçenek ağ öykünmesini yavaş ağ benzetmek için kullanmaktır. Daha fazla bilgi için bkz: [sanal ağ türlerini belirtme](../test/specify-virtual-network-types-in-a-load-test-scenario.md) ve [sanal ağ türlerini belirtme](../test/specify-virtual-network-types-in-a-load-test-scenario.md).

Daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

Bir başka neden olan, ancak bazı değil tüm aracıları yüklü yazılım, belirli bir senaryo için gerekli olabilir.

Belirli bir test rolleri test ayarlarını kullanarak çalıştırması için aracı seçimini denetleyebilirsiniz. Daha fazla bilgi için bkz: [toplamak tanılama bilgileri Test ayarlarını kullanarak](../test/collect-diagnostic-information-using-test-settings.md).

Test aracısı makine CPU kullanımı yüzde 75'inden daha vardır veya kullanılabilir fiziksel bellek yüzde 10'den az varsa, daha fazla aracıları aracı makine yük testlerini sıkışıklık haline gelmediğinden emin olmak için yük testi ekleyin.

## <a name="to-specify-the-agents-to-use-for-a-scenario"></a>Bir senaryo için kullanılacak aracıları belirtmek için

1.  Bir yük testi açın.

     Yük Testi Düzenleyicisi görüntülenir. Yük testi ağacı görüntülenir.

2.  Ağaçları yük testi **senaryoları** klasörü, kullanılacak aracıları belirtmek istediğiniz senaryo düğümünü seçin.

3.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Kategoriler ve Özellikler senaryonun Özellikler penceresinde görüntülenir.

4.  Metin kutusunda **kullanılacak aracılar** özelliği, senaryo çalışabilir aracıların listesini yazın.

     Aracıları ayrılmalıdır virgüllerle, örneğin "**Aracı1, Aracı2, Aracı3**". Özelliği boş bırakmak senaryo tüm kullanılabilir aracıları'nı kullanması gerektiğini belirtir.

    > [!NOTE]
    > **Kullanılacak aracılar** özelliği, yerel çalıştırmaları için yoksayılır. Uzak çalıştığında, belirtilen aracıların hiçbiri için **kullanılacak aracılar** var, testleri senaryoda çalışmaz.

5.  Özelliği değiştirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından, yeni kullanarak yük testlerini çalıştırabilirsiniz **kullanılacak aracılar** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [İzlenecek yol: Yük testi oluşturma ve çalıştırma](../test/walkthrough-create-and-run-a-load-test.md)
- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)