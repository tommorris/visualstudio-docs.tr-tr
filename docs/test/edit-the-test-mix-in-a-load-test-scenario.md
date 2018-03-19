---
title: "Visual Studio Yük testi senaryosunda için test karışımını | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, adding tests
- test mix
- load tests, test mix
- load tests, removing tests
ms.assetid: 303e1d70-5d98-424a-b51e-e0898e16d3f8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 20437bf88d62943d6f0dbf3d9df320836c5e9e36
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="edit-the-test-mix-to-specify-which-web-performance-unit-and-coded-ui-tests-to-include-in-a-load-test-scenario"></a>Hangi Web başarımı, birim ve kodlanmış UI testleri bir yük testi senaryosunda içerecek şekilde belirlemek için Test Karışımını düzenleme

*Test karışımı* bir senaryo senaryoda içerilen Web performansı ve birim testleri seçimi ve bu testlerin senaryoda dağıtımını bir birleşimidir. Dağıtım için belirli bir testi bir yük testi çalışma sırasında sanal bir kullanıcı tarafından seçilir olasılık belirtebileceğiniz bir ayardır.

 Bir yük testi için test kümesi ekledikten sonra *test karışımı* karışımı seçenekleri diğer gibi çalışır. Sanal kullanıcı, bir test karışımında belirtilen olasılığa dayanarak, rastgele seçer. Örneğin, iki testler, her yüzde 50 karışımında varsa, ilk testi yaklaşık yarım saatte çalıştırmak yeni bir sanal kullanıcı seçer. Bir 50/50 karışımında bir test uzun ise ve diğeri kısaysa, uzun testten daha fazla yük gelir.

 Karışıma testleri ekledikten sonra bunları kaldırabilirsiniz. Test karışımı dağıtımını Karışım denetimini kullanarak da değiştirebilirsiniz. Karışım denetimi, kolayca bir senaryoda testlerin dağıtımını ayarlamanıza olanak sağlar.

> [!NOTE]
> Dağıtım, belirli bir testi bir yük testi çalışma sırasında sanal bir kullanıcı tarafından seçilir olasılık ölçüsüdür. Dağıtım yüzde olarak ifade edilir. Bu nedenle, bir senaryoda içerilen tüm testler için dağıtım sayılarının toplamını 100'dür. Örneğin, bir senaryo yalnızca bir test içeriyorsa, bu test için dağıtım yüzde 100'dür.

## <a name="add-new-tests-to-a-test-mix-in-an-existing-scenario"></a>Varolan bir senaryoyu Test karışımında yeni testleri ekleme

Yeni Yük Testi Sihirbazı'nı kullanarak yeni bir senaryoya oluşturduğunuzda, yeni senaryonun test karışımı eklemek için Web performansı ve birim testleri belirtebilirsiniz.

Yük Testi Düzenleyicisini kullanarak karışımına senaryo için daha fazla Web performansı ve birim testleri ekleyebilirsiniz.

![Mevcut bir yük testi için test ekleme](../test/media/ltest_addingtests.png "LTest_AddingTests")

### <a name="to-add-more-tests-to-an-existing-scenario"></a>Daha fazla testleri varolan bir senaryoyu eklemek için

1.  Bir yük testi açın.

2.  Yük Testi Düzenleyicisi'nde, varolan bir senaryoyu sağ tıklayın ve ardından **testler Ekle**.

     **Testler Ekle** iletişim kutusu görüntülenir. Tüm Web performans, birim ve senaryonuzda olmayan kodlanmış UI testleri çözümünüzdeki senaryoya eklemek kullanılabilir.

3.  İçinde **kullanılabilir testler** bölmesinde Web performans, birim ve eklemek istediğiniz kodlanmış UI testleri seçin. Testleri eklemek için sağ oka seçin **seçili testleri** bölmesi.

