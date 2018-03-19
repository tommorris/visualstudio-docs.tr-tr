---
title: "Visual Studio Yük testi senaryolarını düzenleme | Microsoft Docs"
ms.date: 10/03/2016
ms.topic: article
helpviewer_keywords:
- load tests, scenarios
- load tests, user activities
- load tests, modeling scenarios
ms.assetid: fec04f2e-bf38-4d44-b2ec-fa50f58fd0d9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 5b4abcb0b75e379df360c045527790a708c55c6e
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="edit-load-test-scenarios"></a>Yük testi senaryolarını düzenleme

Bir yük testi *senaryo* yük düzeni, test karışımı, tarayıcı karışımı ve ağ karışımı belirtir. Senaryolar, karmaşık, gerçekçi iş yükleri benzetimini yapmak için testleri yapılandırmanıza olanak sağlamak için önemlidir.

Örneğin, kullanılan bir Internet ön uç çok sayıda bağlantı hızları gelen ve farklı tarayıcılar kullanarak eşzamanlı müşteriler yüzlerce tarafından bir e-ticaret sitesi sınama. Aynı sitede ayrıca ürünleri güncelleştirmek ve istatistiklerini görüntülemek için şirket içi çalışanlar tarafından kullanılan bir yönetim işleve sahip olabilir. Bu dahili kullanıcılar, aynı tarayıcı ve yüksek hızlı bir LAN bağlantısı kullanarak site genellikle erişir. Bu iki farklı kullanıcı grupları farklı senaryolarında özelliklerini saklamak isteyeceksiniz. Her senaryo, bir sanal kullanıcı türü içerebilir. Bu durumda, sanal müşterileri temsil edecek bir yük testi senaryosuna yapılabilir ve başka bir senaryo, bir Web sitesinin sanal iç kullanıcıları temsil etmek için yapılabilir.

## <a name="scenario-components"></a>Senaryo Bileşenleri

İlk yapılandırma seçenekleri ve bir yük testi oluşturduğunuzda, belirttiğiniz ayarları değiştirilebilir daha sonra Yük Testi Düzenleyicisi'nde. Bir yük testine yeni senaryolar, çalıştırma ayarlarını ve sayaç kümeleri de ekleyebilirsiniz.

![Yük testi senaryolarını](../test/media/loadtesteditinscenarios.png)

Senaryoları aşağıdaki bileşenleri içerir:

|||
|-|-|
|Terim|Tanım|
|Tarayıcı karışımı|Sanal kullanıcı Web tarayıcıları çeşitli bir Web sitesine erişim benzetimini yapar.|
|Yük düzeni|Bir yük testi ve yeni kullanıcılar başladığı oranı sırasında etkin olan sanal kullanıcıların sayısını belirtir. Örneğin: adım, sabit ve hedef tabanlı.|
|Test Mix Model|Bir yük testi senaryosunda belirli bir test çalıştıran sanal kullanıcı olasılığını belirtir. Örneğin: % 20 olasılık TestA çalıştırmak için ve % 80 olasılık. Test karışımı modeli her belirli bir senaryo için hedefini yansıtmalıdır.|
|Test karışımı|Test karışımı senaryoyu oluşturan Web performansı ve birim testleri seçimi ve bu testlerin dağıtımını ' dir.|
|Ağ karışımı|Sanal kullanıcıların çeşitli ağ bağlantıları bir Web sitesine erişim benzetimini yapar. Ağ karışımı LAN, kablolu modem ve diğer seçenekleri dahil seçenekleri sunar.|

Bir senaryonun yük testi düzenleyicisini kullanarak düzenleyebilirsiniz diğer bazı özellikleri vardır. Daha fazla bilgi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

## <a name="tasks"></a>Görevler

