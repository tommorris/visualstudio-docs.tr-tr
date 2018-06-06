---
title: Modelleri, Sınıfları ve İlişkileri Anlama
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, models
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 394b21d396bf92b794060ff27ed940e25a77aa26
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748494"
---
# <a name="understanding-models-classes-and-relationships"></a>Modelleri, Sınıfları ve İlişkileri Anlama
Bir etki alanına özgü dil (DSL) yazma herhangi bir özel program kodu ile birlikte kendi DSL tanım dosyası tarafından tanımlanır. DSL çözüm program kodunda çoğu bu dosyadan oluşturulur.

 Bu konu DSL tanımı merkezi özelliklerini açıklar.

## <a name="the-dsl-definition"></a>DSL tanımı
 Açtığınızda `Dsl\DslDefinition.dsl`, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] penceresinde, aşağıdaki resimde benzer.

 ![DSL Tasarımcısı](../modeling/media/dsl_designer.png)

 En önemli bilgiler DSL tanımında DSL tanımı diyagramda görüntülenir. Ayrıca DslDefinition.dsl bir parçası olan ek bilgileri genellikle diyagram tarafında görünür DSL Gezgini'nde görüntülenir. En sık kullanılan görevler için diyagram ile daha gelişmiş özelleştirmeler DSL Gezgini ile çalışırsınız.

 DSL tanımı diyagramı model öğelerini ve model öğeleri arasında bağlantılar tanımlamak ilişkileri tanımlayın etki alanı sınıflarını gösterir. Ayrıca, kullanıcıya model öğelerini görüntülemek için kullanılan bağlayıcılar ve şekilleri gösterir.

 ![kulvarlı DSL Tasarımcısı](../modeling/media/dsl_desinger.png)

 DSL tanımında, diyagram veya DSL Gezgini'nde, bir öğe seçtiğinizde, ilgili bilgileri Özellikler penceresinde görüntülenir. Ek bilgi DSL Ayrıntıları penceresinde görüntülenebilir.

### <a name="models-are-instances-of-dsls"></a>Modelleri DSL'ler örnekleridir
 A *modeli* bir kullanıcı tarafından oluşturulan, DSL örneğidir. Bir modeli tanımladığınız etki alanı sınıfları ve tanımladığınız etki alanı ilişkilerini örnekleri olan öğeler arasında bağlantılar örnekleridir model öğelerini içerir. Bir model, Şekil ve diyagramda görünen model öğelerini ve bağlantıları bağlayıcıları da sahip olabilirsiniz. DSL tanımı şekil sınıfları, bağlayıcı sınıfları ve diyagramı için bir sınıf içerir.

 DSL tanım olarak da bilinir bir *etki alanı modeli*. Model etki alanına özgü dil çalışma zamanı örneklemesi iken DSL tanımı veya etki alanı modeli etki alanına özgü dil tasarım zamanı gösterimidir.

## <a name="domain-classes-define-model-elements"></a>Model öğelerini etki alanı sınıflarını tanımla
 Etki alanında çeşitli öğeleri oluşturmak için kullanılan etki alanı sınıflar ve etki alanı ilişkilerini olan öğeler arasında bağlantılardır. Öğeleri ve bunların modelleri oluşturduğunuzda tasarım özgü dil kullanıcılar tarafından örneğinin oluşturulması bağlantıları tasarım zamanı gösterimi oldukları.

 Bu örnekte, Müzik Kitaplığı DSL kullanıcı tarafından oluşturulmuş bir model gösterilmiştir. Müzik albümlerini şarkıya listesini içeren kutuları ile temsil edilir. Sanatçılar yuvarlatılmış kutuları ile temsil edilir ve katkısı albümleri bağlanır.

 ![Oluşturulan DSL örnek modeli](../modeling/media/music_instance.png)

 DSL tanımı iki yön ayırır. Model diyagramı modeli öğeleri görünümünü şekil sınıfları ve bağlayıcı sınıfları kullanılarak tanımlanır. Model içinde taşınan bilgiler, etki alanı sınıfları ve etki alanı ilişkilerini kullanılarak tanımlanır.

 Aşağıdaki çizimde, Müzik Kitaplığı DSL tanımı'nda etki alanı sınıfları ve ilişkileri gösterir.

 ![Katıştırma ve başvuru ilişkileri](../modeling/media/music_classes.png)

 Çizimde dört etki alanı sınıflarını gösterir: müzik, albüm, sanatçı ve şarkı. Etki alanı sınıflarını adı, başlık ve benzerleri gibi etki alanı özellikleri tanımlayın. Örnek modelinde, bu özelliklerden bazıları değerlerini diyagramı görüntülenir.

 Etki alanı ilişkilerini arasında sınıfları şunlardır: MusicHasAlbums, MusicHasArtists, AlbumbHasSongs ve ArtistAppearedOnAlbums. 1..1 gibi Çeşitlilikler ilişkilerine sahip 0.. *. Örneğin, her bir şarkıyı AlbumHasSongs ilişkisi aracılığıyla tam olarak bir albüm ilişkili olmalıdır. Albümlerini şarkıya herhangi bir sayıda olabilir.

