---
title: "Oluşturma ve Visual Studio Yük testi çalıştırma | Microsoft Docs"
ms.date: 10/01/2016
ms.topic: article
helpviewer_keywords:
- unit tests, in load tests
- unit tests, load test walkthrough
- load tests, walkthrough
ms.assetid: bbf075a5-96d5-48ed-a03c-330f0fc04748
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 53bde20393f5acd55295bf106cb35f6f09e68bf3
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="walkthrough-create-and-run-a-load-test-that-contains-unit-tests"></a>İzlenecek yol: Oluşturma ve birim testleri içeren bir yük testi çalıştırma

Bu kılavuzda birim testleri içeren bir yük testi oluşturun.

Bu kılavuz size oluşturma ve Visual Studio Enterprise kullanarak bir yük testi çalıştırma adımları. Bir yük testi Web performans testleri ve birim testleri bir kapsayıcıdır. Yük testleri Yeni Yük Testi Sihirbazı ile oluşturun.

Bir yük testi da istenen yük benzetimini oluşturacak şekilde değiştirilebilir birçok çalışma zamanı özellikleri sunar. Bu kılavuzda, bir yük testi için birim testleri eklemek için Yeni Yük Testi Sihirbazı'nı kullanın.

Bu kılavuzda, aşağıdaki görevleri tamamlar:

-   Birim testleri kullanan bir yük testi oluşturun.

-   Bazı yük testi ayarlarını değiştirin.

-   Bir yük testi çalıştırın.

-   Bölümündeki adımları gerçekleştirdikten [izlenecek yol: yönetilen kod için birim testleri oluşturma ve çalışan](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md) Web içeren bir basit C# sınıf kitaplığı oluşturmak için performans ve yük proje bazı Birim testleri test.

## <a name="create-a-load-test-containing-unit-tests-using-the-new-load-test-wizard"></a>Yeni Yük Testi Sihirbazı'nı kullanarak birim testleri içeren bir yük testi oluşturma

### <a name="to-start-the-new-load-test-wizard"></a>Yeni Yük Testi Sihirbazı'nı başlatmak için

1.  Oluşturduğunuz Banka çözümünü açın [izlenecek yol: yönetilen kod için birim testleri oluşturma ve çalışan](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md).

2.  İçinde **Çözüm Gezgini**, banka çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.

     Yeni Proje Ekle iletişim kutusu görüntüler.

3.  Yeni Proje Ekle iletişim kutusunda genişletin **Visual C#** ve **Test**. Şablonları listesinden seçim **Web performansı ve yük testi projesi** ve **adı** alanı, tür `BankLoadTest`. Seçin **Tamam**.

     BankLoadTest web performansı ve yük testi proje çözüme eklenir.

4.  Açık kısayol menüsünün projesi, yeni BankLoadTest web performansı ve yük testi seçin **Ekle**ve ardından **yük testi**.

5.  **Yeni Yük Testi Sihirbazı** başlatır.

6.  **Hoş Geldiniz** sayfasında **Yeni Yük Testi Sihirbazı** ilk sayfa verilmiştir.

7.  Seçin **sonraki**.

### <a name="to-edit-settings-for-load-test-scenario"></a>Yük testi senaryosuna ayarlarını düzenlemek için

1.  İçinde **yük testi senaryosu için bir ad girin** metin kutusunda, **ScenarioSample**.

     A *senaryo* bir gruplandırma mekanizmasıdır. Bir dizi testleri ve yük altında bu testleri çalıştırmak için özellikleri oluşur.

2.  Ayarlama **profil düşünme süresi** için `Use normal distribution centered on recorded think times`. Düşünme süreleri bir kullanıcı bir sonraki sayfaya geçmeden önce bir Web sayfasında düşündüğü zamanı temsil eder.

1.  Seçin **sonraki** işiniz bittiğinde.

### <a name="to-edit-load-pattern-setting-for-test-scenario"></a>Test senaryosu için yük düzeni ayarını düzenlemek için

1.  Seçin **Adım yük**.

    > [!NOTE]
    > Yük desenleri iki türlerinden birini seçebilirsiniz: sabit ve adım. Yük testi, ancak bu kılavuzun amacıyla seçin işlevini her türüne sahip **Adım yük**.

2.  Ayarlama **Başlat kullanıcı sayısı** 10 kullanıcılara.

3.  Ayarlama **adım süresi** 10 saniye.

