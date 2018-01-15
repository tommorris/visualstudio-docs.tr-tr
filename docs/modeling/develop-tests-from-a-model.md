---
title: "Model aracılığıyla test geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tests and requirements
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9d073178ca9a8bb26e5cffe2d90f347156679416
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="develop-tests-from-a-model"></a>Model aracılığıyla test geliştirme
Sisteminiz ve bileşenlerinin testlerini düzenlemenize yardımcı olması için gereksinimleri ve mimari modelleri kullanabilirsiniz. Bu yöntem kullanıcılar ve diğer Paydaşlar için önemli olan gereksinimleri test ve gereksinimleri değiştiğinde testleri hızlı bir şekilde güncelleştirmenize yardımcı sağlamaya yardımcı olur. Kullanırsanız [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], modeller ve testler arasındaki bağlantıları da koruyabilirsiniz.  
  
 Visual Studio hangi sürümlerinin bu özellikleri desteklediğini görmek için bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="system-and-subsystem-testing"></a>Sistem ve alt sistemi test etme  
 *Sistem sınama,* olarak da bilinen *kabul testi*, kullanıcıların gereksinimlerini karşılayıp karşılamadığını test anlamına gelir. Bu tür sınamalar iç tasarım yerine sistem dışarıdan görünen davranışı hakkında duyarlıdır.  
  
 Sistem testleri genişletmek veya bir sistem yeniden tasarlarken çok değerlidir. Kodu değiştirdiğinizde giriş hatalarından korunmanıza yardımcı olurlar.  
  
 Herhangi bir değişiklik veya bir sistem uzantısı planlarken, mevcut sistemde sistem testleri kümesi ile başlatmak yararlıdır. Ardından genişletin veya yeni gereksinimleri sınamak, kodda değişiklik ve test kümesinin tamamını yeniden çalıştırmak için testleri ayarlayın.  
  
 Yeni bir sistem geliştirirken geliştirme başlar başlamaz testleri oluşturmaya başlayabilirsiniz. Her bir özelliğin geliştirmeden önce testleri tanımlayarak gereksinimler tartışmalarını çok belirli bir şekilde yakalayabilirsiniz.  
  
 Alt sistem testi aynı ilkeleri bir sistem ana bileşenleri için geçerlidir. Her bileşen diğer bileşenlerden ayrı ayrı test edilir. Alt sistemi bileşenin kullanıcı arabirimleri veya API görünür davranışına odaklanmak sınar.  
  
## <a name="deriving-system-tests-from-a-requirements-model"></a>Gereksinimler Modeli'nden Sistem Testleri Türetme  
 Oluşturabilir ve sistem testler ve gereksinimler modeli arasında bir ilişki sürdürebilirsiniz. Bu ilişki kurmak için gereksinimler modelinin ana öğelerine karşılık gelen testler yazma. Visual Studio testleri ve model bölümleri arasında bağlantılar oluşturmanıza izin vererek ilişkiyi sürdürmenize yardımcı olur. Gereksinimleri modelleri hakkında daha fazla bilgi için bkz: [Model kullanıcı gereksinimlerini](../modeling/model-user-requirements.md).  
  
### <a name="write-tests-for-each-use-case"></a>Her kullanım durumu için testleri yazma  
 Kullanırsanız [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], testleri gereksinimler modelinde tanımladığınız her kullanım örneği için bir grup oluşturabilirsiniz. Örneğin, kullanım örneği sipariş oluştur ve siparişe öğe Ekle'yi içeren bir paket varsa, her iki genel testleri oluşturabilirsiniz ve bunların daha ayrıntılı kullanım. 
  
 Bu yönergeler yardımcı olabilir:  
  
-   Her kullanım örneği ana yollar ve özel sonuçlar için çeşitli sınamalar olması gerekir.  
  