4.  Testleri eklemeyi bitirdiğinizde, seçin **Tamam**.

     Testler için test karışımını eklenir. Yeni bir dağıtım testleri test karışımında otomatik olarak atanır.

5.  (İsteğe bağlı) Test dağıtımını belirtmek için karıştırma denetimini ayarlayın. Daha fazla bilgi için bkz: [karışımı denetimi hakkında](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).

##  <a name="EditingTestMixRemoveTest"></a> Senaryodan testleri kaldırma
 ![Varolan yük testten test kaldırma](../test/media/ltest_removetest.png "LTest_RemoveTest")

### <a name="to-remove-tests-from-a-scenario"></a>Senaryodan testleri kaldırmak için

1.  Bir yük testi açın.

2.  Yük Testi Düzenleyicisi'nde, yük testi ağacında, istediğiniz bir test ve kaldırmak senaryoyu **Test Karışımını düzenleme**. **Test Karışımını düzenleme** iletişim kutusu görüntülenir.

3.  Web performans, birim ve kodlanmış UI testi kılavuzdaki seçin ve ardından **kaldırmak**.

    > [!NOTE]
    > Test kaldırdıktan sonra tercih edilen dağıtımınız için test karışımını ayarlayın.

4.  Testleri kaldırma bitirdikten sonra Seç **Tamam**.

##  <a name="EditingTestMixAboutMixControl"></a> Karışım denetimi hakkında
 Karışım denetimi, testleri, tarayıcı türleri veya bir yük testi senaryosunda ağ türleri arasında dağıtılmış yük yüzdesini ayarlamanıza olanak sağlar. Yüzde değerleri kaydırıcılar hareket ettirilerek ayarlanır. Testler için karışımı ayarlamak, bir sanal kullanıcının bir yük testi senaryosunda belirli bir testi çalıştırma olasılığını belirtir.

 Kaydırıcıyı taşıdığınızda, tüm kullanılabilir öğelerin yüzde değerleri değiştirin. İkiden fazla öğe varsa, ekleme veya kaldırma tutar diğer öğeler arasında eşit olarak dağıtılır. Bu davranışı geçersiz kılmak mümkündür. Belirli bir öğe için kilit sütunundaki onay kutusunu seçerseniz, o öğe için belirtilen yüzde değerini kilitlersiniz. Ardından, kaydırıcıyı taşıdığınızda, ekleme veya kaldırma tutarı yalnızca kalan kilidi açılmış öğeler için uygulanır.

 **Dağıt** düğmesi yüzdeyi tüm öğeler arasında eşit ayırmak için kullanılır. Örneğin, üç öğe varsa, seçme **Dağıt** 34, 33 ve 33 yüzde değerlerini ayarlar.

> [!WARNING]
>  **Dağıt** düğmesi kilitli olan tüm öğeleri geçersiz kılar.

 Yüzde değerleri doğrudan yazmanız da mümkündür  **%**  Kaydırıcıları kullanmak yerine sütun. Bir yüzde değeri doğrudan girerseniz, diğer öğeler otomatik olarak ayarlar değil.

> [!NOTE]
>  Kaydırıcıları toplamı % 100 eklemez veya yüzde değerleri girilen devre dışı bırakılır  **%**  sütunu olan ondalık basamaktır.

 Yüzde değerlerini el ile girdiğinizde, tüm öğelerin toplamının %100 olduğundan emin olmanız gerekir. Bir karışımı kaydettiğinizde, toplam %100 değilse, yüzde değerlerini oldukları gibi kabul etmeniz veya geri gidip onları ayarlamanız istenir. Oldukları gibi bunları kabul etmeyi seçerseniz, bunlar % 100'e eşit olarak bölünecek.  Örneğin, iki öğe varsa ve el ile bunları % 80 ve % 40 olarak ayarlamanız, ilk öğe (120 bölünmüş 80) % 66.67 ayarlamak ve ikinci öğe %33.33 (120 bölünmüş 40) ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)