4.  Ayarlama **adım kullanıcı sayısı** 10 kullanıcıları/adıma.

5.  Ayarlama **maksimum kullanıcı sayısı** ila 100 kullanıcı.

6.  Seçin **sonraki**.

### <a name="to-select-test-mix-model-for-the-scenario"></a>Senaryo için test karışımı modeli seçmek için

1.  Altındaki test karışımı modellenmesi seçin **test toplam sayısına göre**.

2.  Seçin **sonraki**.

### <a name="to-add-unit-tests-to-the-scenario"></a>Birim testleri senaryoya eklemek için

1.  Sonraki adım **Ekle testleri bir yük testi senaryosundaki ve test karışımını düzenleme**.

2.  Seçin **Ekle** testleri seçmek için.

3.  Listelenen CreditTest birim testleri seçin **kullanılabilir testler** tüm Web performansı ve yük testi projesi birim testleri ve Web performans testleri listeler bölmesi.

4.  CreditTest birim testine eklemek için oku seçin **Seçili testler** bölmesi.

5.  DebitTest FreezeAccountTest için birim testleri ve 3 ve 4 numaralı adımları tekrarlayın.

6.  Üç birim testleri eklemeyi bitirdiğinizde seçin **Tamam**.

     Test karışımı ile sunulur.

7.  Dağıtım için CreditTest altındaki kaydırma çubuğunun biraz test dağıtım ayarlamak için sağa taşıyın. % 100 oranında dağıtım kalmayacak şekilde otomatik olarak diğer kaydırıcıyı sola taşı dikkat edin.

8.  Seçin **sonraki**.

### <a name="to-select-network-mix-for-test-scenario"></a>Test senaryosu için ağ karışımı seçmek için

1.  Ağ bant genişliği karışımına eklenecek LAN bağlantı türünü seçin.

     Daha fazla ağ türü ekleyebilirsiniz. Test dağıtımını ve ağırlığını ayarlamak için kaydırıcıyı kullanın.

2.  Seçin **sonraki**.

### <a name="to-specify-computers-to-monitor-with-counter-sets-during-load-test-run"></a>Yük testi sırasında sayaç kümeleriyle izlemek için bilgisayarları belirtmek için

1.  Seçin **sonraki**.

     Sayaç kümeleri hakkında daha fazla bilgi için bkz: [sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testinde belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

### <a name="to-edit-run-setting-for-load-test"></a>Yük testi çalışma ayarı düzenlemek için

1.  Seçin **yük test süresi** ve ardından **çalışma süresi** için 2 dakika *duman testi* yük testi.

     Yük testleri oluşturduğunuzda, her şeyin doğru şekilde yapılandırılmış ve kısa, açık yük testi çalıştırarak beklendiği gibi çalışıyor olduğunu doğrulamak için iyi bir uygulamadır. Bu işlem olarak bilinir *duman testi*.

2.  Seçin **son**. Yük testi açılır **Yük Testi Düzenleyicisi**.

## <a name="running-the-load-test"></a>Yük testi çalıştırma
 Yük testi oluşturduktan sonra yük benzetimi banka uygulamanızı nasıl yanıt vereceğini görüntülemek için çalıştırın. Bir yük testi çalışırken, gördüğünüz **Yük Testi Çözümleyicisi** penceresi.

### <a name="to-run-the-load-test"></a>Yük testi çalıştırmak için

1.  Yük testi Aç ile **Yük Testi Düzenleyicisi**, yeşil seçin **testi Çalıştır** araç çubuğu düğmesi. Yük testi çalışmaya başlar.

2.  Test benzetim herhangi eşiklerini aşarsa, simgeler eşik ihlali göstermek için ağaç denetimi düğümlerinde görünür. Kaplama kırmızı bir daire hatalar var, uyarılar kaplama sarı bir üçgen sahiptir. Eşiği aşan bir sayaç bulun ve grafiğine simgesi sürükleyerek grafik. Test çalışırken bunu yapabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Hangi testlerin bir yük testi senaryosunda ekleneceğini belirlemek için Test Karışımını düzenleme](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)
- [Sanal ağ türlerini belirtme](../test/specify-virtual-network-types-in-a-load-test-scenario.md)
- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Sanal kullanıcı etkinlikleri modellemek için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md)
- [Bir Test çalıştıran sanal kullanıcı olasılığını belirtmek için test karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)