-   Kullanım örneği gereksinimler modelinde tanımlamak, onun sonkoşulunu yordamları ayrıntılı bir şekilde tanımlamak için hedefe ulaşmak için kullanıcı izlediği daha diğer bir deyişle, elde hedefi tanımlamak daha önemlidir. Örneğin, sipariş yemek Sonkoşul, olabilir bir restoran yemek bir müşteri için hazırlanıyor ve Müşteri'nin ödeme. Sonkoşul testlerinizin doğrulaması gereken ölçüttür.  
  
-   Ayrı yan tümceleri Sonkoşul temel ayrı testler. Örneğin, sipariş Restoran bildirme ve ödeme müşteriden ayırdığınız için ayrı testleri oluşturun. Bu ayrım şu avantajları vardır:  
  
    -   Gereksinimleri farklı yönlerini değişiklikleri sık bağımsız olarak gerçekleşir. Bu şekilde farklı yönlere testleri ayırarak, gereksinimleri değiştiğinde testleri güncellemeyi kolaylaştırır.  
  
    -   Geliştirme planı önce başka bir kullanım örneğinin tek bir yönüne uygularsa, geliştirme ilerledikçe testleri ayrı ayrı etkinleştirebilirsiniz.  
  
-   Testleri tasarladığınızda seçimi test verileri, kod veya sonkoşulun olup olmadığını belirleyen komut dosyasından ayırın. Örneğin, bir test basit aritmetik işlevinin olabilir: Giriş 4; Çıkış 2 olduğunu doğrulayın. Bunun yerine, komut dosyası olarak tasarlamanız: giriş; seçin tek başına çıkış çarpma ve sonucun özgün giriş olduğundan emin olun. Bu stili test ana gövdesini değiştirmeden test girişleri değiştirmenizi sağlar.  
  
#### <a name="linking-tests-to-use-cases"></a>Kullanım örnekleri için testler bağlama  
 Kullanıyorsanız [!INCLUDE[TCMlong](../modeling/includes/tcmlong_md.md)] tasarlama ve testleri çalıştırmak için testlerinizi gereksinim, kullanım örneği veya kullanıcı hikayesi iş öğeleri altında düzenleyebilirsiniz. Bu bağlantı iş öğelerini modelinizdeki kullanım. Bu hızlı bir şekilde izleme gereksinimleri değişiklikler testleri etkinleştirir ve kullanım örneği her ilerlemesini izlemek yardımcı olur.  
  
###### <a name="to-link-tests-to-a-use-case"></a>Testleri kullanım örneğine bağlamak için  
  
1.  İçinde [!INCLUDE[TCMlong](../modeling/includes/tcmlong_md.md)], bir gereksinim oluşturmanız ve test paketi ona dayandırın.
  
     Oluşturduğunuz bir iş öğesinin gereksinimdir [!INCLUDE[vstsTfsShort](../modeling/includes/vststfsshort_md.md)]. Bir kullanıcı hikayesi, gereksinim veya kullanım örneği iş öğesi ile projenizin kullandığı işlem şablonu bağlı olarak olabilir [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]. Daha fazla bilgi için bkz: [Visual Studio Team Services veya Team Foundation Server kullanarak iş izleme](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503).  
  
2.  Gereksinim çalışma öğesini modelinizdeki bir veya daha fazla kullanım örnekleri bağlayın.  
  
     Kullanım örneği diyagramında kullanım örneğine sağ tıklayın ve ardından **iş öğesi bağlantı**. 
  
3.  Kullanım örneklerini doğrulayan test çalışmaları, test paketine ekleyin.  
  
 Genellikle, her kullanıcı hikayesi veya gereksinim çalışma öğesi modelinizdeki birçok kullanım örneğine bağlar ve her kullanım örneği birkaç kullanıcı yazıları veya gereksinimler bağlayacaksınız. Her kullanıcı hikayesi veya gereksinim birkaç kullanım örnekleri geliştirme görevleri bir dizi kapsar olmasıdır. Örneğin, projenizin erken bir yineleme müşteri Kataloğu'ndan öğeleri seçin ve bunları teslim temel kullanıcı hikayesi geliştirebilir. Bir sonraki yinelemede mal gönderdikten sonra sırasını ve tedarikçi Tamamlanıyor para aldığında ödeyen kullanıcı hikayesi olabilir.  Her hikaye sipariş mal kullanım örneği Sonkoşul için bir yan tümcesi ekler.  
  
 Bu yan tümceleri ayrı açıklamalara kullanım örneği diyagramında yazarak Sonkoşul yan tümcelerini gereksinimlerden ayrı bağlantılar oluşturabilirsiniz. Her açıklamayı gereksinim iş öğesine bağlamak ve açıklamayı diyagramdaki kullanım örneği bağlayabilirsiniz.  
  
