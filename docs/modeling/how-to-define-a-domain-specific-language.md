---
title: 'Nasıl yapılır: Etki Alanına Özgü bir Dili Tanımlama'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.domainrelationship
- vs.dsltools.dsldesigner.domainclass
- vs.dsltools.dsldesigner.domaintype
helpviewer_keywords:
- Domain-Specific Language, domain class
- Domain-Specific Language, external types
- Domain-Specific Language, relationships
- Domain-Specific Language, domain properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4aea2750e3900beb0aaa62156c215376ff16d1ea
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-a-domain-specific-language"></a>Nasıl yapılır: Etki Alanına Özgü bir Dili Tanımlama
Bir etki alanına özgü dil (DSL) tanımlamak üzere bir şablondan bir Visual Studio çözümü oluşturun. Çözüm önemli bir parçası DslDefinition.dsl depolanan DSL tanımı diyagramıdır. DSL tanımı DSL şekilleri ve sınıfları tanımlar. Sonra değiştirmek ve bu öğeleri ekleme, daha ayrıntılı DSL özelleştirmek için program kodunu ekleyebilirsiniz.

İçin DSL'ler yeniyseniz, aracılığıyla çalışmanızı öneririz **DSL araçları Laboratuvar**, bu sitede bulabilirsiniz: [Visualizaton ve SDK Modelleme](http://go.microsoft.com/fwlink/?LinkID=186128)

##  <a name="templates"></a> Bir şablon çözümü seçme
 DSL tanımlamak için aşağıdaki bileşenler yüklü olmalıdır:

|||
|-|-|
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio Görselleştirme ve modelleme SDK||


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]


 Yeni bir etki alanına özgü dil oluşturmak için etki alanına özgü dil proje şablonunu kullanarak yeni bir Visual Studio çözümü oluşturun.

#### <a name="to-create-a-dsl-solution"></a>Bir DSL çözüm oluşturmak için

1.  Bir çözüm oluşturmak **etki alanına özgü dil** altında bulunan şablon **diğer proje türleri/genişletilebilirlik** içinde **yeni proje** iletişim kutusu.

     ![Oluştur iletişim kutusu DSL](../modeling/media/create_dsldialog.png "Create_DSLDialog")

     Tıkladığınızda **Tamam**, **etki alanına özgü dil Sihirbazı** açar ve şablon DSL çözümlerinin listesini görüntüler.

2.  Her bir şablon açıklamasını görmek için tıklatın. Oluşturmak istediğiniz en çok benzeyen çözümü seçin.

     Her DSL şablonu temel çalışma DSL tanımlar. Bu DSL kendi gereksinimlerinizi karşılayacak şekilde düzenleyeceksiniz.

     Her örnek daha fazla bilgi için tıklatın.

    -   Seçin **Görev akışı** kulvarları sahip DSL oluşturmak için. Kulvarları diyagramın dikey veya yatay bölümlerdir.

    -   Seçin **bileşen modelleri** bağlantı noktası içeren bir DSL oluşturmak için. Daha büyük bir şekli kenarında küçük şekiller bağlantı noktalarıdır.

    -   Seçin **sınıf diyagramları** bölme şekiller sahip DSL tanımlamak için. Bölme şekiller öğeleri listesini içerir.

    -   Seçin **en az bir dil** diğer durumlarda veya belirsiz.

    -   Seçin **en az WinForm Tasarımcısı** veya **en az WPF Tasarımcısı** bir Windows Forms veya WPF yüzeyine görüntülenen DSL oluşturmak için. Düzenleyici tanımlamak için kod yazmanız gerekir. Daha fazla bilgi için aşağıdaki konulara bakın:

         [Windows Forms Tabanlı Etki Alanına Özgü Dil Oluşturma](../modeling/creating-a-windows-forms-based-domain-specific-language.md)

         [WPF Tabanlı Etki Alanına Özgü Dil Oluşturma](../modeling/creating-a-wpf-based-domain-specific-language.md)

3.  Bir dosya adı uzantısı, DSL uygun Sihirbazı sayfasında girin. Bu, DSL örneklerini içeren dosyaları kullanacağı uzantısıdır.

    -   Herhangi bir uygulama, bilgisayarınızın veya DSL yüklemek istediğiniz herhangi bir bilgisayar ile ilişkilendirilmemiş bir dosya adı uzantısı seçin. Örneğin, **docx** ve **htm** kabul edilebilir dosya adı uzantılarını olacaktır.

    -   Girdiğiniz uzantısı DSL kullanılmakta olup olmadığını, sihirbaz sizi uyarır. Farklı bir dosya adı uzantısı kullanmayı düşünün. Eski Deneysel tasarımcıları temizlemek için Visual Studio SDK deneysel örneği sıfırlayabilir. Tıklatın **Başlat**, tıklatın **tüm programlar**, **Microsoft Visual Studio 2010 SDK**, **Araçları**ve ardından **Microsoft Sıfırla Visual Studio 2010 Experimental örneği**.

4.  Sihirbazın diğer sayfalarını ayarları veya varsayılan değerleri bırakın.

5.  **Son**'a tıklayın.

     Sihirbaz, iki veya üç projeleri içeren ve kod DSL tanımından oluşturur bir çözüm oluşturur.

 Kullanıcı arabirimi şimdi aşağıdaki resimde benzer.

 ![DSL Tasarımcısı](../modeling/media/dsl_designer.png "dsl_designer")

 Bu çözüm, etki alanı belirli bir dil tanımlar. Daha fazla bilgi için bkz: [etki alanına özgü dil araçları kullanıcı arabirimi genel bakış](../modeling/overview-of-the-domain-specific-language-tools-user-interface.md).

### <a name="test-the-solution"></a>Çözüm test
 Şablon çözüm çalışma değiştirin veya olduğu gibi kullanın, DSL sağlar.

 Çözümü test etmek için F5'e veya CTRL + F5 tuşuna basın. Visual Studio yeni bir örneğini Deneysel modunda açılır.

 Çözüm Gezgini'nde, Visual Studio yeni bir örneğini örnek dosyasını açın. Bir araç kutusu ile bir diyagramı olarak açılır.

 Bir çözüm çalıştırırsanız, gelen oluşturduğunuz **en az bir dil** şablonu, Deneysel, Visual Studio, aşağıdaki örnekte benzer:

 ![](../modeling/media/dsl_min.png "DSL_min")

 Araçları ile deneyin. Öğeleri oluşturmak ve bunları bağlayın.

 Visual Studio Deneysel örneklerini kapatın.

> [!NOTE]
>  DSL değiştirildiğinde, artık test dosyası şekiller örneği görmeye olacaktır. Ancak, yeni öğeleri oluşturmak mümkün olacaktır.

### <a name="modifying-the-template-dsl"></a>Şablon DSL değiştirme
 Yeniden adlandırın ve bazı veya tüm etki alanı sınıfları ve şekil sınıfları DSL tanımı şablonunda tutun. Yeni sınıf adları geçerli CLR adları, boşluk veya noktalama işareti olmadan olmalıdır.

 Bu sınıfların tutmak kullanışlıdır:

