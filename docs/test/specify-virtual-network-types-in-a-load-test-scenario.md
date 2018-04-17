---
title: Visual Studio Yük testi senaryosunda sanal ağ türlerini belirtme | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, adding networks
- load tests, removing networks
- load tests, virtual networks
- network mix
ms.assetid: 3c4f7874-081a-4ec4-9510-4d6d7d863a11
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: f40c1d26d1b8f28fd72bbcc5eb4842724e2d1e89
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="specify-virtual-network-types-in-a-load-test-scenario"></a>Bir yük testi senaryosunda sanal ağ türlerini belirtme

*Ağ karışımı* bir yük testi senaryosunda daha gerçekçi benzetimini yapmak için bir yöntem sunar. Yükleme yerine tek tek ağ türü ağ türlerini heterojen bir karışımını kullanarak oluşturulur. Son kullanıcıların uygulamalarınızla nasıl etkileşim akışınız oluşturun.

 Ağ karışımı çalıştıran sanal kullanıcı olasılığını belirtir bir verilen *ağ profili*. Bir ağ profili, ağ bant genişliği uygulama katmanında bir benzetimi ' dir. Gecikme benzetimini değil.

 Bir yük testi oluşturduğunuzda, benzetimini yapmak isteyebilirsiniz yük birden fazla tür ağ bağlantısı oluşturuluyor. Ağ karışımı çeşitli ağ türleri sunar. Farklı ağlar benzetilir. Seçeneğini belirlediğinizde bir seçenek gibi `Cable-DSL 1.5Mbps`, bekleme süreleri seçili bant genişliği benzetimini yapmak için testine eklenmiş.

 Ağ karışımı diğer karışım seçenekleri gibi çalışır. Bir ağ türü rastgele ilişkili ağ karışımını temel alarak bir sanal kullanıcıyla seçilir. Bu kullanıcının test karışımında belirtilen olasılığa dayanarak bir özel ağ türü kullanılarak çalıştırılır.

 Ağ karışımı belirttikten sonra Ekle ve ağ türlerini kaldırın. Karışım denetimini kullanarak ağ karışımı dağıtımını de değiştirebilirsiniz.

 Karışım denetimi, kolayca dağıtım senaryosunda ağların ayarlamanıza olanak sağlar.

 Daha fazla bilgi için bkz: [karışımı denetimi hakkında](../test/specify-virtual-network-types-in-a-load-test-scenario.md).

## <a name="true-network-emulation"></a>Gerçek ağ öykünmesi

 Visual Studio Yük testleri de dahil olmak üzere tüm test türleri için yazılım tabanlı gerçek ağ öykünmesini kullanır. Gerçek ağ öykünmesini ağ koşulları tarafından ağ paketlerinin doğrudan düzenlemesi benzetimini yapar. Gerçek ağ öykünücü Ethernet gibi güvenilir bir fiziksel bağlantıyı kullanarak hem kablolu hem de kablosuz ağların davranışını taklit edebilir. Aşağıdaki ağ öznitelikleri gerçek ağ öykünmesine dahil edilir:

-   Gidiş dönüş süresi (gecikme) ağ üzerinden

-   Kullanılabilir bant genişliği

-   Sıraya alma davranışı

-   Paket kaybı

-   Paketlerin yeniden sıralama

-   Hata yayma.

Gerçek ağ öykünmesini Ayrıca ağ paketlerini IP adresleri veya TCP, UDP ve ICMP gibi protokollere göre filtreleme esneklik sağlar.

Gerçek ağ öykünmesini ağ tabanlı uygulama geliştiricileri ve sınayıcılar tarafından istenen bir sınama ortamına öykünmek, performansını değerlendirmek, değişikliğin etkilerini öngörmek veya teknoloji iyileştirmesi hakkında kararlar için kullanılabilir. Donanım test yataklarıyla karşılaştırıldığında, gerçek ağ öykünmesini daha ucuz ve daha esnek bir çözüm değildir.

## <a name="to-add-new-networks-to-a-scenario"></a>Bir senaryoya yeni ağlar eklemek için

