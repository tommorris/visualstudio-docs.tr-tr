---
title: 'Bağımlılık diyagramları: yönergeler'
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
ms.openlocfilehash: 9ce90746d89dd41c1f53d7150d83afaa2e2bad46
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31954398"
---
# <a name="dependency-diagrams-guidelines"></a>Bağımlılık diyagramları: yönergeler
Uygulama Mimarinizi yüksek bir düzeyde oluşturarak açıklamak *bağımlılık diyagramları* Visual Studio. Bir bağımlılık diyagramı kodunuzla doğrulayarak kodunuzu bu tasarım ile tutarlı kaldığından emin olun. Katman doğrulaması yapı işleminizin de ekleyebilirsiniz. Bkz: [kanal 9 Video: tasarım ve bağımlılık diyagramları kullanarak Mimarinizi geçerli](http://go.microsoft.com/fwlink/?LinkID=252073).

 Bu özellik, Visual Studio'nun hangi sürümleri desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="what-is-a-dependency-diagram"></a>Bir bağımlılık diyagramı nedir?
 Geleneksel mimari diyagram gibi bir bağımlılık diyagramı ana bileşenlerini veya işlevsel birimlerini tasarım ve onların bağımlılıklarını tanımlar. Diyagramdaki her düğüm olarak adlandırılan bir *katman*, ad alanları, projeler veya diğer yapıları mantıksal grubunu temsil eder. Tasarımınızda bulunması gereken bağımlılıkları çizebilirsiniz. Geleneksel mimari diyagramın aksine, kaynak kodundaki gerçek bağımlılıkları belirttiğiniz hedeflenen bağımlılıklara uygun doğrulayabilirsiniz. Düzenli bir yapı doğrulama parçası üzerinde yaparak [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)], program kodunu gelecekteki değişiklikler sistemin mimarisine uygun devam ettiğinden emin olmak. Bkz: [bağımlılık diyagramları: başvuru](../modeling/layer-diagrams-reference.md).

##  <a name="Update"></a> Tasarım veya bağımlılık diyagramları ile uygulamanızı güncelleştirme
 Aşağıdaki adımlar bağımlılık diyagramları geliştirme süreci içinde kullanmak nasıl bir bakış sağlar. Bu konunun sonraki bölümlerinde her adım hakkında daha fazla ayrıntı açıklanmaktadır. Yeni bir tasarım geliştiriyorsanız varolan koda başvuran adımları atlayın.

> [!NOTE]
>  Bu adımları yaklaşık sırada görünür. Muhtemelen görevleri çakışma, kendi durum uyacak şekilde yeniden sıralamak ve her bir yineleme projenizdeki başlangıcında bunları yeniden ziyaret istersiniz.