### <a name="base-tests-on-the-requirements-types"></a>Gereksinim türleri temel testler  
 Olduğu türleri, sınıflar, arabirimler ve gereksinimleri modelinin numaralandırmalar kavramlar ve kullanıcıların nasıl düşünün ve kendi iş hakkında iletişim bakımından ilişkileri açıklar. Sistem yalnızca iç tasarımı ile ilgili türleri dışlar.  
  
 Bu gereksinim türleri açısından testlerinizi tasarlayın. Bu uygulama gereksinimlerinde yapılacak değişiklikler ele alınmıştır, testleri gerekli değişiklikleri değişiklikleri ilişkilendirilecek kolaydır emin olmanıza yardımcı olur. Bu testler ve son kullanıcılar ve diğer Paydaşlar ile doğrudan hedeflenen sonuçları tartışmak mümkün kılar. Bu, kullanıcıların geliştirme süreci dışında tutulabilir ve tasarımında olası eksiklikler etrafında testlerin yanlışlıkla tasarımını önler anlamına gelir.  
  
 El ile testler için test komut dosyasındaki gereksinimler modeli sözlüğüne bağlılığı bu yöntem içerir. Otomatikleştirilmiş testler için bu yöntem gereksinimleri sınıf diyagramları test kodunuz için temel olarak kullanarak ve erişimci ve güncelleştirici gereksinim modelini koda bağlamak için işlevleri oluşturmayı içerir.  
  
 Örneğin, model içerebilir gereksinimleri menüsü, menü öğesi, sipariş ve onlar arasındaki ilişkileri türleri. Bu model depolanır ve ile sistem sıralama yemek tarafından ele, ancak kendi uygulama karmaşıklığını göstermiyor bilgileri temsil eder. Çalışma sistem veritabanlarında, kullanıcı arabirimleri ve API'leri her tür birkaç farklı gerçekleştirimi olabilir. Dağıtılmış bir sistemde, aynı zamanda sistem farklı kısımlarını depolanan her örneğinin birkaç varyantı olabilir.  
  
 Kullanım örneği sipariş öğesi Ekle gibi test etmek için bir test yöntemi aşağıdakine benzer bir kod dahil olabilir:  
  
```  
Order order = ... ; // set up an order  
// Store prior state:  
int countBefore = order.MenuItems.Count;   
// Perform use case:  
MenuItem chosenItem = ...; // choose an item  
AddItemToOrder (chosenItem, order);   
// Verify part of postcondition:  
int countAfter = order.MenuItems.Count;  
Assert (countAfter == countBefore = 1);   
```  
  
 Bu test yönteminin gereksinimler modeli sınıflarını kullandığına dikkat edin. İlişkilendirmeler ve öznitelikler .NET özelliği olarak gerçekleştirilirler.  
  
 Bunun çalışmasını sağlamak için sınıfların özellikleri salt okunur işlevler veya geçerli durumu hakkında bilgi almak için sisteme ulaşan erişimciler olarak tanımlanmalıdır. AddItemToOrder bir katman veya kendi API aracılığıyla sistem, kullanıcı arabiriminin altındaki sürücü gerekir gibi durumlarda benzetimini yöntemlerini kullanın. Sipariş ve MenuItem gibi test nesneleri Oluşturucular, ayrıca sistem içinde karşılık gelen öğeleri oluşturmak için sistem sürücüsü gerekir.  
  
 Birçok erişimci ve güncelleyici zaten uygulamanın normal API aracılığıyla kullanılabilir. Ancak bazı ek işlevler testleri etkinleştirmek için yazılacak olabilir. Bu ek erişimci ve güncelleyici bazen 'test araçları"olarak bilinir. Sistem iç tasarım bağımlı olduğundan, sınayıcılar gereksinimler modeli açısından testleri için kod yazma ise, onları sağlamak sistem geliştiricilerin sorumluluğundadır.  
  
 Otomatikleştirilmiş testleri yazarken, erişimci ve güncelleyici sarmalamak için genel testleri kullanabilirsiniz.
  
