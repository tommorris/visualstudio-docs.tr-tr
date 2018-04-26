---
title: Bir Simgenin veya Dekoratörün Görünürlüğünü Denetleme
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2f2e0671229635eb3dd5fdd50aca15ce11d1ac3a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="controlling-the-visibility-of-an-icon-or-decorator"></a>Bir Simgenin veya Dekoratörün Görünürlüğünü Denetleme
A *oluşturma öğesi* bir simge ya da bir etki alanına özgü dil (DSL) şeklinde görünür metin satırının. Oluşturma öğesi görünmesi yapın ve model özelliklerinde durumunu bağlı olarak kaybolur. Örneğin, bir kişinin temsil eden bir şekli üzerinde alt, sayısını kişinin cinsiyeti bağlı olarak görünür ve benzeri farklı simgeleri olabilir.

## <a name="controlling-the-visibility-of-an-icon-or-decorator"></a>Simge veya oluşturma öğesi görünürlüğünü denetleme
 Aşağıdaki yordam, zaten bir şekli ve onun eşleme bir etki alanı sınıfa tanımladığınız varsayılır. Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md).

#### <a name="to-control-the-visibility-of-an-icon-or-text-decorator"></a>Bir simge veya metin oluşturma öğesi görünürlüğünü denetlemek için

1.  DSL tanımı şemada, simgeler veya görünmesini istediğiniz metin dekoratörler şekli sınıfına ekleyin.

    1.  Shape sınıfı sağ tıklayın, fareyle **Ekle**ve oluşturma öğesi gerekli tür'ı tıklatın.

    2.  Oluşturma öğesi'nin ayarlamak **konumu** özelliği. Birden fazla oluşturma öğesi aynı konuma sahip olabilir. Örneğin, erkek ve aynı konumda paylaşımı kadın simgelerini olabilir.

    3.  Ayarlama **varsayılan simgesi** bir simge oluşturma öğesi özelliği.

2.  Şekil ve DSL tanımı diyagramda etki alanı sınıf arasında bir gri satır diyagram öğesi harita seçin.

3.  DSL Ayrıntıları penceresinde içinde **oluşturma öğesi eşlemeleri** sekmesinde, bir oluşturma öğesi seçin. Örneğin, MaleDecorator.

4.  Denetleme **görünürlük filtre** kutusu.

5.  Hemen etki alanı sınıf üzerinde görünürlük denetlemesi gerekir etki alanı özelliği olan ise bırakın **filtre özelliğe yol** boş.

     Aksi takdirde açılır menüsünü tıklatın ve ilişki veya özellik bulunduğu sınıfı gidin.

    -   Bir hata raporu önlemek için ile işaretli bir ilişki gezinmek değil "*" gezinme aracında.

6.  Ayarlama **filtre özelliği** etki alanı özelliği. Örneğin, cinsiyeti.

7.  İçinde **görünürlük girişleri** listesinde, oluşturma öğesi görünür olacağı bu etki alanı özellik değerlerini ekleyin. Örneğin, erkek.

8.  Her simge için arasındaki adımları yineleyin.

9. **Tüm Şablonları dönüştürme**, derleme ve çalıştırma ve test diyagramı açın.

10. Denetleme özelliği değeri değiştirdiğinizde, dekoratörler kayboluyor görünür ve.

 Genelde, basit bir değerler kümesi'den daha karmaşık bir formül tarafından denetlenmesi için görünürlük istiyorsunuz. Örneğin, belirli bir türdeki bağlantılar sayısına bağlı bir simgesi vardır ya da bir olup olmadığına göre değişir yapmak için bir belirli bir aralıkta sayıdır. Bu durumda, aşağıdaki yordamı kullanın.

#### <a name="to-control-the-visibility-of-a-decorator-based-on-a-formula"></a>Bir formüle dayanarak oluşturma öğesi görünürlüğünü denetlemek için

1.  Bir hesaplanan etki alanı özelliği etki alanı sınıfına ekleyin. İçinde **özellikleri** penceresinde, aşağıdaki değerleri ayarlayın:

     **IsBrowsable =**`False`**-bu özellik kullanıcıdan gizler** 

     **Tür =**`Calculated`**-bu değeri hesaplar kodu sağlayacaktır anlamına gelir.** 

     **Ad** örneğin **DecoratorControl**

     **Türü** = `Boolean`

     Daha fazla bilgi için bkz: [hesaplanan ve özel depolama özellikleri](../modeling/calculated-and-custom-storage-properties.md).

2.  Yeni özellik oluşturma öğesi görünürlük kontrol edin.

    1.  Etki alanı sınıfından gri satır şeklin diyagram öğesi harita seçin. İçinde **DSL ayrıntıları** penceresi açık **DecoratorMap** sekmesi.

    2.  Denetleme **görünürlük filtre** kutusu.

    3.  İçinde **filtre özelliği**, denetim özelliğini seçin **DecoratorControl**.

    4.  Altında **görünürlük girişleri**, girin `True`.

3.  Tıklatın **tüm şablonları dönüştürme** Çözüm Gezgini araç çubuğunda.

4.  Tıklatın **yapı çözümü** üzerinde **yapı** menüsü.

5.  Görüntülendi hata raporu çift tıklatın: "*YourClass* GetDecoratorControlValue için tanıma sahip değil...".

     Metin Düzenleyici üzerinde Dsl\GeneratedCode\DomainClasses.cs açar. Vurgulanan hata bir yöntem eklemek için istek bir açıklamadır.

6.  Ad alanı, sınıf ve yöntemi eksik olan unutmayın.  Örneğin, Company.FamilyTree.Person.GetDecoratorControlValue().

7.  Ayrı kod dosyasında eksik yöntemini içeren bir parçalı sınıf tanımı yazma. Örneğin:

    ```
    namespace Company.FamilyTree
    { partial class Person
      { bool GetDecoratorControlValue()
        {
          return this.Children.Count > 0;
    } } }
    ```

     Program kodunu modeliyle özelleştirme hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).

8.  Yeniden oluşturun ve çözümü çalıştırın.

## <a name="see-also"></a>Ayrıca Bkz.

- [Şekiller ve Bağlayıcıları Tanımlama](../modeling/defining-shapes-and-connectors.md)
- [Diyagram Üzerinde Arka Plan Görüntüsü Ayarlama](../modeling/setting-a-background-image-on-a-diagram.md)
- [Program Kodunda Modeli Gezinme ve Güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)
- [Etki Alanına Özgü Dili Özelleştirmek için Kod Yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)