-   Kök sınıf üst sol altında DSL tanımı diyagramı altında görünür **sınıflar ve ilişkiler**. DSL farklı bir adla yeniden adlandırın. Örneğin, adlandırılmış bir DSL **MusicLibrary** adlı bir kök sınıfı olabilir **müzik**.

-   Diyagram sınıfı DSL tanımı diyagramı alt sağ taraftaki görünür **diyagramı öğeleri** sütun. Sağa görmek için kaydırmanız gerekebilir. Genellikle adlı * YourDsl ***diyagramı**.

-   Kullandıysanız **Görev akışı** şablonu ve istediğinizde diyagramları ile kulvarları oluşturun, tutun ve aktör etki alanı sınıfı ve ActorSwimlane şekli yeniden adlandırın.

 Silin veya başka sınıfların gereksinimlerinize uyacak şekilde yeniden adlandırın.

##  <a name="patterns"></a> DSL tanımlamak için desenleri
 Ekleyerek veya aynı anda bir veya iki özellikleri ayarlama DSL geliştirmek öneririz. Özellik ekleme, DSL çalıştırın ve test ve bir veya iki daha fazla özellikleri ekleyin. Tipik bir özellik olan, DSL olabilir:

-   Bir etki alanı sınıf diyagramı ve kullanıcıların olanak sağlayan öğe aracı o sınıfın öğeleri görüntülemek için gerekli olan şekil model öğesi bağlandığı katıştırma ilişki öğeleri oluşturun.

-   Bir etki alanı sınıfının ve şekli görüntülemek dekoratörler etki alanı özellikleri.

-   Başvuru ilişkisi ve bu diyagramda ve kullanıcıların sağlayan bağlayıcı aracını görüntüler Bağlayıcısı bağlantılar oluşturabilirsiniz.

-   Doğrulama kısıtlaması veya menü komutu gibi program kodu gerektirir özelleştirme.

 Aşağıdaki bölümlerde DSL özellikleri en yararlı tür oluşturma açıklanmaktadır. İle DSL oluşturulabilir birçok desenleri vardır, ancak bunlar en sık kullanılır.

> [!NOTE]
>  Bir özellik eklendikten sonra tıklamayı değil **tüm şablonları dönüştürme** Çözüm Gezgini araç çubuğunda, önce yapı ve, DSL çalışıyor.

 Bu konudaki örnek olarak kullanılan DSL sınıflar ve ilişkiler parçası aşağıdaki şekilde gösterilmiştir.

 ![Katıştırma ve başvuru ilişkileri](../modeling/media/music_classes.png "Music_Classes")

 Sonraki şekilde, bu DSL örnek modelinin gösterilmiştir:

 ![Oluşturulan DSL örneği modelinin](../modeling/media/music_instance.png "Music_Instance")

> [!NOTE]
>  "Model" kullanıcıların oluşturmak ve genellikle bir diyagram görüntülenir, DSL örneği ifade eder. Bu konuda, hem DSL tanımı diyagramı hem de, DSL kullanıldığında görüntülenen modeli diyagramları anlatılmaktadır.

##  <a name="classes"></a> Etki alanı sınıfları tanımlama
 Etki alanı sınıfları, DSL kavramlarını temsil eder. Örnekleri olan *model öğelerini*. Örneğin bir **MusicLibrary** DSL etki alanı adında sınıflarını olabilir **albüm** ve **şarkı**.

 Bir etki alanı sınıfı oluşturmak için gelen sürükleyebilirsiniz **adlı etki alanı sınıf** aracı diyagrama ve sınıf olarak yeniden adlandırın.

 Daha fazla bilgi için bkz: [etki alanı özellikleri sınıflarını](../modeling/properties-of-domain-classes.md).

### <a name="create-an-embedding-relationship-for-each-domain-class"></a>Her bir etki alanı sınıf için bir katıştırma ilişkisi oluşturun
 Kök sınıf dışında her etki alanı sınıf en az bir katıştırma ilişkisinin hedefi olması gerekir veya hedefi katıştırma bir ilişkisi olan bir sınıftan devralın gerekir.

 Bir modeldeki her model öğesi ilişkileri katıştırma tek ağacındaki bir düğümdür. Kaynak ve hedef bir katıştırma ilişkisinin sık için üst ve alt adlandırılır.

 Bir etki alanı sınıf için bir üst seçimini diğer öğelerde bağımlı öğeleri yaşam süreleri nasıl istediğinizi bağlıdır. Bir ağaç düğümünün silinirse, kendi alt ağaç genellikle de silinir. Bağımsız bir varlığı olan öğe sınıfları, bu nedenle doğrudan kök sınıfı altında katıştırılır.

 Genellikle, başka bir öğe içinde bir öğe görüntülemek, sahibi ilişki göstermek istiyorsunuz. Bu durumda, en uygun üst sınıfı kapsayıcı sınıftır. İçinde bir kapsayıcı gördüğünüz öğesi gerçekte yalnızca bağımsız bir öğeye başvuru bağlantısı olduğunda istisnadır. Bu durumda, kapsayıcı silme başvuru ancak kendi hedef siler.

 Bu konuda açıklanan DSL tanımı düzenleri kapsayıcı silindiğinde, bir kapsayıcı görüntülenen öğeler silinecek varsayacağız. Daha karmaşık düzenleri olası ve kurallar tanımlayarak elde edilebilir.

|Öğe nasıl görüntülenir|(Katıştırma) üst sınıfı|Örnekte DSL çözüm şablonu|
|------------------------------|--------------------------------|--------------------------------------|
|Diyagramda şekil.<br /><br /> Kulvar.|DSL kök sınıfı.|En az dili.<br /><br /> Görev akışı: Aktör sınıfı.|
|İçinde kulvar şekli.|Etki alanı sınıf öğelerinin kulvarları görüntülenir.|Görev akışı: Görev sınıfı.|
|Listedeki öğe kapsayıcısı silinirse, burada silinir şeklinde öğesi.<br /><br /> Şekil kenarında bağlantı noktası.|Kapsayıcı şekle eşlenen etki alanı sınıf.|Sınıf diyagramı: öznitelik sınıfı.<br /><br /> Bileşen Diyagramı: bağlantı noktası sınıfı.|
|Öğe listesinde, kapsayıcı silinirse silinmez.|DSL kök sınıfı.<br /><br /> Referans bağlantıları görüntüler.||
|Doğrudan görüntülenir.|Bu bölümü forms sınıfı.||

 Müzik Kitaplığı örnekte albümleri şarkıya başlıklarını listelenen dikdörtgenler olarak görüntülenir. Bu nedenle albüm üst kök sınıfı müzik ve şarkı üst albüm şeklindedir.

 Bir etki alanı sınıf ve aynı anda katıştırma oluşturmak için tıklatın **katıştırma ilişki** aracı, sonra üst sınıfı'ı tıklatın ve diyagramı boş bir bölümüne tıklatın.

 Sınıf adları otomatik olarak izleyecek çünkü katıştırma ilişki ve kendi rolleri adını ayarlamak genellikle gerekli değildir.

 Daha fazla bilgi için bkz: [etki alanı ilişkilerini özellikleri](../modeling/properties-of-domain-relationships.md) ve [etki alanı özellikleri rolleri](../modeling/properties-of-domain-roles.md).

