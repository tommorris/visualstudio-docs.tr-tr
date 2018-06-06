---
title: Kodunuz aracılığıyla bağımlılık diyagramları oluşturma
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 73f3cf2bbb5903a3c2dda8c531f28e9aa81facad
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749707"
---
# <a name="create-dependency-diagrams-from-your-code"></a>Kodunuz aracılığıyla bağımlılık diyagramları oluşturma

Yazılım sisteminizin üst düzey, mantıksal mimarisi görselleştirmek için oluşturun bir *bağımlılık diyagramı* Visual Studio. Kodunuzu bu tasarım ile tutarlı kalmasını sağlamak için bir bağımlılık diyagramı ile kodunuzu doğrulayın. Visual C# ve Visual Basic projeleri için bağımlılık diyagramları oluşturabilirsiniz. Bu özellik, Visual Studio'nun hangi sürümleri desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

![Bir bağımlılık diyagramı oluşturma](../modeling/media/layerdiagramvisualizecode.png)

Bir bağımlılık diyagramı, Visual Studio çözüm öğeleri olarak adlandırılan mantıksal, soyut gruplar halinde düzenlemenizi sağlar *katmanları*. Bu yapıların gerçekleştirdiği temel görevleri veya sistemin ana bileşenlerini açıklamak için katmanları kullanabilirsiniz. Her katman, daha ayrıntılı görevleri açıklayan başka katmanlar içerebilir. Hedeflenen veya varolan da belirtebilirsiniz *bağımlılıkları* katmanlar arasında. Oklar olarak temsil edilen bu bağımlılıklar, hangi katmanların diğer katmanlar tarafından temsil edilen işlevi kullanabileceğini veya kullanmakta olduğunu gösterir. Kodunun mimari denetimini sağlamak için diyagram üzerinde hedeflenen bağımlılıkları gösterin ve ardından kodu diyagrama karşı doğrulayın.

[Video: mimarisi bağımlılıklarınızı gerçek zamanlı doğrula](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)

##  <a name="CreateDiagram"></a> Bir bağımlılık diyagramı oluşturma

Bir bağımlılık diyagramı oluşturmadan önce çözümünüzü modelleme projesine sahip olduğundan emin olun.

> [!IMPORTANT]
> Yok eklemek, sürükleyin veya varolan bir bağımlılık diyagramını modelleme projesinden başka bir modelleme projesine veya çözümdeki başka bir yere kopyalayın. Bu, diyagramı değiştirseniz bile orijinal diyagramdan yapılan başvuruları korur. Bu, katman doğrulamasının doğru çalışmasını da engeller ve siz diyagramı açmaya çalışırken kayıp öğeler veya başka hatalar gibi diğer sorunlara da neden olabilir.
>
> Bunun yerine, yeni bir bağımlılık diyagramı modelleme projesine ekleyin. Öğeleri kaynak diyagramdan yeni diyagrama kopyalayın. Modelleme projesi ve yeni bağımlılık diyagram kaydedin.

#### <a name="to-add-a-new-dependency-diagram-to-a-modeling-project"></a>Yeni bir bağımlılık diyagramı modelleme projesine eklemek için

1.  Üzerinde **mimarisi** menüsünde seçin **yeni bağımlılık diyagram**.

2.  Altında **şablonları**, seçin **bağımlılık diyagramı**.

3.  Diyagrama ad verin.

4.  İçinde **eklemek modelleme projesine**bulun ve var olan bir modelleme projesi, çözümünüz seçin.

     veya

     Seçin **yeni bir modelleme projesi oluşturma** çözüme yeni bir modelleme projesi eklemek için.

    > [!NOTE]
    >  Bağımlılık diyagramı modelleme projesi içinde bulunmalıdır. Bununla birlikte, bunu çözümün herhangi bir yerindeki öğelere bağlayabilirsiniz.

5.  Modelleme projesi ve bağımlılık diyagramı kaydettiğinizden emin olun.

## <a name="drag-and-drop-or-copy-and-paste-from-a-code-map"></a>Sürükleme ve bırakma, veya kopyalayın ve yapıştırın, kod eşlemesinden

1. Çözümü kullanan bir kod Haritası Oluştur **mimarisi** menüsü.

2. Yalnızca ürün kodu bağımlılıkları zorlamak istiyorsanız çözüm klasörleri ve "Test varlıklar" kaldırmak için bir kod Haritası filtre uygulamayı düşünün.