### <a name="rearranging-the-dsl-definition-diagram"></a>DSL tanımı diyagramı yeniden düzenleme
 Bu resmi albüm yaptığı gibi bir etki alanı sınıf DSL tanımı diyagramda birkaç kez görünebilir dikkat edin. Her zaman bir ana görünüm yok ve olabilir bazı *başvuru* görünümleri.

 DSL tanımı diyagramı yeniden düzenlemek için şunları yapabilirsiniz:

-   Ana değiştirme ve başvuru görünümleri kullanarak **getirin ağacı burada** ve **bölünmüş ağaç** komutları. Bu komutları görmek için bir tek etki alanı sınıfı sağ tıklatın.

-   Etki alanı sınıfları ve şekil sınıfları Ctrl + Yukarı Ok ve Ctrl + aşağı ok tuşlarına basarak yeniden sıralar.

-   Daraltma veya her şekli üst-sağ taraftaki simgesini kullanarak sınıfları genişletebilirsiniz.

-   Bir etki alanı sınıfının altındaki eksi işareti (-) tıklayarak ağaçtaki bölümlerini daraltın.

## <a name="inheritance"></a>Devralma
 Etki alanı sınıflar, devralma kullanılarak tanımlanabilir. Devralma türetme oluşturmak için devralma Aracı'nı tıklatın ve türetilen sınıfın temel sınıf'ye tıklayın. Bir model öğesi temel sınıfından devralınan tüm özellikleri ile birlikte kendi etki alanı sınıfı üzerinde tanımlanan tüm özelliklerine sahiptir. Ayrıca, ilişkilerinde rolleri devralır.

 Devralma ilişkisi, şekilleri ve bağlayıcıları arasında kullanılabilir. Devralma aynı Grup içerisinde tutmanız gerekir. Bir şekli bir etki alanı sınıfından olamaz.

## <a name="domain-relationships"></a>Etki alanı ilişkileri
 Model öğelerini ilişkileriyle bağlanabilir. Bağlantılar her zaman ikili; Bunlar tam olarak iki öğe bağlayın. Ancak, herhangi bir öğe diğer nesnelere çok sayıda bağlantı içerebilir ve ayrıca aynı çiftlerini arasında birden fazla bağlantı bile olabilir.

 Farklı öğe sınıfı tanımlayabilirsiniz gibi bağlantılar farklı sınıflardaki tanımlayabilirsiniz. Bir bağlantı sınıfının adlı bir *etki alanı ilişkisinin*. Bir etki alanı ilişkisinin öğesinin sınıfları örneklerini belirtir. Her bir ilişki sonu adlı bir *rol*, ve etki alanı ilişkisinin ilişki yanı sıra, iki rolleri için adlarını tanımlar.

 Etki alanı ilişkilerini iki tür vardır: ilişkiler ve başvuru ilişkileri katıştırma. DSL tanımı diyagramında katıştırma ilişkileri Kesiksiz çizgi her rolde olan ve başvuru ilişkileri satırları kesik.

