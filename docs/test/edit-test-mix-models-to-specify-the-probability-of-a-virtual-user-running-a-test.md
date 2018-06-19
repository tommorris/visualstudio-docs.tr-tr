---
title: Visual Studio'da karışımı modellerini düzenleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, virtual users
ms.assetid: e3b7d952-9012-400a-8131-3444390a6066
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 591bdaa84d143dc3b639990530a68246dc00385a
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32425341"
---
# <a name="edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test"></a>Bir Test çalıştıran sanal kullanıcı olasılığını belirtmek için Test karışımı modellerini düzenleme

*Test karışımı modeli* bir yük testi senaryosunda belirli bir test çalıştıran sanal kullanıcı olasılığını belirtir. Bu, yük daha gerçekçi benzetimini sağlar. Tek bir iş akışı uygulamalarınız aracılığıyla sahip olmak yerine birkaç iş akışları, son kullanıcıların uygulamalarınızla nasıl etkileşim akışınız olduğu olabilir.

## <a name="test-mix-model-options"></a>Test karışımı modeli seçenekleri

Yük testi senaryonuz için aşağıdaki test karışımı modeli seçeneklerinden birini belirtebilirsiniz:

-   **Testleri toplam sayısına göre:** hangi Web performans veya birim testi sanal kullanıcı test yineleme başladığında çalıştırıldığında belirler. Yük testi sonunda, belirli bir testi çalıştırıldığı sayısı atanan test dağıtım ile eşleşir. Bu test karışımı modeli işlem yüzdeleri bir IIS günlüğü veya üretim verileri üzerinde test karışımı alma kullanın.

-   **Sanal kullanıcı sayısına göre:** belirli bir Web performans veya birim testi çalıştıracak sanal kullanıcıların yüzdesini belirler. Yük testindeki herhangi bir noktada, belirli bir testi çalıştıran kullanıcıların sayısını atanan dağıtım ile eşleşir. Bu test karışımı modeli test karışımı kullanıcıların belirli bir testi çalıştırma yüzdesi alma kullanın.

-   **Kullanıcı adına dayalı:** bir belirtilen sayıda saat başına kullanıcı başına yük testi süresince her Web performans testi veya birim testi çalıştırılır. Yük testi boyunca belirli bir hızda testi sanal kullanıcı istediğinizde bu test karışımı modeli kullanın.

-   **Sıralı sırasına göre:** her sanal kullanıcı testleri senaryoda tanımlanan sırayla Web performans veya birim testleri çalıştırır. Sanal kullanıcı yük testi tamamlanana kadar bu sırayla testlerin dolaşma devam eder.

## <a name="tasks"></a>Görevler

|Görevler|İlişkili Konular|
|-----------|-----------------------|
|**Yük testi için test karışımını belirtme:** bir yük testi oluşturduğunuzda, Yeni Yük Testi Sihirbazı ' yük testi için ayarları belirtin. Yeni Yük Testi Sihirbazı'nda mevcut Web ve birim testleri ilk senaryoyu eklemek için seçin. Senaryoya testleri ekledikten sonra senaryo için test karışımını belirtin.<br /><br /> Bir Web sitesi veya yük test ettiğiniz uygulamanın beklenen gerçek dünya kullanımını daha doğru bir şekilde tahmin etmek için yük modeli oluşturma seçeneklerini kullanın. Doğru yük modelini temel alan olmayan bir yük testi yanıltıcı sonuçları oluşturabileceğinden Bunu yapmak önemlidir.|-   [Bir Web sitesi veya uygulama beklenen gerçek dünya kullanımının öykünmesini yapma](../test/emulate-real-world-usage-of-a-web-site-in-a-load-test-using-test-mix-models.md)|
|**Test karışımı modeli düzenleyebilirsiniz:** Yük Testi Düzenleyicisini kullanarak test karışımı modellerini birini kullanmak için bir yük testi senaryosuna değiştirebilirsiniz.||
|**Bir kullanıcı uygulanan test karışımı modeli için ilerleme gecikmesini yapılandırın:** yük testi senaryonuz kullanmak üzere yapılandırılmışsa, **kullanıcı adım testi karışım modeli göre**, nasıl yapılandırılmış ilerleme gecikme dağıtım istediğinizi belirtebilirsiniz.|-   [Nasıl yapılır: kullanıcı adım testi karışım modeli kullanılırken Gecikmesine Dağıtım uygulama](../test/how-to-apply-distribution-to-pacing-delay-when-using-a-user-pace-test-mix-model.md)|

## <a name="change-the-test-mix-model-in-a-scenario"></a>Bir senaryo Test karışımı modeli

Kullanarak yük testi oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** senaryoları özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için.

> [!NOTE]
> Yükleme ayarları özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

Yük Testi Düzenleyicisini kullanarak, bir yük testi senaryosunda test karışımı modeli düzenleyerek değiştirebileceğiniz **Test karışım türü** Özellikleri penceresinde özelliği.

### <a name="to-change-the-test-mix-model"></a>Test karışımı modeli değiştirmek için

1.  Bir yük testi açın.

     Yük Testi Düzenleyicisi görüntülenir. Yük testi ağacı görüntülenir.

2.  İçinde **senaryoları** yük testi ağacı klasörü test yineleme sayısını belirtmek istediğiniz senaryo düğümünü seçin.

3.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Kategoriler ve Özellikler senaryonun görüntülenir.

4.  İçinde **Test karışım türü** özelliği, üç nokta düğmesini seçin ( **...** ).

     Test karışımı Düzenle iletişim kutusu görüntülenir.

5.  Aşağı açılan listesinde seçin **Test karışımı modeli** ve senaryo için kullanmak istediğiniz test karışımı modeli seçin.

6.  (İsteğe bağlı) Test karışımı kullanarak değiştirme **Ekle**, **kaldırmak** ve **Dağıt** düğmeleri ve dağıtım kaydırıcılar. Daha fazla bilgi için bkz: [belirtin testleri INCLUDE bir yük testi senaryosunda Test Karışımını düzenleme](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).

7.  (İsteğe bağlı) Başlatması veya onay kutularını kullanarak ve istenen testleri seçerek sonlandırmak için bir Web performansı ve birim testi belirtin. Daha fazla bilgi için bkz: [öykünen beklenen gerçek dünya kullanımının bir Web sitesi veya uygulama](../test/emulate-real-world-usage-of-a-web-site-in-a-load-test-using-test-mix-models.md).

8.  Seçin **Tamam**.

     **Özellikleri** pencere görüntüler için yeni test karışımı modeli **Test karışım türü** özelliği.

9. Özelliği değiştirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından, yeni kullanarak yük testlerini çalıştırabilirsiniz **Test karışım türü** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)