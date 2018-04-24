---
title: Etki Alanı Rollerinin Özellikleri
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: ead7128c998b8c4ed97acac0f6da0f08113e7bef
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="properties-of-domain-roles"></a>Etki Alanı Rollerinin Özellikleri
Bir etki alanı rol ile ilişkili aşağıdaki tabloda özelliklerdir. Etki alanı rolleri hakkında daha fazla bilgi için bkz: [anlama modelleri, sınıflar ve ilişkiler](../modeling/understanding-models-classes-and-relationships.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

|Özellik|Açıklama|Varsayılan|
|--------------|-----------------|-------------|
|Koleksiyon türü|Bu rol 0 çokluğu varsa.. * ya da 1... \*, bu özellik bağlantıları koleksiyonunu depolamak için kullanılan genel tür özelleştirir.|`(none)` - <xref:Microsoft.VisualStudio.Modeling.LinkedElementCollection%601> kullanılır|
|Özel Öznitelikler|Burada belirttiğiniz öznitelikleri için oluşturulan kodun sınıf öznitelikleri olarak eklenir.|< yok\>|
|Özellik gözatılamaz mi|Varsa `True`, ve kullanıcı tarafından ilişkinin çoğulluk değerinin 0.. 1 çokluğa veya 1..1 ise, rol özellik gözatılabilir **özellikleri** penceresi. Özelliği ilişki bağlantısı diğer ucunda öğesinin adını görüntüler.|`True`|
|Özellik Oluşturucusu|Varsa `True`, bir rol özelliği ilişki program kodundaki çapraz geçiş için kullanabileceğiniz bu rol için oluşturulur. Bu yanlış ayarlarsanız, etki alanı ilişkisinin statik yöntemler kullanarak ilişki daha az verimli bir şekilde geçiş yapabilirsiniz.|`True`|
|Özellik alıcısı erişim değiştiricisi|Oluşturulan özellik alıcısı için erişim değiştiricisi (`public`, `internal`, `private`, `protected`, veya `protected internal`).|`public`|
|Özellik ayarlayıcı erişim değiştiricisi|Oluşturulan özellik ayarlayıcı için erişim değiştiricisi (`public`, `internal`, `private`, `protected`, veya `protected internal`).|`public`|
|Çokluk|Ters rol oynayabilir model öğelerinin sayısı (`0..1`, `1..1`, `0..*`, veya `1..*`). Çeşitlilik ise `0..*` veya `1..*`, ardından oluşturulan özellik koleksiyonunu temsil eder; Aksi takdirde, oluşturulan özellik tek model öğesini temsil eder.|İlişki türüne bağlıdır ve bu ilişkiyi kaynak veya hedef rolde olduğunu.|
|Ad|Etki alanı rolün adı. Bu özellik, boşluk içeremez.|Bu rol için rol player etki alanı sınıfının adı.|
|Kopya yayar|`DoNotPropagateCopy` -Kopyalanan rol player bu bağlantıyı kopyası sahip olur.<br /><br /> `PropagateCopyToLinkOnly` -Rol player varolan kopyalanan bağlantı noktaları.<br /><br /> `PropagateCopyToLinkAndOppositeRolePlayer` -Kopyalanan bağlantı ters rol player kopyaya işaret eder.|`PropagateCopyToLinkAndOppositeRolePlayer` katıştırılmış kaynak rolleri için.<br /><br /> `DoNotPropagateCopy` diğer roller.<br /><br /> Daha fazla bilgi için bkz: [kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md)|
|Delete yayar|`True` ilişkili bağlantı silindiğinde, bu rol oynar öğeyi silmek için.|`True` Hedef katıştırma bir rolün.<br /><br /> `False` diğer roller.<br /><br /> Daha fazla bilgi için bkz: [özelleştirme silme davranışı](../modeling/customizing-deletion-behavior.md).|
|Özellik adı|Rol player kodda oluşturulan özelliğinin adı. Bu ad boşluk içeremez.|Bu rol bir sıfır bire varsa ters rolün adını veya bire bir Çokluk; Aksi halde, ters rolünün pluralized adı.|
|Rol Player|Bu rol ilişkisinde oynayabilir öğesi etki alanı sınıfı. Bu özellik salt okunurdur.|Bu rol için rol player etki alanı sınıfı.|
|Notlar|Etki alanı rol ile ilişkili olan resmi olmayan notları.|< yok\>|
|Kategori|Altında oluşturulan özellik görünür kategori **özellikleri** oluşturulan Tasarımcısı penceresinde. Bu özellik boşsa sonra altında oluşturulan özelliği görünür **çeşitli** kategorisi|< yok\>|
|Açıklama|Kod belge için kullanılır ve oluşturulan Tasarımcısı'nın kullanıcı Arabiriminde kullanılan açıklaması.<br /><br /> Oluşturulan özelliği rol player sınıfı için IntelliSense ipucunda açıklama görüntülenir.|`Description for` *rolün tam adı*|
|Görünen ad|Etki alanı rolü için oluşturulan Tasarımcısı'nda görüntülenen ad.|Name özelliği ayarlanmış değeri.|
|Yardım anahtar sözcüğü|Etki alanı rolü için F1 Yardımı dizin oluşturmak için kullanılan isteğe bağlı anahtar sözcük.|\<yok >|
|Özellik görünen adı|Oluşturulan rol özelliği için oluşturulan Tasarımcısı'nda görüntülenen ad.|Özellik adı özelliği ayarlanmış değeri.|

> [!NOTE]
> Varsayılan değer olan bir görünen ad, bir küçük harf karakter öncesinde ve başka bir büyük harf karakter tarafından izlenmeyen her büyük harf karakter önce boşluk ekleyerek ilişkili özelliğin değeri temel alır.

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki Alanı İlişkilerinin Özellikleri](../modeling/properties-of-domain-relationships.md)