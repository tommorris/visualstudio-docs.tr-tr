---
title: Etki Alanı Özelliklerinin Özellikleri
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: e675d0c4cb7826fb0ddc56dc4491be5d126f3410
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="properties-of-domain-properties"></a>Etki Alanı Özelliklerinin Özellikleri
A *etki alanı özelliği* değer tutan bir model öğesi, bir özelliğidir. Örneğin, `Person` etki alanı sınıf özellikleri vardır `Name` ve `BirthDate`. DSL tanımı'nda, etki alanı özellikleri etki alanı sınıfı kutusunda diyagramında ve etki alanı sınıfı DSL Explorer'da altında listelenir. Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md).

> [!NOTE]
>  "Özellik" word iki kullanımı vardır. A *etki alanı özelliği* bir etki alanı sınıf tanımlayan bir özelliktir. Bunun aksine, bir DSL birçok öğeleri sahip *özellikleri*, hangi listelenir **özellikleri** DSL tanımında pencere. Örneğin, her etki alanı özelliği bu konuda açıklanan özellikler kümesi vardır.

 Çalışma zamanında, bir kullanıcı etki alanı sınıfının örnekleri oluşturduğunda, etki alanı özelliklerinin değerlerini Özellikler penceresinde görülebilir ve şekillerdeki görüntülenebilir.

 Çoğu etki alanı özellikleri sıradan CLR özellikleri olarak uygulanır. Ancak, bir programlama açısından bakıldığında, etki alanı özellikleri daha zengin işlevsellik sıradan program özellikleri vardır:

-   Kurallar ve bir özellik durumunu izlemek olayları tanımlayabilirsiniz. Daha fazla bilgi için bkz: [yanıtlama ve yayılıyor değişiklikleri](../modeling/responding-to-and-propagating-changes.md).

-   İşlemler tutarsız durumları önlemeye yardımcı olur. Daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).

 Bir diyagram veya DSL Gezgini'nde bir etki alanı özelliği seçtiğinizde, aşağıdaki öğeleri Özellikleri penceresinde görebilirsiniz. Bu öğelerin nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

|Özellik|Açıklama|Varsayılan Değer|
|--------------|-----------------|-------------------|
|**Açıklama**|Oluşturulan Tasarımcısı kullanıcı arabirimi (UI) belge için kullanılan açıklaması.|\<yok >|
|**Görünen ad**|Bu etki alanı özelliği için oluşturulan Tasarımcısı'nda görüntülenen ad. Boşluk veya noktalama, örneğin "şarkı başlığı" içerebilir.|\<yok >|
|**Öğe adı sağlayıcısı**|Bu yalnızca ayarladıysanız, geçerli `Is Element Name` için `true`. Varsayılan davranışı geçersiz kılma bir etki alanı sınıfının yeni bir öğe için bir ad sağlar kod yazabilirsiniz.<br /><br /> DSL projesinde kodu dosyasında türetilmiş bir sınıf oluşturun <xref:Microsoft.VisualStudio.Modeling.ElementNameProvider>.<br /><br /> Ardından DSL Explorer'da DSL kökündeki sağ tıklayın ve dış türü Ekle'yi tıklatın. Sınıfınızda adını girin.<br /><br /> Bu etki alanı özelliği yeniden seçin ve aşağı açılan listesinde sınıfın adını seçin.|\<yok >|
|**Alıcı erişim değiştiricisi**|Etki alanı sınıfının erişim düzeyini (`public` veya `internal`). Bu, hangi programın kodunu özelliği erişebilirsiniz kapsam denetler.|`public`|
|**Yardım anahtar sözcüğü**|Bu etki alanı özelliği için F1 Yardımı dizin oluşturmak için kullanılan isteğe bağlı anahtar sözcük.|\<yok >|
|**Gözatılamaz olduğu**|Varsa `True`, bu DSL modellerinin açık olduğunda, etki alanı özelliği kullanıcı için Özellikler penceresini görüntülenir.<br /><br /> Varsa `False`, etki alanı özelliği kullanıcı Arabiriminde gizlenir.<br /><br /> Görünür ancak salt okunur etki alanı özelliği yapmak istiyorsanız, Ayarla **UI salt okunur**.|`True`|
|**Öğe adı**|Varsa `True`, bu etki alanı özellik adı, model öğesi DSL Explorer'da olarak görüntülenir.<br /><br /> Yeni model öğelerini bu özellik için benzersiz varsayılan bir değer alır. Bu değerleri nasıl oluşturulacağını denetlemek istiyorsanız, Ayarla **öğesi ad sağlayıcısı**.|`False`|
|**Kullanıcı Arabirimi salt okunur**|Varsa `True`, kullanıcı arabirimini kullanarak etki alanı özelliğinin değeri değiştirilemez. Programlar tarafından hala ayarlanabilir ve Özellikler penceresinde görünür olur.<br /><br /> Kullanıcının etki alanı özelliğinden gizlemek istiyorsanız, Ayarla **olan gözatılamaz**. Programlar tarafından erişimi denetlemek istiyorsanız, **ayarlayıcı erişim değiştiricisi**.|`False`|
|**türü**|Etki alanı özelliğin türünü (`Normal`, `Calculated`, veya `CustomStorage`). Daha fazla bilgi için bkz: [hesaplanan ve özel depolama özellikleri](../modeling/calculated-and-custom-storage-properties.md).|`Normal`|
|**Ad**|Bu etki alanı özelliğinin adı. Geçerli bir tanımlayıcı örneğin olmalıdır **SongTitle**.|\<yok >|
|**Notlar**|Bu etki alanı özelliğiyle ilişkili resmi olmayan notları.|\<yok >|
|**Ayarlayıcı erişim değiştiricisi**|Ayarlayıcı için erişim değiştiricisi. Bu, hangi programın kodunu özelliği de ayarlayabilirsiniz kapsam denetler.|`public`|
|**Türü**|Özelliğin türü. Kullanılabilir türler listesine eklemek için DSL Explorer'da DSL kökündeki sağ tıklayın ve tıklayın **dış türü Ekle**.|`String`|

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)