1.  Bir senaryo için Ağ Karışımı Belirtme işlemi sırasında seçin **Ekle**.

     Yeni bir ağ giriş kılavuza eklenir.

    > [!NOTE]
    > Görüntülenecek **Ağ Karışımını Düzenle** iletişim kutusu, varolan bir senaryoyu sağ tıklayın ve ardından **Ağ Karışımını Düzenle**.

2.  İçinde **ağ türü** sütun, yeni giriş için oku seçin. İstenen ağ türünü seçin.

3.  (İsteğe bağlı) Test dağıtımını belirtmek için karıştırma denetimini ayarlayın. Daha fazla bilgi için bkz: [karışımı denetimi hakkında](../test/specify-virtual-network-types-in-a-load-test-scenario.md).

4.  Ağları eklemeyi tamamladığınızda seçin **Tamam**.

## <a name="to-remove-networks-from-a-scenario"></a>Senaryodan Ağları kaldırmak için

1.  Bir yük testi açın.

2.  İstediğiniz ağı kaldırmak ve seçmek senaryoyu **Ağ Karışımını Düzenle**. **Ağ Karışımını Düzenle** iletişim kutusu görüntülenir.

3.  Kılavuzdaki ağı seçin ve ardından **kaldırmak**.

4.  (İsteğe bağlı) Test dağıtımını belirtmek için karıştırma denetimini ayarlayın. Daha fazla bilgi için bkz: [karışımı denetimi hakkında](../test/specify-virtual-network-types-in-a-load-test-scenario.md).

5.  Ağları kaldırma bittiğinde seçin **Tamam**.

## <a name="about-the-mix-control"></a>Karışım denetimi hakkında

 Karışım denetimi, testleri, tarayıcı türleri veya bir yük testi senaryosunda ağ türleri arasında dağıtılmış yük yüzdesini ayarlamanıza olanak sağlar. Yüzde değerleri ayarlamak için kaydırıcıyı hareket ettirin. Ağ türleri için karışımını ayarlayarak, belirli bir ağ profili çalıştıran bir yük testi senaryosunda sanal kullanıcı olasılığını belirtir.

 Kaydırıcıyı taşıdığınızda, tüm kullanılabilir öğelerin yüzde değerleri değiştirin. İkiden fazla öğe varsa, ekleme veya kaldırma tutar diğer öğeler arasında eşit olarak dağıtılır. Bu davranışı geçersiz kılmak mümkündür. Belirli bir öğe için kilit sütunundaki onay kutusunu seçerseniz, o öğe için belirtilen yüzde değerini kilitlersiniz. Ardından, kaydırıcıyı taşıdığınızda, ekleme veya kaldırma tutarı yalnızca kalan kilidi açılmış öğeler için uygulanır.

 **Dağıt** düğmesi tüm öğeler arasında eşit yüzde değerleri ayırmak için kullanılır. Örneğin, üç öğe varsa, seçme **Dağıt** 34, 33 ve 33 yüzde değerlerini ayarlar.

> [!WARNING]
> **Dağıt** düğmesi kilitli olan tüm öğeleri geçersiz kılar.

 Yüzde değerleri doğrudan yazmanız da mümkündür **%** Kaydırıcıları kullanmak yerine sütun. Bir yüzde değeri doğrudan girerseniz, diğer öğeler otomatik olarak ayarlar değil.

> [!NOTE]
> Kaydırıcıları toplamı % 100 eklemez veya yüzde değerleri girilen devre dışı bırakılır **%** sütunu olan ondalık basamaktır.

Yüzde değerlerini el ile girdiğinizde, tüm öğelerin toplamının %100 olduğundan emin olmanız gerekir. Toplamı % 100 değilse bir karışımını kaydettiğinizde, oldukları gibi yüzde değerleri kabul edin veya geri dönün ve bunları ayarlamanız istenir. Oldukları gibi bunları kabul etmeyi seçerseniz, bunlar % 100'e eşit olarak bölünecek.  Örneğin, iki öğe varsa ve el ile bunları % 80 ve % 40 olarak ayarlamanız, ilk öğe (120 bölünmüş 80) % 66.67 ayarlamak ve ikinci öğe %33.33 (120 bölünmüş 40) ayarlayın.