3. Oluşturulan kod eşleme "Dış" düğümünü kaldırmak veya ad alanı bağımlılıkları zorlamak istediğinize bağlı olarak dış derlemeler göstermek için genişletin ve gerekli olmayan derlemeleri kod eşlemesinden silin.

4. Çözüm kullanmak için yeni bir bağımlılık diyagramı oluşturmak **mimarisi** menüsü

5. Kod Haritası tüm düğümlerde seçin (kullanmak _Ctrl_ + _A_, veya tuşlarına basarak pencere bant seçimini kullan _Shift_ ' ı tıklatın, sürükleyin ve bırakın önce anahtar.

6. Sürükleme ve bırakma, ya da bir kopyalama ve yapıştırma seçilen öğeleri yeni bağımlılık doğrulama diyagrama.

7. Geçerli uygulama mimarisi gösterilir. Mimari olmasını istediğinize karar verin ve bağımlılık diyagramı uygun şekilde değiştirin.

![Kod eşlemesinden oluşturulan bağımlılık diyagramı](media/dependency-validation-01.png)

##  <a name="CreateLayers"></a> Yapılardan katmanlar oluşturma
 Visual Studio çözüm öğelerinden projeler, kod dosyaları, ad alanları, sınıflar ve yöntemler gibi katmanlar oluşturabilirsiniz. Bu, katmanlar ve öğeler arasında otomatik olarak bağlantılar oluşturarak bunları katman doğrulama işlemine dahil eder.

 Katmanları Word belgeleri veya PowerPoint sunumları gibi doğrulamayı desteklemeyen öğelere de ekleyebilir ve böylece bir katmanı belirtimlerle veya planlarla ilişkilendirebilirsiniz. Katmanları birden fazla uygulama arasında paylaşılan projelerdeki dosyalara da bağlayabilirsiniz, ancak doğrulama işlemi "Katman 1" ve "Katman 2" gibi genel adlarla görünen bu katmanları içermez.

 Bağlantılı bir öğe doğrulama destekleyip desteklemediğini görmek için açık **Katman Gezgini** ve inceleyin **doğrulamayı destekler** öğesinin özelliği. Bkz: [yapıt bağlantıları yönetme](#Managing).

|**Hedef**|**Aşağıdaki adımları izleyin**|
|------------|----------------------------|
|Tek bir yapı için katman oluşturma|<ol><li>Öğe, bu kaynaklardan bağımlılık diyagram üzerine sürükleyin:<br /><br /> <ul><li>**Çözüm Gezgini**<br /><br />         Örneğin, dosyaları veya projeleri sürükleyebilirsiniz.</li><li>Kod haritaları<br /><br />         Bkz: [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md) ve [kullanım kod eşlemeleri uygulamalarınızda hata ayıklamak için](../modeling/use-code-maps-to-debug-your-applications.md).</li><li>**Sınıf Görünümü** veya **Nesne Tarayıcısı**</li></ul><br />     Katman, diyagramda görünür ve yapıya bağlanır.</li><li>İlişkili kodun veya yapıların sorumluluklarını yansıtmak için katmanı yeniden adlandırın.</li></ol> **Önemli:** bağımlılık diyagrama ikili dosyaları sürükleme otomatik olarak eklemez başvurularını modelleme projesi için. Doğrulamak istediğiniz ikili dosyaları el ile modelleme projesine eklemeniz gerekir. **İkili dosyaları modelleme projesine eklemek için** <ol><li>İçinde **Çözüm Gezgini**modelleme projesi için kısayol menüsünü açın ve ardından **varolan öğeyi Ekle**.</li><li>İçinde **varolan öğeyi Ekle** iletişim kutusunda, Gözat ikili dosyaları, bunları seçin ve ardından **Tamam**.     İkili dosyalar modelleme projesinde görünür.</li><li>İçinde **Çözüm Gezgini**, eklenen ve tuşuna basarak bir ikili dosya seçin **F4** açmak için **özellikleri** penceresi.</li><li>Her bir ikili dosya üzerinde ayarlamak **yapı eylemi** özelliğine **doğrulama**.</li></ol>|
|Seçilen tüm yapılar için tek bir katman oluşturma|Tüm yapıları aynı anda bağımlılık diyagrama sürükleyin.<br /><br /> Katman diyagramda görünür ve tüm yapılara bağlıdır.|
|Seçilen her yapı için bir katman oluşturma|Basılı **SHIFT** tüm yapıları bağımlılık diyagrama aynı anda tutarak sürükleyin anahtar. **Not:** kullanırsanız **SHIFT** anahtarı bir dizi öğeyi seçmek için yapıları seçtikten sonra tuşunu bırakın. Yapıları diyagrama sürüklerken tuşu tekrar basılı tutun. <br /><br /> Katman her yapı için diyagramda görünür ve her yapıya bağlanır.|
|Katmana yapı ekleme|Yapıyı katmana sürükleyin.|
|Bağlantısız bir katman oluşturma|İçinde **araç**, genişletin **bağımlılık diyagramı** bölümünde ve ardından sürükleyin bir **katman** bağımlılık diyagrama.<br /><br /> Çoklu katman eklemek için araca çift tıklayın. İşiniz bittiğinde, seçin **işaretçi** aracını veya tuşuna **ESC** anahtarı.<br /><br /> - veya -<br /><br /> Bağımlılık diyagram için kısayol menüsünü açın, seçin **Ekle**ve ardından **katman**.|
|İç içe katmanlar oluşturma|Varolan katmanı başka bir katmanın üzerine sürükleyin.<br /><br /> - veya -<br /><br /> Bir katman için kısayol menüsünü açın, seçin **Ekle**ve ardından **katman**.|
|Varolan iki veya daha fazla katmanı içeren yeni bir katman oluşturma|Katmanları seçin, seçiminiz için kısayol menüsünü açın ve ardından **grup**.|
|Katmanın rengini değiştirme|Ayarlama, **renk** istediğiniz renk özelliğine.|
|Bir katman ile ilişkili yapıların belirli ad alanlarına ait olmaması gerektiğini belirtme|Katmanın içinde ad alanlarını yazın **Yasak Ad alanları** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|
|Bir katman ile ilişkili yapıların belirli ad alanlarına bağlı olamayacağını belirtme|Katmanın içinde ad alanlarını yazın **Yasak Namespace bağımlılıkları** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|
|Bir katman ile ilişkili yapıların belirli ad alanlarından birine ait olması gerektiğini belirtme|Katmanın içinde ad alanını yazın **gereken ad alanlarını** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|

 Bir katmandaki sayı, katmana bağlı olan yapıların sayısını gösterir. Ancak, bu sayıyı okurken, aşağıdakileri unutmayın:

-   Bir katman diğer yapıları içeren bir yapıya bağlanırsa, ancak katman doğrudan diğer yapılara bağlanmazsa, sayı yalnızca bağlı yapıyı içerir. Bununla birlikte, diğer yapılar katman doğrulanırken analiz için alınır.

     Örneğin, bir katman tek bir ad alanına bağlanırsa, ad alanı sınıflar içerse bile, bağlı yapıların sayısı 1'dir. Katmanın ad alanındaki her bir sınıfa da bağlantıları bulunuyorsa, sayı bağlantılı sınıfları da içerecektir.

-   Bir katman yapılarla bağlantılı diğer katmanları içeriyorsa, kapsayıcı katman da üzerindeki sayı bu yapıları içermese bile bu yapılara bağlıdır.

##  <a name="Managing"></a> Katmanlar ve Yapılar arasındaki bağlantıları yönetme

1.  Bağımlılık diyagramdaki katman için kısayol menüsünü açın ve ardından **bağlantıları görüntüleme**.

     **Explorer katman** seçili katman için yapı bağlantılarını gösterir.

2.  Bu bağlantıları yönetmek için aşağıdaki görevleri kullanın.

|**Hedef**|**Katman Gezgini**|
|------------|---------------------------|
|Katman ve yapı arasındaki bağlantıyı silme|Yapı bağlantısı için kısayol menüsünü açın ve ardından **silmek**.|
|Bağlantıyı bir katmandan diğerine taşıma|Yapı bağlantısını diyagramda varolan bir katmana sürükleyin.<br /><br /> - veya -<br /><br /> 1.  Yapı bağlantısı için kısayol menüsünü açın ve ardından **Kes**.<br />2.  Bağımlılık diyagramdaki katman için kısayol menüsünü açın ve ardından **Yapıştır**.|
|Bağlantıyı bir katmandan diğerine kopyalama|1.  Yapı bağlantısı için kısayol menüsünü açın ve ardından **kopya**.<br />2.  Bağımlılık diyagramdaki katman için kısayol menüsünü açın ve ardından **Yapıştır**.|
|Varolan yapı bağlantısından yeni bir katman oluşturma|Yapı bağlantısını diyagramdaki boş bir alana sürükleyin.|
|Bağlantılı bir yapı bağımlılık diyagramına dayalı doğrulamayı desteklediğini doğrulayın.|Bakmak **doğrulamayı destekler** yapı bağlantısı için sütun.|

##  <a name="Discovering"></a> Ters mühendislik Varolan bağımlılıkları
 Bir bağımlılık, bir katman ile ilişkili yapının başka bir katman ile ilişkili bir yapıya başvurusu olduğu yerde var olur. Örneğin, bir katmandaki sınıf başka bir katmanda sınıfı olan değişkeni bildirir. Diyagramdaki katmanlara bağlanmış yapılar için varolan bağımlılıklara ters mühendislik uygulayabilirsiniz.

> [!NOTE]
>  Bağımlılıklarda belirli türdeki yapılar için ters mühendislik uygulanamaz. Örneğin, hiçbir bağımlılıkta metin dosyasına bağlı katmandan veya katmana ters mühendislik uygulanmaz. Hangi yapıların ters mühendislik uygulayabileceğiniz bağımlılıkları olduğunu görmek için bir veya birden çok katmanları için kısayol menüsünü açın ve ardından **bağlantıları görüntüleme**. İçinde **Katman Gezgini**, inceleyin **doğrulamayı destekler** sütun. Bağımlılıklar, bu sütunda görüntülenir yapıtlar için ters mühendislik olmayacak **False**.

-   Bir veya birden çok katman seçin, seçili bir katman için kısayol menüsünü açın ve ardından **Bağımlılıklar Oluştur**.

 Genellikle var olmaması gereken bazı bağımlılıklar göreceksiniz. Bu bağımlılıkları hedeflenen tasarım ile uyumlu hale getirmek için düzenleyebilirsiniz.

##  <a name="EditDependencies"></a> Katmanları ve bağımlılıkları hedeflenen tasarımı göstermek için düzenleme
 Sisteminiz veya hedeflenen mimari yapmayı planladığınız değişiklikleri açıklamak için bağımlılık diyagramı düzenleyin:

|**Hedef**|**Bu adımları uygulayın**|
|------------|-----------------------------|
|Bağımlılık yönünü değiştirme veya kısıtlama|Ayarlama, **yönü** özelliği.|
|Yeni bağımlılıklar oluşturma|Kullanım **bağımlılık** ve **çift yönlü bağımlılık** araçları.<br /><br /> Çoklu bağımlılıklar çizmek için araca çift tıklayın. İşiniz bittiğinde, seçin **işaretçi** aracını veya tuşuna **ESC** anahtarı.|
|Bir katman ile ilişkili yapıların belirli ad alanlarına bağlı olamayacağını belirtme|Katmanın içinde ad alanlarını yazın **Yasak Namespace bağımlılıkları** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|
|Bir katman ile ilişkili yapıların belirli ad alanlarına ait olmaması gerektiğini belirtme|Katmanın içinde ad alanlarını yazın **Yasak Ad alanları** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|
|Bir katman ile ilişkili yapıların belirli ad alanlarından birine ait olması gerektiğini belirtme|Katmanın içinde ad alanını yazın **gereken ad alanlarını** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|

##  <a name="EditLayout"></a> Öğeleri diyagramı görüntülenme şeklini değiştirme
 Özelliklerini düzenleyerek katmanların boyutunu, şeklini, rengini ve konumunu veya bağımlılıkların rengini değiştirebilirsiniz.

##  <a name="Codemaps"></a> Desenleri ve bir kod Haritası bağımlılıkları Bul
 Bağımlılık diyagramları oluşturulurken, aynı zamanda oluşturabilirsiniz **kod eşlemeleri**. Bu diyagramları kodu keşfetmenize sırada desenleri ve bağımlılıkları keşfetmenize yardımcı olabilir. Çözüm Gezgini, sınıf görünümü ve Nesne Tarayıcısı derlemeler, ad alanları ve genellikle de mevcut katmanlara karşılık gelen sınıflar - keşfetmek için kullanın. Kod eşlemeleri hakkında daha fazla bilgi için bkz:

-   [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)

-   [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)

-   [Kod haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)

## <a name="see-also"></a>Ayrıca Bkz.

- [Video: mimarisi bağımlılıklarınızı gerçek zamanlı doğrula](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)
- [Bağımlılık Diyagramları: Başvuru](../modeling/layer-diagrams-reference.md)
- [Bağımlılık Diyagramları: Yönergeler](../modeling/layer-diagrams-guidelines.md)
- [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)
- [Kodu görselleştirme](../modeling/visualize-code.md)