|Görevler|İlişkili Konular|
|-----------|-----------------------|
|**Yapay insan etkileşimi duraklatır, senaryoda ekleyin:** düşünme sürelerini insanların bir Web sitesi ile etkileşim arasında beklemesine neden olan insan davranışı benzetimi için kullanılır. Web performans testinde istekleri arasında ve bir yük testi senaryosunda test yinelemeleri arasındaki düşünme sürelerini oluşur. Bir yük testinde düşünme sürelerini kullanarak daha kesin yükleme benzetimleri oluşturmada faydalı olabilir.|-   [Web sitesi insan etkileşimi gecikmelerini benzetmek için Düşünme zamanlarını düzenleme](../test/edit-think-times-in-load-test-scenarios.md)|
|**Senaryonuz için sanal kullanıcı sayısını belirtin:** benzetimli kullanıcı yükünün bir yük testi sırasında nasıl ayarlanacağını belirtmek için yük düzeni özelliklerini yapılandırabilirsiniz. Üç yerleşik yük düzenlerini alma: Sabit, adım ve hedef temelli. Yük düzeni seçin ve yük testi hedeflerinize uygun düzeylerine özelliklerini ayarlayın.|-   [Sanal kullanıcı etkinlikleri modellemek için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md)|
|**Senaryoda bir test çalıştıran sanal kullanıcı olasılığını yapılandırın:** bir yük testi senaryosunda belirli bir test çalıştıran sanal kullanıcı olasılığını belirtir test karışımını kullanabilirsiniz. Bu, yük daha gerçekçi benzetimini sağlar. Tek bir iş akışı uygulamalarınız aracılığıyla sahip olmak yerine birkaç iş akışları, son kullanıcıların uygulamalarınızla nasıl etkileşim akışınız olduğu olabilir.|-   [Karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)|
|**Web performans veya birim testi bir Yük Testi Senaryosundan ekleyip:** ekleyebilir veya bir yük testi senaryosunda Web performans veya birim testi kaldırın. Bir yük testi her biri bir veya daha fazla Web performans testleri içeren bir veya daha fazla senaryo içerir.|-   [Test Karışımını düzenleme](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**Senaryonuz için istenen ağ karışımı yapılandırın:** ağ karışımını kullanarak, Ağ Yükü yük testi senaryosunda daha gerçekçi benzetimini yapabilirsiniz. Yükleme yerine tek tek ağ türü ağ türlerini heterojen bir karışımını kullanarak oluşturulur. Son kullanıcıların uygulamalarınızla nasıl etkileşim akışınız oluşturun. Bu senaryonun ağ karışımı modeli yansıtmalıdır.|-   [Sanal ağ türlerini belirtme](../test/specify-virtual-network-types-in-a-load-test-scenario.md)|
|**Senaryonuz için uygun Web tarayıcısı karışımını seçin:** tarayıcı karışımını kullanarak, bir yük testi senaryosunda daha gerçekçi Web yük benzetimini yapabilirsiniz. Yükleme yerine tek tek tarayıcı tarayıcılar heterojen bir karışımını kullanarak oluşturulur. Akışınız uygulamalarınızla kullanılacak tarayıcıların oluşturun.|-   [Web tarayıcısı türlerini belirtme](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**Senaryonuz için test yineleme ayarları yapılandırın:** Yük Testi Düzenleyicisi'ni ve Özellikler penceresini kullanarak test yineleme ayarlarını yapılandırmak için bir yük testi senaryosu düzenleyebilirsiniz. Varsayılan olarak, bir senaryo yok en yüksek test yinelemeleri ile ayarlanır. Yineleme sayısı isteğe bağlı olarak, senaryoda ve bunlar arasında duraklatmak için ne kadar süreyle da yapılandırabilirsiniz.|-   [Senaryolar için test yinelemelerini yapılandırma](../test/configure-test-iterations-in-a-load-test-scenario.md)|
|**Senaryonuz için gecikme ayarlarını yapılandırın:** Yük Testi Düzenleyicisi'ni ve Özellikler penceresini kullanarak, bir gecikme senaryo bir yük testi başlatmadan önce belirtebilirsiniz. Ne zaman kullanmak isteyebilirsiniz örneği **gecikme başlangıç zamanı** özelliği olan başka bir senaryonun tükettiği öğeleri oluşturmaya başlamak için bir senaryo ihtiyacınız varsa. Bazı verileri doldurmak üretmeye senaryosunu sağlamak üzere tüketim senaryosunu geciktirebilir.|-   [Senaryo Başlatma Gecikmelerini Yapılandırma](../test/configure-scenario-start-delays.md)|
|**Bir yük testi senaryosunda kullanılacak uzak makineleri belirtin:** bir yük testi oluşturduğunuzda, dahil etmek istediğiniz hangi test aracılarını belirtmek için yük testi senaryonuzun özelliklerini düzenleyebilirsiniz. Daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).|-   [Nasıl yapılır: kullanılacak Test aracıları belirtme](../test/how-to-specify-test-agents-to-use-in-load-test-scenarios.md)|

## <a name="see-also"></a>Ayrıca bkz.

- [Düzenleme yük testleri](../test/edit-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)