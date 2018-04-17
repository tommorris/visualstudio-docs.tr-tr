---
title: Visual Studio'da Test yük için tarayıcı test karışımı | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, web browser types
- load tests, scenarios
- load tests, adding browsers
- load tests, removing browsers
ms.assetid: 47f981d9-3038-45cc-a486-82b9daf9a9a1
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: be0bd036c907f852028f6a9cccc798742e624184
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario"></a>Hangi Web belirtmek için Test Karışımını düzenleme tarayıcısı türlerini bir yük testi senaryosu

*Tarayıcı karışımı* bir yük testi senaryosunda daha gerçekçi benzetimini yapmak için bir yöntem sunar. Yükleme, Web tarayıcıları heterojen bir karışımını yerine tek bir Web tarayıcısı kullanılarak oluşturulur. Akışınız uygulamalarınızla kullanılacak Web tarayıcıları oluşturun.

 Tarayıcı karışımı belirli bir Web tarayıcısı türü çalıştıran bir yük testi senaryosunda sanal kullanıcı olasılığını belirtir. Bir yük testi oluşturduğunuzda, yükleme birden fazla Web tarayıcısı aracılığıyla oluşturulur benzetimini yapmak isteyebilirsiniz. Sağlanan Web tarayıcıları kümesinden Karışıma bir Web tarayıcısı türü eklediğinizde, bir Web performans testi tarafından gönderilen her HTTP isteği seçilen Web tarayıcısı için ilişkili üstbilgi kümesi eklenir.

 Tarayıcı karışımı diğer karışım seçenekleri gibi çalışır. Bir Web tarayıcısı türü, tarayıcı karışımına dayanarak sanal bir kullanıcı rasgele ilişkilidir. Bu kullanıcının testleri karışımında belirtilen olasılık göre belirli bir Web tarayıcısı üzerinde çalışır.

 Tarayıcı karışımı belirttikten sonra daha sonra ekleyebilir ve Web tarayıcı türleri Karışıma kaldırın. Karışım denetimini tarayıcı karışımını dağıtımını da değiştirebilirsiniz. Karışım denetimi, kolayca bir senaryo tarayıcılarda dağıtım ayarlamanıza olanak sağlar.

## <a name="adding-new-browsers-to-a-scenario"></a>Senaryoya yeni tarayıcılar ekleme

### <a name="to-add-new-browsers-to-a-scenario"></a>Bir senaryoya yeni tarayıcılar eklemek için

1.  Bir senaryo için tarayıcı karışımını belirtme işleminde seçin sırada **Ekle**.

     Yeni bir tarayıcı girdisi kılavuza eklenir.

    > [!NOTE]
    > Görüntülenecek **Tarayıcı Karışımını Düzenle** iletişim kutusu, varolan bir senaryoyu sağ tıklayın ve ardından **Tarayıcı Karışımını Düzenle**.

2.  İçinde **tarayıcı türü** sütun, yeni giriş için oku seçin ve istenen tarayıcı türü seçin.

3.  (İsteğe bağlı) Test dağıtımını belirtmek için karıştırma denetimini ayarlayın.

4.  Tarayıcıları eklemeyi tamamladığınızda seçin **Tamam**.

##  <a name="EditingTestMixSpecifyBrowserRemovingBrowserTypes"></a> Senaryodan Tarayıcıları Kaldırma

### <a name="to-remove-browsers-from-a-scenario"></a>Senaryodan Tarayıcıları kaldırmak için

1.  Bir yük testi açın.

2.  Bir tarayıcı kaldırın ve ardından istediğiniz senaryoyu **Tarayıcı Karışımını Düzenle**.

     **Tarayıcı Karışımını Düzenle** iletişim kutusu görüntülenir.

3.  Kılavuzdaki tarayıcıyı seçin ve ardından **kaldırmak**.

4.  (İsteğe bağlı) Test dağıtımını belirtmek için karıştırma denetimini ayarlayın.

5.  Tarayıcıları kaldırma bittiğinde seçin **Tamam**.

## <a name="about-the-mix-control"></a>Karışım denetimi hakkında

 Karışım denetimi, testleri, tarayıcı türleri veya bir yük testi senaryosunda ağ türleri arasında dağıtılmış yük yüzdesini ayarlamanıza olanak sağlar. Yüzde değerleri kaydırıcılar hareket ettirilerek ayarlanır. Tarayıcı türleri için karışımını ayarlama belirli tarayıcı türü çalıştıran bir yük testi senaryosunda sanal kullanıcı olasılığını belirtir.

 Kaydırıcıyı taşıdığınızda, tüm kullanılabilir öğelerin yüzde değerleri değiştirin. İkiden fazla öğe varsa, ekleme veya kaldırma tutar diğer öğeler arasında eşit olarak dağıtılır. Bu davranışı geçersiz kılmak mümkündür. Belirli bir öğe için kilit sütunundaki onay kutusunu seçerseniz, o öğe için belirtilen yüzde değerini kilitlersiniz. Ardından, kaydırıcıyı taşıdığınızda, ekleme veya kaldırma tutarı yalnızca kalan kilidi açılmış öğeler için uygulanır.

 **Dağıt** düğmesi tüm öğeler arasında eşit yüzde değerleri ayırmak için kullanılır. Örneğin, üç öğe varsa, seçme **Dağıt** 34, 33 ve 33 yüzde değerlerini ayarlar.

> [!WARNING]
> **Dağıt** düğmesi kilitli olan tüm öğeleri geçersiz kılar.

 Yüzde değerleri doğrudan yazmanız da mümkündür **%** Kaydırıcıları kullanmak yerine sütun. Bir yüzde değeri doğrudan girerseniz, diğer öğeler otomatik olarak ayarlar değil.

> [!NOTE]
> Kaydırıcıları toplamı % 100 eklemez veya yüzde değerleri girilen devre dışı bırakılır **%** sütunu olan ondalık basamaktır.

 Yüzde değerlerini el ile girdiğinizde, tüm öğelerin toplamının %100 olduğundan emin olmanız gerekir. Bir karışımı kaydettiğinizde, toplam %100 değilse, yüzde değerlerini oldukları gibi kabul etmeniz veya geri gidip onları ayarlamanız istenir. Oldukları gibi bunları kabul etmeyi seçerseniz, bunlar % 100'e eşit olarak bölünecek.  Örneğin, iki öğe varsa ve el ile bunları % 80 ve % 40 olarak ayarlamanız, ilk öğe (120 bölünmüş 80) % 66.67 ayarlamak ve ikinci öğe %33.33 (120 bölünmüş 40) ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)