### <a name="tests-for-business-rules"></a>İş kuralları için testler  
 Bazı gereksinimler herhangi bir kullanım durumu için doğrudan ilgili değildir. Örneğin, ŞimdiAkşamYemeği iş birçok menülerden seçim yapmasını sağlar, ancak her sırada gerektiren tüm seçilen öğeler, tek bir menüden olacaktır. Bu iş kuralı siparişler, menüler ve öğeleri arasındaki ilişkileri gereksinimleri sınıf modelindeki hakkında bir değişmez değer olarak ifade edilebilir.  
  
 Bu tür sabit bir kuralı, yalnızca şu anda tanımlı tüm kullanım durumları ancak daha sonra açıklanacak olan ayrıca diğer kullanım örneklerini yönetir. Bu nedenle, herhangi bir kullanım örneğinden ayrı olarak yazma ve kullanım örneklerinden ayrı ayrı test etmek için yararlı olacaktır.  
  
## <a name="deriving-subsystem-tests-from-models"></a>Modellerden alt sistem testleri türetme  
 Büyük bir sistemin üst düzey tasarımında bileşenleri veya alt sistemleri tanımlayabilirsiniz. Bunlar, birçok yolla tasarlanabilen yeniden kullanılabilir modül ayrı olarak tasarlanmış veya farklı bilgisayarlarda bulunan bölümleri temsil eder. 
  
 Tam sistem için kullandığınız her ana bileşene aynı ilkeleri uygulayabilirsiniz. Büyük bir projede her bileşenin kendi gereksinimler modeli olabilir. Daha küçük projelerde mimari model veya üst düzey tasarımı başlıca bileşenleri ve onların etkileşimlerini göstermek için oluşturulabilir. Daha fazla bilgi için bkz: [uygulama Mimarinizi Model](../modeling/model-your-app-s-architecture.md).  
  
 Her iki durumda da gereksinimler modeli ve sistem testleri arasında olduğu gibi aynı şekilde model öğelerini ve alt sistem testleri arasında bir ilişki kurabilirsiniz.  
  
### <a name="isolate-components-with-provided-and-required-interfaces"></a>Sağlanan ve gerekli arabirimleri bileşenleriyle yalıtma  
 Sistem veya dış hizmetler diğer bölümleri bir bileşeni olan tüm bağımlılıkları tanımlamak ve bunları gerekli arabirimler olarak göstermek için kullanışlıdır. Bu alıştırmada, genellikle bileşeni tasarımınız geri kalanından çok daha ayrılmış ve kolayca ayrılabilir bırakır bazı yeniden tasarlanması neden olmaktadır.  
  
 Bu ayırma bir avantajı, bileşen hizmetlerin genellikle kullandığı sahte nesneler ile değiştirerek test etmek için yürütülebilecek olmasıdır. Bu test amacıyla için ayarladığınız bileşenleridir. Sahte bir bileşeni, benzetimli verilerle sorgulara yanıt bileşeniniz gerektirir arabirimi sağlar. Sahte bileşenleri bileşeninin tüm arabirimler için bağlanabilir tam test bandı parçasını oluşturur.  
  
 Sahte sınama bileşeniniz bunu kullanır, hizmetleri halen geliştirilme aşamasındadır diğer bileşenleri sırasında geliştirebilirsiniz avantajdır.  
  