### <a name="embedding-relationships"></a>İlişkileri katıştırma
 Kendi kök dışında bir modeldeki her öğe bir katıştırma bağlantı hedefidir. Bu nedenle, tüm modeli bağlantıları katıştırma tek bir ağaç oluşturur. Kapsama veya sahipliği katıştırma bir ilişkiyi temsil eder. Bu yolla ilgili iki model olarak da bilinen üst ve alt öğeleridir. Alt üst katıştırılmış kabul edilir.

 Katıştırma bağlantılar genellikle açıkça diyagramında bağlayıcılar olarak gösterilmez. Bunun yerine, bunlar genellikle kapsama ile temsil edilir. Modelin kökü diyagram tarafından temsil edilen ve katıştırılmış öğeleri şekiller diyagramdan olarak görüntülenir.

 Örnekte, kök sınıfı müzik katıştırma bir ilişkisi şarkı için katıştırma bir AlbumHasSongs sahip albüm MusicHasAlbums yok. Şarkıya her albüm içinde bir listedeki öğeleri olarak görüntülenir. Müzik örnekleri da diyagramda şekiller olarak görünür sanatçı sınıfına katıştırma bir MusicHasArtists de vardır.

 Varsayılan olarak, üst silindiğinde katıştırılmış öğelerini otomatik olarak silinir.

 Bir model kaydedildiğinde serileştirme özelleştirmediyseniz XML biçiminde dosyasına katıştırılmış öğeleri kendi üst içinde yuvalanmış.

> [!NOTE]
>  Katıştırma devralma ile aynı değil. Alt katıştırma ilişkisinde üst öğenin özelliklerini devralmaz. Bir katıştırma model öğeleri arasında bağlantı türüdür. Devralma sınıflar arasında bir ilişki olduğunu ve model öğeleri arasında bağlantılar oluşturmaz.

### <a name="embedding-rules"></a>Kuralları katıştırma
 Her öğe bir örnek modelinde modelin kökü dışında tam olarak bir katıştırma bağlantı hedefi olmalıdır.

 Bu nedenle, kök sınıfı dışında her Özet olmayan etki alanı sınıf en az bir katıştırma ilişki hedefi olmalıdır ya da bir taban sınıftan katıştırma devralmalıdır. Bir sınıf iki veya daha fazla katıştırılmış hedef olabilir, ancak örnek modeli öğeleri aynı anda yalnızca bir üst olabilir. Hedefin Çokluk kaynağına 0.. 1 çokluğa veya 1..1 olması gerekir.