1.  [Bir bağımlılık diyagramı oluşturmak](#Create) tüm uygulama veya içindeki bir katman için.

2.  [Birincil işlev alanları veya bileşenleri göstermek için katman tanımlama](#CreateLayers) uygulamanızın. Bu katmanlar kendi işlevi göre örneğin, "Sunu" veya "Hizmetler" olarak adlandırın. Varsa bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözüm, her katman içeren bir koleksiyonu ilişkilendirebilirsiniz *yapıları*projeleri, ad alanları, dosyaları vb. gibi.

3.  [Varolan bağımlılıkları keşfetme](#Generate) katmanlar arasında.

4.  [Katmanları ve bağımlılıkları düzenleme](#EditArchitecture) güncelleştirilmiş göstermek için tasarım yansıtmak için kodu istiyor.

5.  [Tasarım, uygulamanızın yeni alanlarını](#NewAreas) asıl mimari blokları veya bileşenleri göstermek için katman oluşturarak ve her katmanın diğer nasıl kullandığını göstermek için bağımlılıkları tanımlama.

6.  [Düzen ve diyagram görünümünü düzenleme](#EditLayout) arkadaşlarınızla ele yardımcı olacak.

7.  [Bağımlılık diyagramı karşı kod doğrulama](#Validate) kod ve mimari arasındaki çakışmaları vurgulayın.

8.  [Yeni mimarinize uygun olması için kodu güncelleştirme](#UpdateCode). Yinelemeli olarak geliştirme ve doğrulama kadar yeniden düzenleme kod çakışmalar gösterir.

9. [Katman doğrulaması yapı işlemine dahil](#BuildValidation) kodu tasarımınıza devam etmesini sağlamak için.

##  <a name="Create"></a> Bir bağımlılık diyagramı oluşturma
 Bir bağımlılık diyagramı modelleme projesi içinde oluşturulmalıdır. Yeni bir bağımlılık diyagramı var olan bir modelleme projesi eklemek, bağımlılık diyagramı için yeni bir modelleme projesi oluşturma veya varolan bir bağımlılık diyagramını aynı modelleme projesi içinde kopyalayın.

> [!IMPORTANT]
>  Değil ekleme, sürükleyin veya varolan bir bağımlılık diyagramını modelleme projesinden başka bir modelleme projesine veya çözümdeki başka bir konuma kopyalayın. Diyagram bile değiştirirseniz bu şekilde kopyalanan bir bağımlılık diyagramı özgün diyagram ile aynı referansları sahip olur. Bu katman doğrulaması düzgün çalışmasını engeller ve eksik öğeleri gibi diğer sorunları veya diğer hataları diyagramı açmaya çalışırken neden olabilir.

 Bkz: [kodunuzdan bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md).

##  <a name="CreateLayers"></a> İşlevsel alanlara veya bileşenleri göstermek için katman tanımlama
 Katmanlar temsil oluşan mantıksal grupları *yapıları*projeleri, kod dosyaları, ad alanları, sınıflar ve yöntemler gibi. Visual C# ve Visual Basic projelerden Yapılardan katmanlar oluşturabilir veya Word dosyaları veya PowerPoint sunumları gibi belgeleri bağlayarak bir katmana belirtimler veya planlar ekleyebilirsiniz. Her Katman diyagramda dikdörtgen olarak görünür ve ona bağlı olan yapıların sayısını gösterir. Bir katman daha belirli görevleri açıklayan iç içe geçmiş katmanları içerebilir.

 Genel kural olarak, örneğin, "Sunu" veya "Hizmetler" adı Katmanlar kendi işlevi göre. Yapılar yakından bağlıysa, onları aynı katmana yerleştirin. Yapıları ayrı olarak güncelleştirilen ya da ayrı uygulamalarda kullanılır, bunları farklı katmanlara yerleştirin. Katman desenleri hakkında bilgi edinmek için desenleri ve uygulamalar sitesini ziyaret edin [ http://go.microsoft.com/fwlink/?LinkId=145794 ](http://go.microsoft.com/fwlink/?LinkId=145794).

> [!TIP]
>  Belirli türde bir katmanlara bağlayabilirsiniz yapıları yoktur ancak bağımlılık diyagramı doğrulanması desteklemez. Yapının doğrulamayı destekleyip desteklemediğini görmek için açın **Katman Gezgini** incelemek için **doğrulamayı destekler** yapı bağlantısının özelliği. Bkz: [katmanlar arasında varolan bağımlılıkları keşfetme](#Generate).

 Tanınmayan bir uygulama güncelleştirilirken kod haritalarını de oluşturabilirsiniz. Bu diyagramları kodu keşfetmenize sırada desenleri ve bağımlılıkları keşfetmenize yardımcı olabilir. Ad alanları ve genellikle de mevcut katmanlara karşılık sınıfları keşfetmek için Çözüm Gezgini'ni kullanın. Bu kod yapılar bağımlılık diyagramlarına Çözüm Gezgini'nden sürükleyerek katmanlara atayın. Bağımlılık diyagramları sonra kodunu güncelleştirin ve tasarımınız ile tutarlı kalmasına yardımcı olmak için de kullanabilirsiniz.

 Bkz.

-   [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)

-   [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)

-   [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)

##  <a name="Generate"></a> Katmanlar arasında varolan bağımlılıkları keşfetme
 Bir bağımlılık, bir katman ile ilişkili yapının başka bir katman ile ilişkili bir yapıya başvurusu olduğu yerde var olur. Örneğin, bir katmandaki sınıf başka bir katmanda sınıfı olan değişkeni bildirir. Var olan bağımlılıkları ters mühendislik uygulayarak bulabilmesi için bunları.

> [!NOTE]
>  Bağımlılıklarda belirli türdeki yapılar için ters mühendislik uygulanamaz. Örneğin, hiçbir bağımlılıkta metin dosyasına bağlı katmandan veya katmana ters mühendislik uygulanmaz. Hangi yapıların ters mühendislik uygulayabileceğiniz bağımlılıkları olduğunu görmek için bir veya birden çok katmanlara sağ tıklayın ve ardından **bağlantıları görüntüleme**. İçinde **Katman Gezgini**, inceleyin **doğrulamayı destekler** sütun. Bağımlılıklar, bu sütunda görüntülenir yapıtlar için ters mühendislik olmayacak **False**.

#### <a name="to-reverse-engineer-existing-dependencies-between-layers"></a>Ters mühendislik katmanlar arasında için var olan bağımlılıkları

-   Bir katman veya birden çok katman seçin, seçili katmana sağ tıklayın ve ardından **Bağımlılıklar Oluştur**.

 Genellikle var olmaması gereken bazı bağımlılıklar göreceksiniz. Bu bağımlılıkları hedeflenen tasarım ile uyumlu hale getirmek için düzenleyebilirsiniz.

##  <a name="EditArchitecture"></a> Katmanları ve bağımlılıkları hedeflenen tasarımı göstermek için düzenleme
 Sisteminiz veya hedeflenen mimari yapmayı planladığınız değişiklikleri açıklamak için bağımlılık diyagramı düzenlemek için aşağıdaki adımları kullanın. Ayrıca, bazı yeniden düzenleme kod yapısını genişletmeden önce iyileştirmek değişiklik yapmayı düşünebilirsiniz. Bkz: [kod yapısını geliştirme](#Improving).

|**Hedef**|**Bu adımları uygulayın**|
|------------|-----------------------------|
|Var olmaması gereken bir bağımlılığı silin|Bağımlılık tıklayın ve sonra basın **silmek**.|
|Bağımlılık yönünü değiştirme veya kısıtlama|Ayarlama, **yönü** özelliği.|
|Yeni bağımlılıklar oluşturma|Kullanım **bağımlılık** ve **çift yönlü bağımlılık** araçları.<br /><br /> Çoklu bağımlılıklar çizmek için araca çift tıklayın. İşiniz bittiğinde, tıklatın **işaretçi** aracını veya tuşuna **ESC** anahtarı.|
|Bir katman ile ilişkili yapıların belirli ad alanlarına bağlı olamayacağını belirtme|Katmanın içinde ad alanlarını yazın **Yasak Namespace bağımlılıkları** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|
|Bir katman ile ilişkili yapıların belirli ad alanlarına ait olmaması gerektiğini belirtme|Katmanın içinde ad alanlarını yazın **Yasak Ad alanları** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|
|Bir katman ile ilişkili yapıların belirli ad alanlarından birine ait olması gerektiğini belirtme|Katmanın içinde ad alanını yazın **gereken ad alanlarını** özelliği. Noktalı virgül kullanın (**;**) ad alanlarını ayırmak için.|

###  <a name="Improving"></a> Kod yapısını geliştirme
 Yeniden düzenleme değişiklikleri uygulamanın davranışını etkilemez, ancak kodu değiştirin ve uzatabilirsiniz daha kolay hale Yardım geliştirmeleridir. İyi yapılandırılmış kodun bir bağımlılık diyagrama soyut kolaydır bir tasarıma sahiptir.

 Örneğin, her ad alanı için bir katman kodu ve ardından ters mühendislik bağımlılıkları oluşturursanız, olmalıdır katmanlar arasında tek yönlü bağımlılıkları en az bir dizi. Sınıfları veya yöntemleri katmanınız gibi kullanarak daha ayrıntılı bir diyagram oluşturursanız, sonuç de aynı özelliklere olmalıdır.

 Bu durumda değilse, kod ömrü boyunca değiştirmek daha zor olacaktır ve bağımlılık diyagramları kullanarak doğrulama için daha az uygun olacaktır.

##  <a name="NewAreas"></a> Uygulamanızın yeni alanlarını tasarlama
 Yeni bir proje ile yeni bir proje veya yeni bir alan geliştirme başlattığınızda katmanları ve kod geliştirmeye başlamadan önce önemli bileşenleri belirlemeye yardımcı olmak için bağımlılıkları çizebilirsiniz.

-   **Tanımlanabilen mimari desenleri gösterin** Mümkünse, bağımlılık diyagramlarındaki. Örneğin, bir masaüstü uygulamasını tanımlayan bir bağımlılık diyagramı sunu, etki alanı mantığı ve veri deposu gibi katmanları içerebilir. Bir uygulama içinde tek bir özellik kapsayan bir bağımlılık diyagramı Model, Görünüm ve denetleyici gibi katmanları olabilir. Desenler hakkında daha fazla bilgi için bkz: [desenleri ve uygulamalar: uygulama mimarisi](http://go.microsoft.com/fwlink/?LinkId=145794).

-   **Her katman için kod yapısı oluşturun** ad alanı, sınıf veya bileşen gibi. Bu kodu izlemenizi ve kod yapılarını katmanlara bağlamak için kolaylaştırır. Her yapı oluşturur oluşturmaz uygun katmana bağlayın.

-   **Çoğu sınıf ve diğer yapıları katmanlara bağlamak zorunda değil** katmanlara zaten bağlı ad alanları gibi daha büyük yapılarını bunlar kapsamında kalan olduğundan.

-   **Yeni bir özellik için yeni bir diyagram oluşturma**. Genellikle, tüm uygulama açıklayan bir veya daha fazla bağımlılık diyagramları olacaktır. Uygulama içinde yeni bir özellik tanımlıyorsanız, değil eklemek veya mevcut diyagramları değiştirin. Bunun yerine, yeni kod parçalarını yansıtır kendi diyagramı oluşturun. Yeni Diyagram Katmanlar sunu, etki alanı mantığı ve yeni bir özellik için veritabanı katmanları içerebilir.

     Uygulamasını derlerken, kodunuzu hem genel diyagramı ve daha ayrıntılı özelliği diyagramı karşı doğrulanacak.

##  <a name="EditLayout"></a> Sunu ve tartışma için Düzen
 Katmanları ve bağımlılıkları tanımlamaya veya takım üyeleriyle tartışmaya yardımcı olması için aşağıdaki yollarla diyagramın düzenini ve görünümünü düzenleyin:

-   Boyutları, Şekil ve Katmanlar konumlarını değiştirin.

-   Katmanları ve bağımlılıkları rengini değiştirin.

    -   Bir veya daha fazla katmanları veya bağımlılıkları, sağ tıklatın ve ardından seçin **özellikleri**. İçinde **özellikleri** penceresinde Düzenle **renk** özelliği.

##  <a name="Validate"></a> Diyagram karşı kod doğrulama
 Diyagram düzenlendiğinde, istediğiniz zaman el ile veya otomatik olarak kod karşı yerel yapıyı çalıştırdığınız her zaman doğrulamak için veya [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)].

 Bkz.

-   [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)

-   [Katman doğrulaması yapı işlemine dahil](#BuildValidation)

##  <a name="UpdateCode"></a> Yeni mimarinize uygun olması için kodu güncelleştirme
 Genellikle, hatalar, güncelleştirilmiş bağımlılık diyagramı karşı kod doğrulama ilk kez görünecektir. Bu hatalar birkaç nedeni olabilir:

-   Yapı yanlış katmana atanmış. Bu durumda, yapıyı taşıyın.

-   Sınıf gibi bir yapı, başka bir sınıfı mimarinizle çakışacak şekilde kullanıyor. Bu durumda, bağımlılığı kaldırmak için kodu yeniden düzenleyin.

 Bu hataları çözmek için doğrulama sırasında daha fazla hata görünmeyene kadar kodu güncelleştirin. Bu genellikle yinelemeli bir işlemdir. Bu hatalar hakkında daha fazla bilgi için bkz: [bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md).

> [!NOTE]
>  Geliştirme veya kodu yeniden gibi bağımlılık diyagrama bağlamak için yeni yapılar olabilir. Ancak, var olan ad alanlarını gösteren Katmanlar olduğunda bu örneğin, gerekli olmayabilir ve yeni kod, daha fazla malzeme yalnızca bu ad alanlarına ekler.

 Geliştirme işlemi sırasında, doğrulama esnasında bildirilen çakışmaların bazılarını gizlemek isteyebilirsiniz. Örneğin, zaten çözdüğünüz veya özel senaryonuzla ilgili olmayan hataları gizlemek isteyebilirsiniz. Bir hatayı bastırmak, bir iş öğesi oturum açmak için iyi bir uygulama olur [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]. Bu görevi gerçekleştirmek için bkz: [bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md).

##  <a name="BuildValidation"></a> Katman doğrulaması yapı işlemine dahil
 Gelecekte yapılan değişiklikler kod bağımlılık diyagramlarına uyumlu olmasını sağlamak için çözümünüzün standart yapı işlemine katman doğrulaması içerir. Diğer ekip üyelerinin çözümü derleme olduğunda, koddaki bağımlılıkları ve bağımlılık diyagram arasındaki farklılıkları derleme hataları olarak raporlanır. Yapı işleminde katman doğrulama hakkında daha fazla bilgi için bkz: [bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md).

## <a name="see-also"></a>Ayrıca Bkz.

- [Bağımlılık Diyagramları: Başvuru](../modeling/layer-diagrams-reference.md)
- [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)