> [!NOTE]
>  Katıştırma devralma ile aynı değil. Katıştırma ilişkisinde alt öğeleri özelliklerini üst devralmaz.

### <a name="add-domain-properties-to-each-domain-class"></a>Etki alanı özellikleri her etki alanı sınıfına ekleyin
 Etki alanı özellikleri değerleri depolar. Örnekler: ad, başlık, yayın tarihi.

 Tıklatın **etki alanı özellikleri** sınıfında, ENTER tuşuna basın ve ardından bir özellik adını yazın. Varsayılan etki alanı özelliği dize türünde. Türünü değiştirmek istiyorsanız, etki alanı özelliğini seçin ve ayarlayın **türü** içinde **özellikleri** penceresi. İstediğiniz türü açılır listede yoksa bkz [özellik türleri ekleme](#addTypes).

 **Bir öğe adı özelliğini ayarlayın.** Dil Explorer'da öğeleri tanımlamak için kullanılan bir etki alanı özelliği seçin. Başlık etki alanı özelliği seçebilirsiniz Örneğin, şarkı etki alanı sınıfı. İçinde **özellikleri** penceresindeki ayarlayın **öğesi adını** için `true`.

### <a name="create-derived-domain-classes"></a>Türetilmiş etki alanı sınıfları oluşturma
 Bir etki alanı sınıf özelliklerini ve ilişkileri devral çeşitleri olmasını istiyorsanız, bu sınıftan türetilen sınıflar oluşturun. Örneğin, albüm WMA ve MP3 türetilmiş sınıfları.

 Türetilmiş sınıf kullanarak oluşturduğunuz **etki alanı sınıfı** aracı.

 Tıklatın **devralma** aracı, türetilmiş sınıf tıklayın ve temel sınıfı'ye tıklayın.

 Ayar göz önünde bulundurun **devralma değiştiricisi** için temel sınıfın **soyut**. Taban sınıf örneklerini gerekebilir düşünüyorsanız, bunun yerine ayrı bir oluşturma türetilmiş düşünün bunlar için sınıf.

 Türetilmiş sınıflar temel sınıflarına rolleri ve özellikleri devralır.

### <a name="tidy-the-dsl-definition-diagram"></a>DSL tanımı diyagramı tutuyor
 İlişkileri eklediğinizde, sınıflarınızı bazıları birden fazla yerde görünür. Görünümler sayısını azaltın ve daha geniş diyagramı yapmak için bir ilişki hedef sınıf sağ tıklayın ve ardından **getirin ağacı burada**. Ters efekt için hedef sınıfı bir ilişki ve tıklatın sağ tıklatın **bölünmüş ağaç**. Bu menü komutlarını görmüyorsanız, yalnızca etki alanı sınıfı seçili olduğundan emin olun.

 Etki alanı sınıfları ve şekil sınıfları taşımak için CTRL + YUKARI OK ve CTRL + AŞAĞI OK kullanın.

### <a name="test-the-domain-classes"></a>Test etki alanı sınıfları

##### <a name="to-test-the-new-domain-classes"></a>Yeni etki alanı sınıfları sınamak için

1.  **Tüm Şablonları dönüştürme tıklatın** araç çubuğundaki DSL Tasarımcı kodu oluşturmak için Çözüm Gezgini'nde,. Bu adım otomatik hale getirebilirsiniz. Daha fazla bilgi için bkz: [otomatikleştirmek tüm şablonları dönüştürme nasıl](http://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).

2.  **Derleme ve DSL çalıştırın.** Visual Studio yeni bir örneğini Deneysel modda çalıştırmak için F5'e veya CTRL + F5 tuşuna basın. Visual Studio'nun deneysel örneğinde, DSL dosya adı uzantısına sahip bir dosya oluşturun veya açın.

3.  **Explorer'ı açın.** AT diyagram tarafında bulunur genellikle adlı dil Gezgini penceresi *YourLanguage* Explorer. Bu pencereyi görmüyorsanız, Çözüm Gezgini altında bir sekmede olabilir. Üzerinde bulamazsa, **Görünüm** menüsündeki **diğer pencereler**ve ardından *YourLanguage* **Explorer**.

     Explorer modelinin ağaç görünümünü gösterir.

4.  **Yeni öğe oluşturun.** Üst kök düğüme sağ tıklayın ve ardından **yeni Ekle *** YourClass*.

     Sınıfının yeni bir örneği dilinizde Gezgini görüntülenir.

5.  Yeni örnekleri oluşturduğunuzda, her bir örneği farklı bir ad olduğundan emin olun. Yalnızca ayarladıysanız, bu meydana gelir **öğesi adını** bir etki alanı özelliği bayrağı.

6.  **Etki alanının özelliklerini inceleyin. Seçildiğinde, sınıfının bir örneği ile** Özellikler penceresini inceleyin. Bu etki alanı sınıfı üzerinde tanımlanan etki alanı özellikleri göstermesi gerekir.

7.  **Dosyayı kaydedin, kapatın ve yeniden açın**. Düğümleri genişlettikten sonra oluşturduğunuz tüm örneklerini explorer'ın görünmesi gerekir.

##  <a name="shapes"></a> Şekilleri diyagramı tanımlama
 Dikdörtgenler, üç nokta veya simgeler diyagramda görünen öğelerin sınıfları tanımlayabilirsiniz.

#### <a name="to-define-a-class-of-elements-that-appear-as-shapes-on-a-diagram"></a>Bir sınıf diyagramında şekiller olarak görüntülenen öğelerin tanımlamak için

1.  **Tanımlama ve açıklandığı gibi bir etki alanı sınıf test**[etki alanı sınıfları tanımlama](#classes) **.** 

    -   Üst sınıfın kök sınıf olmalıdır. Diğer bir deyişle, kök ve yeni etki alanı sınıf arasında katıştırma bir ilişki olmalıdır.

    -   Diyagram kulvarları varsa, üst bir kulvara eşlenen etki alanı sınıf olabilir. Bu yordama devam etmeden önce bkz [kulvarları sahip DSL tanımlama](#swimlanes).

2.  **Şekil sınıfı ekleme** model diyagramı öğeleri göstermek için. DSL tanımı diyagram üzerine aşağıdaki araçlardan birini sürükleyin:

    -   **Geometri şekli** dikdörtgen veya elips sağlar.

    -   **Görüntü şekli** sağlayan bir görüntüsünü görüntüler.

    -   **Şekil compartment** öğeleri bir veya daha fazla listesini içeren bir dikdörtgen.

     Şekiller ve bağlayıcılar altında DSL tanımı Diyagramı sağ tarafında görünür shape sınıfı yeniden adlandırın.

3.  **Bir resmi bir resim şekli oluşturduysanız tanımlamak**.

    1.  Herhangi bir boyuttaki bir yansıma dosyası oluşturun. BMP, JPEG, GIF ve EMF biçimleri desteklenir.

    2.  Çözüm Gezgini'nde, çözüm Dsl\Resources altında dosyası ekleyin.

    3.  DSL tanımı şemaya geri dönmek ve yeni görüntü shape sınıfı seçin.

    4.  Özellikler penceresinde **görüntü** özelliği.

    5.  İçinde **Görüntüsü Seç** iletişim kutusunda, altında açılan menüsünü **dosya adı**ve görüntüyü seçin.

4.  **Metin dekoratörler etki alanının özelliklerini görüntülemek için şekle ekleyin.**

     Adını veya model öğenin başlığını görüntülemek için büyük olasılıkla en az bir metin oluşturma öğesi gerekir.

     Shape sınıfının başlığına sağ tıklayın, fareyle **Ekle**ve ardından **metin oluşturma öğesi**. Oluşturma öğesi adını ve Özellikler penceresini kümedeki ayarlamak kendi **konumu**.

5.  **Her şekli görüntülemesi gereken etki alanı sınıf diyagramı öğesi haritaya bağlamak**.

     Tıklatın **diyagram öğesi harita** aracı, sonra etki alanı sınıfı tıklayın ve ardından shape sınıfı.

6.  **Metin dekoratörler harita özellikleri.**

    1.  Etki alanı ve diyagram öğesi harita temsil eden şekli sınıf arasında gri satırı seçin.

    2.  İçinde **DSL ayrıntıları** penceresinde tıklatın **oluşturma öğesi eşlemeleri** sekmesi. Görmüyorsanız, **DSL ayrıntıları** penceresi, **Görünüm** menüsündeki **diğer pencereler** ve ardından **DSL ayrıntıları**. Tüm içeriğini görmek için bu pencerenin üst kısmındaki yükseltmek sıklıkla gereklidir.

    3.  Bir oluşturma öğesi adını seçin. Altında **görüntüleme özelliği**, etki alanı sınıfının bir özellik adını seçin. Bu, her oluşturma öğesi için işlemi yineleyin.

         İlişkili bir öğesi özelliği görüntülemek istiyorsanız, altında aşağı açılan Ağaç Gezgini tıklatın **özelliği görüntülemek için yol**.

    4.  Her oluşturma öğesi adının bir onay işareti görünür olduğundan emin olun.

     ![Şekil eşlemeleri ve DSL ayrıntıları penceresini](../modeling/media/dsldetailswindow.png "DslDetailsWindow")

7.  **Etki alanı sınıfının öğeleri oluşturmak için bir araç kutusu öğesi olun.**

    1.  İçinde **DSL Explorer**, genişletin **Düzenleyicisi** düğümü ve tüm alt düğümleri.

    2.  Düğümü altında **araç kutusu sekmeleri** DSL, örneğin MusicLibrary aynı ada sahip. Tıklatın **öğesi aracı Ekle**.

        > [!NOTE]
        >  Sağ tıklattığınızda, **Araçları** düğümünü görmezsiniz **eklemek öğesi aracı**. Bunun yerine, yukarıdaki düğümünü tıklatın.

    3.  Özellikler penceresinde seçili yeni öğe aracıyla ayarlayın **sınıfı** kısa süre önce eklemiş olduğunuz etki alanı sınıfı.

    4.  Ayarlama **resim yazısı** ve **araç ipucu**.

    5.  Ayarlama **araç kutusu simgesi** araç kutusunda görünür bir simge. Yeni bir simge veya zaten başka bir aracı için kullanılan bir simge ayarlayabilirsiniz.

         Yeni bir simge oluşturmak için de Dsl\Resources açın **Çözüm Gezgini**. Kopyalayın ve var olan öğe araç BMP dosyaları birini yapıştırın. Yapıştırılan kopyayı yeniden adlandırın ve düzenlemek için çift tıklayın.

         Dönüş DSL tanımı diyagrama, Aracı'nı seçin ve Özellikler penceresinde tıklatın **[...]**  içinde **araç kutusu simgesi**. İçinde **seçin bit eşlem** iletişim kutusunda. Aşağı açılır menüden BMP dosyası.

 Daha fazla bilgi için bkz: [geometri şekiller özellikleri](../modeling/properties-of-geometry-shapes.md) ve [görüntü şekiller özellikleri](../modeling/properties-of-image-shapes.md).

#### <a name="to-test-shapes"></a>Şekilleri sınamak için

1.  **Tüm Şablonları dönüştürme tıklatın** araç çubuğundaki DSL Tasarımcı kodu oluşturmak için Çözüm Gezgini'nde,.

2.  **Derleme ve DSL çalıştırın.** Visual Studio yeni bir örneğini Deneysel modda çalıştırmak için F5'e veya CTRL + F5 tuşuna basın. Visual Studio'nun deneysel örneğinde, DSL dosya adı uzantısına sahip bir dosya oluşturun veya açın.

3.  **Öğe araçları araç kutusunu göründüğünü doğrulayın.**

4.  **Şekiller oluşturma** modeli diyagram üzerine bir aracından sürükleyerek.

5.  **Her metin oluşturma öğesi göründüğünü doğrulayın** ve:

    1.  Ayarlamış olduğunuz sürece, düzenleyebilirsiniz **UI salt okunur** etki alanı özelliği bayrağı.

    2.  Özellik Özellikleri penceresinde veya oluşturma öğesi düzenlediğinizde, diğer görünüm güncelleştirilir.

 Bir şekli ilk test ettikten sonra bazı özelliklerini ayarlamanıza ve daha gelişmiş özellikler eklemek isteyebilirsiniz. Daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

##  <a name="references"></a> Başvuru ilişkileri tanımlama
 Tüm kaynak etki alanı ve tüm hedef etki alanı sınıf arasında bir başvuru ilişkisi tanımlayabilirsiniz. Başvuru ilişkileri şekiller arasında satırlar bağlayıcılar olarak diyagramda genellikle görüntülenir.

 Örneğin, müzik albümlerini ve sanatçılar, Diyagram şekilleri olarak görüntülenmiyorsa, işe yaradığını albümleri Sanatçılar bağlantılar ArtistsAppearedOnAlbums adlı bir ilişki tanımlayabilirsiniz. Şekil örneğe bakın.

 ![Oluşturulan DSL örneği modelinin](../modeling/media/music_instance.png "Music_Instance")

 Başvuru ilişkileri Ayrıca aynı türdeki öğeleri bağlayabilirsiniz. Örneğin, Aile ağacı temsil eden bir DSL üst ve alt öğeleri arasındaki ilişki bir başvuru kişi başka bir kişi ilişkidir.

### <a name="define-a-reference-relationship"></a>Başvuru ilişkisi tanımlayın
 Başvuru ilişkisi Aracı'nı tıklatın sonra kaynak etki alanı sınıf ilişkisinin tıklayın ve sonra hedef etki alanı sınıf'ı tıklatın. Hedef sınıf kaynak sınıf ile aynı olabilir.

 İki rolleri, ilişki kutusunun her tarafında satırında tarafından temsil edilen her bir ilişkisi yok. Her bir rol seçin ve Özellikler penceresinde özelliklerini ayarlayın.

 **Rolleri yeniden adlandırma göz önünde bulundurun**. Örneğin, kişi ve kişi arasında bir ilişki üst ve alt öğeleri, Yöneticisi ve ast, Öğretmen ve Öğrenci için varsayılan adlarını değiştirmek ve benzeri isteyebilirsiniz.

 **Her rol çeşitliliği ayarlamak**, gerekli değilse. En çok bir yöneticiye sahip herkes istiyorsanız 0.. 1 diyagramda Yöneticisi etiketin altında görünür Çokluk ayarlayın.

 **Etki alanı özellikleri ilişki ekleyin.** Şekilde, Sanatçı Albüm ilişki rolünün bir özelliğe sahiptir.

 **İlişkinin verir yineleme özelliğini ayarlayın** aynı sınıfın birden fazla bağlantı modeli öğeleri aynı çifti arasında varsa. Örneğin, birden fazla aynı Öğrenci tabi öğretmeyi Öğretmen izin verebilir.

 ![Şekil eşlemeleri bağlayıcıların](../modeling/media/music_connector.png "Music_Connector")

 Daha fazla bilgi için bkz: [etki alanı ilişkilerini özellikleri](../modeling/properties-of-domain-relationships.md) ve [etki alanı özellikleri rolleri](../modeling/properties-of-domain-roles.md).

### <a name="define-a-connector-to-display-the-relationship"></a>İlişki görüntülemek için bir bağlayıcı tanımlayın
 Bir bağlayıcı modeli diyagramda iki şekiller arasında bir çizgi görüntüler.

 Sürükleme **bağlayıcı** DSL tanımı diyagram üzerine aracı.

 Bağlayıcı etiketleri görüntülemek istiyorsanız, metin dekoratörler ekleyin. Konumlarına ayarlayın. Metin oluşturma öğesi taşıma kullanıcı izin vermek için ayarlanmış kendi **olan taşınabilir** özelliği.

 Kullanım **diyagram öğesi harita** başvuru ilişkisi bağlayıcı bağlamak için aracı.

 Seçili diyagram öğesi eşlemesi ile açmak **DSL ayrıntıları** penceresi ve açık **oluşturma öğesi eşlemeleri** sekmesi.

 Her seçin **oluşturma öğesi** ve **görüntüleme özelliği** doğru etki alanı özelliği.

 Bir onay işareti her öğesinin yanındaki göründüğünden emin olun **dekoratörler** listesi.

### <a name="define-a-connection-builder-tool"></a>Bir bağlantı Oluşturucu aracı tanımlayın
 İçinde **DSL Explorer** penceresinde genişletin **Düzenleyicisi** düğümü ve tüm alt düğümlerini.

 DSL aynı ada sahip düğümünü sağ tıklatın ve ardından **ekleme yeni bağlantı aracını**.

 Yeni aracı seçiliyken Özellikler penceresinde:

-   Ayarlama **resim yazısı** ve **araç ipucu**.

-   Tıklatın **bağlantı Oluşturucu** ve yeni ilişki için uygun Oluşturucusu'nu seçin.

-   Ayarlama **araç kutusu simgesi** araç kutusunda görünmesini istediğiniz simge. Yeni bir simge veya zaten başka bir aracı için kullanılan bir simge ayarlayabilirsiniz.

     Yeni bir simge oluşturmak için de Dsl\Resources açın **Çözüm Gezgini**. Kopyalayın ve var olan öğe araç BMP dosyaları birini yapıştırın. Yapıştırılan kopyayı yeniden adlandırın ve düzenlemek için çift tıklayın.

     Dönüş DSL tanımı diyagrama, Aracı'nı seçin ve Özellikler penceresinde tıklatın **[...]**  içinde **araç kutusu simgesi**. İçinde **seçin bit eşlem** iletişim kutusunda. Aşağı açılır menüden BMP dosyası.

##### <a name="to-test-a-reference-relationship-and-connector"></a>Başvuru ilişkisi ve bağlayıcı test etmek için

1.  **Tüm Şablonları dönüştürme tıklatın** araç çubuğundaki DSL Tasarımcı kodu oluşturmak için Çözüm Gezgini'nde,.

2.  **Derleme ve DSL çalıştırın.** Visual Studio yeni bir örneğini Deneysel modda çalıştırmak için F5'e veya CTRL + F5 tuşuna basın. Visual Studio'nun deneysel örneğinde, DSL dosya adı uzantısına sahip bir dosya oluşturun veya açın.

3.  **Bağlantı aracını araç kutusunda görüntülendiğini doğrulayın.**

4.  **Şekiller oluşturma** modeli diyagram üzerine bir aracından sürükleyerek.

5.  **Bağlantıları oluşturma** şekiller arasında. Bağlayıcı Aracı'nı tıklatın, bir şekli tıklatın ve başka bir Şekil'ye tıklayın.

6.  **Uygunsuz sınıflar arasındaki bağlantıları oluşturulamıyor doğrulayın.** Örneğin, ilişkiniz Albümler ve Sanatçılar arasındaysa için Sanatçılar Sanatçılar bağlayamazsınız doğrulayın.

7.  **Çeşitliliği doğru olduğundan emin olun. Örneğin, bir kişi birden fazla Manager'a bağlanamıyor doğrulayın.**

8.  **Her metin oluşturma öğesi göründüğünü doğrulayın** ve:

    1.  Ayarlamış olduğunuz sürece, düzenleyebilirsiniz **UI salt okunur** etki alanı özelliği bayrağı.

    2.  Özellik Özellikleri penceresinde veya oluşturma öğesi düzenlediğinizde, diğer görünüm güncelleştirilir.

 Bir bağlayıcı ilk test ettikten sonra bazı özelliklerini ayarlamanıza ve daha gelişmiş özellikler eklemek isteyebilirsiniz. Daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

##  <a name="compartments"></a> Listeleri içeren şekilleri tanımlama: Compartment şekiller
 Bir bölme şekil öğeleri bir veya daha fazla listesini içerir. Örneğin, Müzik Kitaplığı DSL müzik albümleri temsil etmek için bölme şekiller kullanabilirsiniz. Her albümü, şarkıya listesini yoktur.

 ![Şekil compartment](../modeling/media/compartmentshape.png "CompartmentShape")

 En basit yöntemi, bu etkiyi DSL tanımında elde kapsayıcı için bir etki alanı sınıf ve her bir listesi için bir etki alanı sınıfı tanımlar. Kapsayıcı sınıfı bölme şekle eşlenir.

 ![Şekil harita](../modeling/media/music_mapcomp.png "Music_MapComp")

 Daha fazla bilgi için bkz: [bölme şekiller özellikleri](../modeling/properties-of-compartment-shapes.md).

#### <a name="to-define-a-compartment-shape"></a>Bir bölme şekil tanımlamak için

1.  **Kapsayıcı etki alanı sınıfı oluşturmak**. Tıklatın **katıştırma ilişki** aracı, model kök sınıfının tıklayın ve DSL tanımı diyagramı boş bir parçası'ye tıklayın. Bu örnek şekilde albüm adlı etki alanı sınıfı oluşturur.

     Alternatif olarak kök sınıfında katıştırma yerine bir kulvara eşlenen bir etki alanı sınıf kapsayıcı eklenebilir.

     Bir etki alanı özellik adı gibi sınıfına ekleyin ve ayarlayın, **öğesi adını** Özellikleri penceresinde bayrağı.

2.  **Liste öğesi etki alanı sınıfı oluşturmak**. Tıklatın **katıştırma ilişki** aracı, kapsayıcı sınıfı (albüm) ve ardından diyagramı boş bir kısmına tıklayın. Bu örnek şekilde şarkı adlı etki alanı sınıfı oluşturur.

     Başlık sınıfına gibi bir etki alanı özellik ekleyin ve ayarlayın, **öğesi adını** bayrağı.

     Diğer etki alanı özellikleri ekleyin.

     Görüntülemek istediğiniz her bir listesi için başka bir liste öğesi etki alanı sınıfına ekleyin.

3.  **Listedeki bir öğe, birkaç türlerini karma olarak**, liste sınıfından sınıfları oluşturmak. List sınıfı soyut belirleyerek kendi **devralma değiştirici**.

     Örneğin, sanatçı yerine oluşturucusu tarafından sıralanacak klasik müzik isterseniz, iki alt sınıfların şarkı, ClassicalSong ve NonClassicalSong oluşturabilirsiniz.

4.  **Bölme şekil oluşturmak**. Sürükleyin **bölme şekli** DSL tanımı diyagram üzerine aracı.

     Metin oluşturma öğesi ekleyin ve adını ayarlayın.

     Bir bölüm ekleyin ve adını ayarlayın.

5.  Liste bölmeler gizleme, bölme shape sınıfı sağ kullanıcı izin vermek için işaret **Ekle**ve ardından **Genişlet/Daralt oluşturma öğesi**. Özellikler penceresinde oluşturma öğesi konumunu ayarlayın.

6.  Tıklatın **diyagram öğesi harita** aracı, kapsayıcı etki alanı sınıfı tıklayın ve sonra bölme şekli tıklatın.

7.  Etki alanı sınıf ve şekil arasındaki diyagram öğesi harita bağlantısını seçin. İçinde **DSL ayrıntıları** penceresi:

    1.  Tıklatın **dekoratörler** sekmesi. Oluşturma öğesi adına tıklayın ve ardından uygun öğeyi altında seçin **görüntü özelliği**. Bir onay işareti oluşturma öğesi adının yanındaki göründüğünden emin olun.

    2.  Tıklatın **bölme eşlemeleri** sekmesi.

         Bölme adına tıklayın.

         Altında **görüntülenen öğeleri koleksiyonu yolu**, liste öğesi sınıfı (şarkı) gidin. Gezgin aracı kullanmak için açılan oku tıklatın.

         Altında **görüntü özelliği**, listede görüntülenen özelliğini seçin. Örnekte, başlık budur.

> [!NOTE]
>  Yol oluşturma öğesi eşlemesindeki ve bölme harita alanları kullanarak daha karmaşık arasındaki ilişkileri etki alanı sınıfları ve bölme şekli yapabilirsiniz.

#### <a name="to-define-a-tool-for-creating-the-shape"></a>Şekil oluşturmak için bir araç tanımlamak için

1.  **Etki alanı sınıfının öğeleri oluşturmak için bir araç kutusu öğesi olun.**

2.  İçinde **DSL Explorer**, genişletin **Düzenleyicisi** düğümü ve tüm alt düğümleri.

3.  Düğümü altında **araç kutusu sekmeleri** DSL, örneğin MusicLibrary aynı ada sahip. Tıklatın **öğesi aracı Ekle**.

    > [!NOTE]
    >  Sağ tıklattığınızda, **Araçları** düğümünü görmezsiniz **eklemek öğesi aracı**. Bunun yerine, yukarıdaki düğümünü tıklatın.

4.  Özellikler penceresinde seçili yeni öğe aracıyla ayarlayın **sınıfı** kısa süre önce eklemiş olduğunuz etki alanı sınıfı.

5.  Ayarlama **resim yazısı** ve **araç ipucu**.

6.  Ayarlama **araç kutusu simgesi** araç kutusunda görünür bir simge. Yeni bir simge veya zaten başka bir aracı için kullanılan bir simge ayarlayabilirsiniz.

     Yeni bir simge oluşturmak için de Dsl\Resources açın **Çözüm Gezgini**. Kopyalayın ve var olan öğe araç birini yapıştırın. BMP dosyaları. Yapıştırılan kopyayı yeniden adlandırın ve düzenlemek için çift tıklayın.

     Dönüş DSL tanımı diyagrama, Aracı'nı seçin ve Özellikler penceresinde tıklatın **[...]**  içinde **araç kutusu simgesi**. İçinde **seçin bit eşlem** iletişim kutusunda, açılır menüden, BMP dosyası seçin.

#### <a name="to-test-a-compartment-shape"></a>Bir bölme şekli sınamak için

1.  **Tüm Şablonları dönüştürme tıklatın** araç çubuğundaki DSL Tasarımcı kodu oluşturmak için Çözüm Gezgini'nde,.

2.  **Derleme ve DSL çalıştırın.** Visual Studio yeni bir örneğini Deneysel modda çalıştırmak için F5'e veya CTRL + F5 tuşuna basın. Visual Studio'nun deneysel örneğinde, DSL dosya adı uzantısına sahip bir dosya oluşturun veya açın.

3.  **Aracı araç kutusunda görüntülendiğini doğrulayın.**

4.  Aracı modeli diyagram üzerine sürükleyin. Bir şekli oluşturulur.

     Öğesinin adı görüntülenir ve bir varsayılan değer otomatik olarak ayarlandığını doğrulayın.

5.  Yeni şekli üstbilgisine sağ tıklayın ve ardından Ekle'yi tıklatın *bilgisayarınızı liste öğesi.* Örnekte, komut ekleme şarkı olur.

     Bir öğe listede görünür ve yeni bir ad olduğundan emin olun.

6.  Liste öğeleri birini tıklatın ve ardından Özellikler penceresini inceleyin. Liste öğeleri özelliklerini görmeniz gerekir.

7.  Dil Gezgini'ni açın. İçinde liste öğesi düğümlerle kapsayıcı düğümleri görebildiğini doğrulayın.

 ![Oluşturulan explorer'ın DSL](../modeling/media/music_explorer.png "Music_Explorer")

 Bir bölme şekli ilk test ettikten sonra özelliklerini ayarlamanıza ve daha gelişmiş özellikler eklemek isteyebilirsiniz. Daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

### <a name="displaying-a-reference-link-in-a-compartment"></a>Bir referans bağlantı bir bölüm içinde görüntüleme
 Genellikle, bir bölüm içinde görüntüleyen bir bölme şekil tarafından temsil edilen öğesinin bir alt öğedir. Ancak bazen, bir başvuru ilişkisi ile bağlı bir öğe görüntülemek istediğiniz.

 Örneğin, biz albümü bağlı Sanatçılar listesini görüntüler AlbumShape için ikinci bir bölme ekleyebilirsiniz.

 Bu durumda, bölme başvurulan öğenin yerine bağlantı görüntülemelidir. Kullanıcı bölüm içinde öğeyi seçer ve DELETE bastığında silinmesi için bağlantıyı istediğiniz olmasıdır başvurulan öğenin.

 Bununla birlikte, başvurulan öğenin adını bölüm içinde görünür olabilir.

 Bu bölümde daha önce açıklandığı gibi aşağıdaki yordamı zaten etki alanı sınıfı, başvuru ilişkisi, bölme şekli ve diyagram öğesi harita oluşturduğunuz varsayar.

##### <a name="to-display-a-reference-link-in-a-compartment"></a>Bir referans bağlantı bir bölüm içinde görüntülemek için

1.  **Bir bölme bölme şekle eklemek**. Bölme shape sınıfı DSL tanımı diyagramda sağ tıklayın, fareyle **Ekle**ve ardından **bölme**.

2.  Ayarlama **görüntülenen öğeleri koleksiyonu yolu** hedef öğe yerine bağlantısına gidin. Aşağı açılır menüsünü tıklatın ve hedefine yerine başvuru ilişkisi seçmek için ağaç görünümünü kullanın. Örnekte, ilişkidir **ArtistAppearedOnAlbums**.

3.  Ayarlama **görüntü özelliğe yol** bağlantıdan hedef öğesine gidin. Bu örnekte olduğu **sanatçı**.

4.  Ayarlama **görüntü özelliği** örneğin hedef öğe uygun özelliğine **adı**.

5.  **Tüm Şablonları dönüştürme**, yapı ve DSL çalıştırın ve bir test modeli açın.

6.  Model diyagramı şeklin uygun sınıfları oluşturmak, adlarını ayarlamak ve bunları arasında bir bağlantı oluşturun. Bölme şeklinde bağlantılı öğeler adlarını görüntülenmesi gerekir.

7.  Bağlantıyı veya öğeyi bölme şeklinde seçin. Bağlantı ve öğe kaybolur.

##  <a name="ports"></a> Bağlantı noktası başka bir şekil sınırında tanımlama
 Başka bir şekil sınırında bulunan bir şekli bir bağlantı noktasıdır.

 Bağlantı noktaları, bir sabit bağlantı noktası kullanıcı bağlayıcılar çizebilirsiniz başka bir şekil sağlamak için de kullanılabilir. Bu durumda, bağlantı noktası şekli saydam yapabilirsiniz.

 Bağlantı noktası kullanan bir örnek görmek için seçin **bileşen diyagramı** yeni bir DSL çözüm oluşturduğunuzda, şablon. Bu örnekte, bağlantı noktaları tanımladığınızda, göz önünde bulundurabilirsiniz ana noktaları göstermektedir:

-   Bağlantı noktaları, kapsayıcı temsil eden bir etki alanı sınıf yok `Component`.

-   Bağlantı noktaları temsil eden bir etki alanı sınıf yoktur. Bu örnekte olduğu `ComponentPort`.

-   Bağlantı noktası etki alanı sınıfı kapsayıcı etki alanı sınıfından katıştırma bir ilişkisi yok. Daha fazla bilgi için bkz: [etki alanı sınıfları tanımlama](#classes).

-   Aynı kapsayıcıda karma için bağlantı noktası farklı türlerde istiyorsanız, bağlantı noktası etki alanı sınıfının alt sınıfları oluşturabilirsiniz. Örnekte, `InPort` ve `OutPort` devralınmalıdır `ComponentPort`.

-   Kapsayıcı etki alanı sınıfı şekli herhangi bir tür için eşlenebilir. Örnek, `ComponentShape`. Daha fazla bilgi için bkz: [tanımlama şekiller](#shapes).

-   Bağlantı noktası etki alanı sınıflarını bağlantı noktası şekillere eşlenir. Bağlantı noktası şekil sınıflarını ayırmak için türetilen sınıflar harita veya map bir bağlantı noktası şekli sınıfı için temel sınıf.

 Diğer yönden bağlantı noktası şekiller açıklandığı gibi davranır [tanımlama şekiller](#shapes).

 Daha fazla bilgi için bkz: [bağlantı noktası özellikleri şekiller](../modeling/properties-of-port-shapes.md).

##  <a name="swimlanes"></a> Kulvarları sahip DSL tanımlama
 Kulvarları diyagramın yatay veya dikey bir bölüm mevcuttur. Her kulvarı bir model öğeye karşılık gelir. DSL tanımınızı bir etki alanı sınıfı için Kulvar öğeleri gerektirir.

 DSL kulvarları ile oluşturmak için en iyi yeni bir DSL çözümü oluşturun ve Görev akışı çözüm şablonu seçin yoludur. DSL tanımında Aktör sınıfı kulvara eşlenen etki alanı sınıftır. Bu ve diğer sınıfları projenizi uygun yeniden adlandırın.

 Şeklin içine bir Kulvar olarak görüntülenecek bir sınıf eklemek için Kulvar ve yeni sınıf arasında bir katıştırma ilişkisi oluşturun. Kullanıcılar öğeleri bir Kulvar sürükleyin mümkün olacaktır, ancak her öğe her zaman içinde belirli bir Kulvar olacaktır. Görev akışı çözüm şablonunda Kulvar sınıfının bir alt FlowElement değil.

 Bir şekli kulvarları bağımsız olarak görüntülenecek bir sınıf eklemek için kök ve yeni sınıf arasında bir katıştırma ilişkisi oluşturun. Kullanıcılar bu şekiller diyagramdan kulvarları ve kulvarları dışında sınırları dahil olmak üzere herhangi bir yere koyun kuramaz. Görev akışı çözüm şablonunda yorum kök sınıfı alt öğesidir.

 Daha fazla bilgi için bkz: [özellikleri, kulvarları](../modeling/properties-of-swimlanes.md).

##  <a name="addTypes"></a> Özellik türleri ekleme

### <a name="domain-enumerations-and-literals"></a>Etki alanı numaralandırmalar ve değişmez değerleri
 Bir etki alanı numaralandırma birkaç değişmez değerler ile bir türüdür.

 Bir etki alanı numaralandırma eklemek için modelde kökündeki sağ **DSL Explorer** ve ardından **ekleme yeni etki alanı numaralandırma**. Öğe görünür **DSL Explorer** altında **etki alanı türleri** düğümü. Bu öğe diyagramda görünmez.

 Etki alanı numaralandırma numaralandırma değişmez değerler eklemek için etki alanı sıralamasında sağ **DSL Explorer** ve ardından **ekleme yeni numaralandırma sabit değeri**.

 Varsayılan olarak, bir numaralandırma türü olan bir özelliğe numaralandırması aynı anda yalnızca bir değere ayarlanabilir. Kullanıcıların ve programcıları değerler - herhangi bir bileşimini ayarlayabilmek için istiyorsanız bir "bit alan" - kümesi **IsFlags** numaralandırma özelliği.

### <a name="external-types"></a>Dış türleri
 Türü bulamazsanız, bir etki alanı özelliğinin türü ayarladığınızda istediğiniz **türü** aşağı açılan listesinde, bir dış türe ekleyebilirsiniz. Örneğin, ekleyebilirsiniz **System.Drawing.Color** listesine türü.

 Bir türü eklemek için DSL Explorer'da modelin kökü sağ tıklayın ve ardından **yeni dış türü Ekle**. Özellikler penceresinde kümesinin adı **renk** ve ad alanına **System.Drawing**. Bu tür DSL Explorer altında görüntülenir **etki alanı türleri**. Bir etki alanı özelliğinin türü ayarladığınız her seçebilirsiniz.

##  <a name="custom"></a> DSL özelleştirme
 Bu konuda açıklanan teknikleri kullanarak, hızlı bir şekilde DSL grafiksel gösterimi, okunabilir bir XML form ve kod ve diğer yapıları oluşturmak için gereken temel Araçlar oluşturabilirsiniz.

 DSL tanımı genişletmek için iki yöntem vardır:

1.  DSL DSL tanımı daha fazla özelliklerini kullanarak hassas ayar yapma. Örneğin, bağlayıcı çeşitli türlerde oluşturabilirsiniz tek bağlayıcı aracını yapabilir ve hangi silerek bir öğe aynı zamanda ilgili öğeleri siler kuralları kontrol edebilirsiniz. Bu teknikler, çoğunlukla DSL tanımında değerlerini ayarlayarak sağlanır ve bazı birkaç satırlık bir program kodu gerektirir.

     Daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

2.  Modelleme Araçları, daha gelişmiş efektler elde etmek için program kodunu kullanarak genişletir. Örneğin, model değiştirebilirsiniz menü komutlarını oluşturabilirsiniz ve iki veya daha fazla DSL'ler tümleştirme araçları oluşturabilirsiniz. VMSDK DSL tanımından oluşturulan kod uzantılarınızın tümleştirileceğini kolaylaştırmak için tasarlanmıştır.  Daha fazla bilgi için bkz: [bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md).

### <a name="changing-the-dsl-definition"></a>DSL tanımı değiştirme
 Herhangi bir öğeyi DSL tanımında oluşturduğunuzda, birden fazla varsayılan değer otomatik olarak ayarlanır. Ayarlandıktan sonra bunları değiştirebilirsiniz. Bu güçlü özelleştirmeler için hala verirken bir DSL geliştirilmesini kolaylaştırır.

 Örneğin, bir şekli bir öğeye eşlediğinizde, eşlemenin üst öğe yolu etki alanı sınıfının katıştırma ilişki göre otomatik olarak ayarlanır. Ancak, daha sonra katıştırma ilişki değiştirirseniz, üst öğe yolu otomatik olarak değiştirilmez.

 Bu nedenle bazı ilişkiler DSL tanımınızı değiştirdiğinizde, tanımı kaydettiğinizde veya tüm şablonları dönüştürme, bildirilen hataları için alışılmadık olmadığını farkında olması gerekir. Bu hataların çoğu düzeltme kolaydır. Hata raporu hatanın konumunu görmek için çift tıklayın.

 Ayrıca bkz. [nasıl yapılır: bir etki alanına özgü dil Namespace değiştirmek](../modeling/how-to-change-the-namespace-of-a-domain-specific-language.md).

##  <a name="trouble"></a> Sorun giderme
 Aşağıdaki tabloda bazı kendi çözümü için öneriler ile birlikte bir DSL tasarlarken, karşılaşılan en yaygın sorunları listeler. Daha fazla öneri kullanılabilir [görselleştirme araçları Extensibililty Forumu](http://go.microsoft.com/fwlink/?LinkId=186074).

|Sorun|Öneri|
|-------------|----------------|
|DSL tanım dosyasında yapmış olduğunuz değişiklikleri hiçbir etkisi yoktur.|Tıklatın **tüm şablonları dönüştürme** Çözüm Gezgini ve sonra yeniden çözümü üstündeki araç içinde.|
|Şekiller oluşturma öğesi özellik değeri yerine adını gösterir.|Oluşturma öğesi eşlemesi ayarlayın. DSL tanımı diyagramı, etki alanı ve Şekil sınıf arasında bir gri satır diyagram öğesi Eşlem'i tıklatın.<br /><br /> Açık **DSL ayrıntıları** penceresi. Görünüm menüsünde, göremiyorsanız, işaret **diğer pencereler**ve ardından **DSL ayrıntıları**.<br /><br /> Tıklatın **oluşturma öğesi eşlemeleri** sekmesi. Oluşturma öğesi adını seçin. Yanındaki kutuyu işaretlediğinizden emin olun. Altında **görüntüleme özelliği**, bir etki alanı özellik adını seçin.<br /><br /> Daha fazla bilgi için bkz: [şekiller diyagramdan](#shapes).|
|Bir koleksiyona DSL Explorer'da ekleyemiyorum. Örneğin, araçları sağ tıklattığınızda, "Aracı Ekle" komutu yoktur menüde.<br /><br /> My DSL explorer'ın bir listesine bir öğe ekleyemiyorum.|Çalıştığınız düğümü Yukarıdaki öğeyi sağ tıklatın. Bir listeye eklemek istediğiniz, Ekle komutu listesi düğümünde ancak sahibi değildir.|
|Bir etki alanı sınıf oluşturuldu, ancak dil explorer'ın örneği oluşturulamıyor.|Kök dışında her etki alanı sınıf katıştırma bir ilişki hedefi olması gerekir.|
|My DSL explorer'ın öğeleri yalnızca tür adları ile gösterilir.|DSL tanımı'nda sınıfın bir etki alanı özelliği seçin ve Özellikler penceresinde ayarlayın **öğesi adını** true.|
|My DSL her zaman XML Düzenleyicisi'nde açar.|Dosyası okunurken bir hata nedeniyle oluşabilir. Ancak, bu hatayı düzeltmek daha sonra DSL Tasarımcısı olmasını Düzenleyicisi açıkça sıfırlamanız gerekir.<br /><br /> Proje öğesi sağ tıklayın, **birlikte Aç** seçip * YourLanguage ***Tasarımcısı (varsayılan)**.|
|Derleme adları değiştikten sonra my DSL araç görünmez.|İnceleyebilir ve güncelleştirme **DslPackage\GeneratedCode\Package.tt** daha fazla bilgi için bkz: [nasıl yapılır: bir etki alanına özgü dil Namespace değiştirmek](../modeling/how-to-change-the-namespace-of-a-domain-specific-language.md).|
|My DSL araç görünmez, ancak derleme adı değişmemiştir.<br /><br /> Veya, bir uzantı yükleme hatası raporlama bir ileti kutusu görünür.|Deneysel örneği sıfırlayın ve, çözümü yeniden derleyin.<br /><br /> 1.  Windows Başlat menüsü, altında **tüm programlar**, genişletin [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)], ardından **Araçları**ve ardından **Microsoft Visual Studio deneysel örneği sıfırlama**.<br />2.  Visual Studio üzerinde**yapı** menüsünde tıklatın **çözümü yeniden derle**.|

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki Alanına Özgü Dillerle Çalışmaya Başlama](../modeling/getting-started-with-domain-specific-languages.md)
- [Windows Forms Tabanlı Etki Alanına Özgü Dil Oluşturma](../modeling/creating-a-windows-forms-based-domain-specific-language.md)
- [WPF Tabanlı Etki Alanına Özgü Dil Oluşturma](../modeling/creating-a-wpf-based-domain-specific-language.md)