### <a name="the-explorer-displays-the-embedding-tree"></a>Explorer katıştırma ağacı görüntüler
 DSL tanımınızı kendi model diyagramı yanı sıra kullanıcıların gördüğü bir explorer da oluşturur.

 ![Oluşturulan explorer'ın DSL](../modeling/media/music_explorer.png)

 Gezgini tüm öğeleri modeldeki olanlar şekilleri tanımlamadığınız gösterir. Öğeleri ve katıştırma ilişkileri gösterir ancak ilişkileri başvuru değil.

 Etki alanı özellikleri, bir öğenin değerleri görmek için kullanıcı bir öğeyi model diyagramı veya model Gezgini seçer ve Özellikler penceresi açılır. Bu diyagramda görüntülenmeyen dahil olmak üzere tüm etki alanı özelliklerini görüntüler. Örnekte, her eserin başlık ve bir tarzını olsa da, yalnızca başlık değeri diyagramda gösterilmiştir.

## <a name="reference-relationships"></a>Başvuru ilişkileri
 Başvuru ilişkisi herhangi bir tür değil katıştırma ilişkiyi temsil eder.

 Başvuru ilişkileri şekiller arasında bağlayıcılar olarak diyagramda genellikle görüntülenir.

 Model XML gösterimini kullanarak bir referans bağlantı iki öğeler arasında temsil *adlar.* Diğer bir deyişle, adlar her öğe modelinde benzersiz şekilde tanımlayan adlardır. Her bir model öğesi için XML düğümü ilişkinin adını ve başka öğesinin ad belirten bir düğüm içeriyor.

## <a name="roles"></a>Roller
 Her etki alanı ilişkisinin iki roller, bir kaynak rolü ve bir hedef rolü vardır.

 Aşağıdaki resimde, arasındaki hat **yayımcı** etki alanı sınıfı ve **PublisherCatalog** etki alanı ilişkisinin kaynak rolüdür. Etki alanı ilişkisinin arasında çizgi ve **albüm** etki alanı sınıftır hedefi rolü.

 ![Roller ve özellikler.](../modeling/media/propertycode.png)

 Model geçeceğini program kodu yazarken bir ilişki ile ilişkilendirilen adlar özellikle önemlidir. Örneğin, DSL çözümü yapılandırdığınızda, oluşturulan sınıf yayımcı albümleri koleksiyonudur katalog bir özelliğe sahiptir. Albüm sınıfı yayımcı sınıfının tek bir örneği olan yayımcı bir özelliğe sahiptir.

 DSL tanımında bir ilişki oluşturduğunuzda, özellik ve ilişki adları varsayılan değerleri verilir. Ancak, bunları değiştirebilirsiniz.

## <a name="multiplicities"></a>Çeşitlilikler
 Kaç tane öğeleri aynı rolü bir etki alanı ilişkisine sahip olabilir Çeşitlilikler belirtin. Örnekte, sıfır çok (0..\*) Çokluk ayarda **katalog** rolü belirtir herhangi bir örneğine **yayımcı** etki alanı sınıfı kadar olabilir  **PublisherCatalog** ilişki onu vermek istediğiniz gibi bağlar.

 Diyagramda yazarak veya değiştirerek bir role çokluğu yapılandırmak `Multiplicity` özelliğinde **özellikleri** penceresi. Aşağıdaki tabloda bu özellik için ayarları açıklanır.

|Çokluk türü|Açıklama|
|-----------------------|-----------------|
|0.. * (sıfır-çok)|Her etki alanı sınıfının örneğini, ilişki birden çok örneğini veya hiçbir ilişki örneği olabilir.|
|0.. 1 çokluğa (sıfır bir)|Her etki alanı sınıfının örneğini, ilişki birden fazla örneğini veya hiçbir ilişki örneği olabilir.|
|1..1 (bir tane)|Her etki alanı sınıfının örneğini, ilişkinin bir örneği olabilir. Herhangi bir rol sınıfı örneğinden Bu ilişkinin birden fazla örneği oluşturulamıyor. Doğrulama etkinse, rol sınıfın örneklerini ilişki örneği olduğunda doğrulama hatası görüntülenir.|
|1.. * (bir-çok)|Bu çoğulluğu rolündeki sınıfın her örneği ilişki birden çok örneği olabilir ve her örneği ilişkinin en az bir örnek olması gerekir. Doğrulama etkinse, rol sınıfın örneklerini ilişki örneği olduğunda doğrulama hatası görüntülenir.|

## <a name="domain-relationships-as-classes"></a>Etki alanı ilişkilerini sınıflar olarak
 Bir bağlantı depo model öğesi türetilmiş bir sınıf LinkElement örneği olarak temsil edilir. Bu özellikler etki alanı ilişkilerini etki alanı modeli diyagramı tanımlayabilirsiniz.

 Bir ilişki de, kaynak veya hedef diğer ilişkilerin da yapabilirsiniz. Etki alanı model diyagramı, etki alanı ilişkisinin sağ tıklayın ve ardından **Show Class**. Bir ek sınıfı kutusu görüntülenir. Ardından ona ilişkileri bağlanabilir.

 Etki alanı sınıflarıyla gibi bir ilişki kısmen devralmaya göre tanımlayabilirsiniz. Türetilen ilişki seçin ve ayarlayın **taban ilişki** Özellikleri penceresinde.

 Türetilmiş bir ilişki taban ilişki uzmanlaşmış. Bağlantılar türetilmiş, BT veya temel ilişkiyle bağlantılı sınıflar ile aynı etki alanı sınıfları. Bir modeldeki türetilmiş ilişkisinin bir bağlantı oluşturulduğunda, türetilmiş ve temel ilişkileri örneği olan. Program kodunda temel veya türetilmiş bir sınıf tarafından oluşturulan özelliklerini kullanarak bağlantı ters sonuna gidebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