## <a name="maintain-the-relationships-between-tests-and-model"></a>Testler ve Model arasındaki ilişkileri koru  
 Yineleme birkaç haftada gerçekleştiren tipik bir projede, her bir yineleme başlangıcı yakınında gereksinimlerini gözden geçirme tutulur. Toplantı sonraki yinelemede teslim edilecek özellikleri açıklanmaktadır. Gereksinimler modeli kavramlar, senaryolar ve geliştirilecek Eylemler dizisi ele yardımcı olmak için kullanılabilir. İş Paydaşlar önceliklerini ayarlayın, geliştiriciler tahmin yapar ve beklenen bir davranış her özelliğin doğru yakalanan sınayıcılar emin olun.  
  
 Testleri yazmak gereksinim tanımlamak için en etkili yoldur ve ayrıca bir kişi gerekli olan NET bir anlayış olduğundan emin olmak için etkili bir yoldur. Yazma testleri alır ancak belirtim Atölyesi sırasında çok uzun, ancak modelleri oluşturma çok daha hızlı bir şekilde gerçekleştirilebilir.  
  
 Bir sınama açısından bakıldığında, gereksinimler modeli testler için bir toplu olarak görülebilir. Bu nedenle, testler ve model proje boyunca arasındaki ilişkiyi korumak önemlidir.  
  
##  <a name="Attaching"></a>Model öğelere test çalışmaları ekleme  
 Projeniz kullanıyorsa [!INCLUDE[TCMlong](../modeling/includes/tcmlong_md.md)], testleri modelinizdeki öğelere bağlayabilirsiniz. Bu, hızlı bir şekilde bir gereksinimlerdeki etkilenen testleri bulma sağlar ve bir gereksinim gerçekleşti ölçüde izlemenize yardımcı olur.  
  
 Öğesi her türlü testleri bağlayabilirsiniz. Bazı örnekler şunlardır:  
  
-   Kullanım örneği onu çalıştıran testlere bağlayın.  
  
-   Yan tümceleri bir kullanım örneği sonkoşulunun ya da hedef, kullanım örneğine bağlı yorumlar üzerine yazma ve her açıklamaya testleri bağlayın.  
  
-   Sınıf diyagramları veya etkinlik diyagramları açıklamaları değişmez kuralları yazma ve testlere bağlayın.  
  
-   Testleri etkinlik diyagramı veya ayrı etkinliklere bağlayın.  
  
-   Bir test paketine bileşeni ya da test ettiği alt bağlayın.  
  
#### <a name="to-link-tests-to-a-model-element-or-relationship"></a>Bir model öğesi veya ilişki testleri bağlamak için  
  
1.  İçinde [!INCLUDE[TCMlong](../modeling/includes/tcmlong_md.md)], bir gereksinim oluşturmanız ve test paketi ona dayandırın. 
  
     Oluşturduğunuz bir iş öğesinin gereksinimdir [!INCLUDE[vstsTfsShort](../modeling/includes/vststfsshort_md.md)]. Bir kullanıcı hikayesi, gereksinim veya kullanım örneği iş öğesi ile projenizin kullandığı işlem şablonu bağlı olarak olabilir [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]. Daha fazla bilgi için bkz: [Visual Studio Team Services veya Team Foundation Server kullanarak iş izleme](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503).  
  
2.  Gereksinim çalışma öğesini modelinizdeki bir veya daha fazla öğe bağlayın.  
  
     Modelleme diyagramında, bir öğe, açıklama veya ilişki sağ tıklayın ve ardından **iş öğesi bağlantı**.
  
3.  Model öğesinde ifade gereksinim doğrulayın test çalışmalarını test paketine ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulamanız için model oluşturma](../modeling/create-models-for-your-app.md)   
 [Kullanıcı gereksinimlerini modelleme](../modeling/model-user-requirements.md)   
 [Uygulama Mimarinizi modeli](../modeling/model-your-app-s-architecture.md)   
 [Çözümleme ve mimarinin modelini oluşturma](../modeling/analyze-and-model-your-architecture.md)
