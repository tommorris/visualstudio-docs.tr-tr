---
title: "Çözümlerinizdeki bağımlılıkları eşleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- vs.progression.codemap
- vs.progression.standardgraphsdialog
helpviewer_keywords:
- Visual Studio Ultimate, dependency graphs
- code exploration, dependency graphs
- dependency graphs, exporting
- code exploration, relationships
- DGML
- graph documents
- code visualization [Visual Studio ALM]
- graph documents, saving
- dependencies, visualizing
- dependency graphs, saving
- Visual Studio Ultimate, code visualization
- code, visualizing
- dependency graphs, creating
- dependency graphs
- graph documents, exporting
- code exploration, visualizing
ms.assetid: e04850a2-17c5-459b-93ec-6c74143b3292
caps.latest.revision: "243"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.workload: multiple
ms.openlocfilehash: fc8d9774c69216136eb2b4c99b379ef1c714997f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="map-dependencies-across-your-solutions"></a>Çözümlerinizdeki bağımlılıkları eşleme
Kodunuz boyunca bağımlılıkları anlamak istediğinizde, kod haritalarını oluşturarak bunları görselleştirin. Bu nasıl kodu birlikte dosyaları ve kod satırlarını aracılığıyla okumadan uyduğunu görmenize yardımcı olur.  
  
 ![Çözümlerinizdeki bağımlılıkları görüntülemek](../modeling/media/codemapsmainintro.png "CodeMapsMainIntro")  
  
 **Bazı videolar işte**:  
  
-   [Kod bağımlılıklarınızın görselleştirme aracılığıyla anlama](http://go.microsoft.com/fwlink/?LinkID=252065)  
  
-   [Değişikliğin etkisini Görselleştirme](http://go.microsoft.com/fwlink/?LinkID=252068)  
  
-   [Kod haritaları karmaşık koduyla anlama](http://go.microsoft.com/fwlink/?LinkID=259869)  
  
##  <a name="GetStarted"></a>Kod haritaları ile çalışmaya başlama  
 **Kod haritaları kullanmak için ya da ihtiyaç duyarsınız**:  
  
-   Visual Studio Enterprise: kod haritalarını kod düzenleyiciden Çözüm Gezgini, sınıf görünümü ve Nesne Tarayıcısı oluşturun.  
  
-   Visual Studio Professional: kod haritalarını açın, sınırlı düzenlemeleri yapın ve kod gidin.  
  
> [!WARNING]
>  Visual Studio Professional kullanan Visual Studio kuruluşta başkalarıyla oluşturulan eşlemeleri paylaşmadan önce tüm öğeleri (örneğin, gizli öğeleri, genişletilmiş grupları ve çapraz grup bağlantılarını) harita üzerinde görünür yapıldığından emin olun.  
  
 **Bu dilde kodu bağımlılıklarını eşleyebilirsiniz**:  
  
-   Visual C# .NET veya Visual Basic .NET bir çözüm ya da derlemeler (.dll veya .exe)  
  
-   Yerel veya yönetilen C veya C++ kodu Visual C++ projelerinde üstbilgi dosyaları (.h veya `#include`), ya da ikili dosyalar  
  
-   X ++ proje ve Microsoft Dynamics AX for .NET modüllerden yapılan derlemeler  
  
 **Not:** C# veya Visual Basic .NET dışındaki projeleri için kod Haritası başlatılıyor veya varolan bir kod Haritası öğeler ekleme için daha az seçenek vardır. Örneğin, C++ projesi metin düzenleyicisinde bir nesneye sağ tıklayın ve bir kod Haritası ekleyin. Ancak, sürükleyin ve kod öğeleri veya dosyaları Çözüm Gezgini'nde sınıf görünümü ve Nesne Tarayıcısı bırakın.  
  
#### <a name="to-see-the-overall-dependencies-across-your-solution"></a>Çözümünüzü arasında genel bağımlılıkları görmek için  
  
1.  Açık **mimarisi** menüsü.  
  
2.  Yalnızca çözüm açılıp henüz yerleşik yapmadıysanız, ya da kodunuzu son yedeklemeden bu yana değişti yerleşik olarak seçin **çözüm için kod Haritası Oluştur**.  
  
3.  En son ne zaman, derlendikten sonra kodunuzu değişmediğinden kaldığınızda **olmadan çözüm oluşturmak için kod Haritası Oluştur** harita oluştururken daha hızlı performans almak için.  
  
4.  [Genel bağımlılıkları görmek](#SeeOverviewSource) çözümünüzü arasında genel bağımlılıkları görüntülemek için kod haritalarını nasıl kullanabileceğinizi anlamak için.  
  
#### <a name="to-see-specific-dependencies-within-your-solution"></a>Çözümünüzü belirli bağımlılıkları görmek için  
  
1.  Yüklenen çözümünüzle birlikte Aç **Çözüm Gezgini**.  
  
2.  Tüm projeleri, derleme başvurularını, klasörleri, dosyaları, türleri veya eşlemek istediğiniz üyeleri seçin.  
  
3.  Üzerinde **Çözüm Gezgini** araç seçin **kod haritasında Göster**![oluşturma yeni grafik gelen seçili düğümleri düğmesini](../modeling/media/createnewgraphfromselectedbutton.gif "CreateNewGraphFromSelectedButton "). Veya kısayol menüsünü açın ve seçin **kod haritasında Göster**. Sınıf Görünümü veya Nesne Tarayıcısı öğelerinden bir yeni veya varolan bir kod Haritası sürükleyebilirsiniz.  
  
4.  [Belirli bağımlılıkları görmek](#SeeSpecificSource) belirli bağımlılıkları çözümünüz içinde görüntülemek için kod haritalarını nasıl kullanabileceğinizi anlamak için.  
  
###  <a name="CreateEmptyMap"></a>Yeni bir boş kod Haritası çözümünüze eklemek için  
  
1.  İçinde **Çözüm Gezgini**, üst düzey çözüm düğümünüz için kısayol menüsünü açın. Seçin **Ekle** ardından **yeni öğe**.  
  
2.  Altında **yüklü**, seçin **genel**.  
  
3.  Sağ bölmede seçin **yönlendirilmiş grafik belgesi** ve ardından **Ekle**.  
  
     Şimdi çözümünüzün içinde görünür boş bir harita sahip **çözüm öğeleri** klasör.  
  
#### <a name="to-create-a-new-empty-code-map-without-adding-it-to-your-solution"></a>Çözümünüze eklemeden yeni bir boş kod haritası oluşturmak için  
  
1.  Açık **mimarisi** menü ve **yeni kod Haritası**.  
  
     \-veya -  
  
2.  Açık **dosya** menü ve **yeni** ardından **dosya**.  
  
3.  Altında **yüklü**, seçin **genel**.  
  
4.  Sağ bölmede seçin **yönlendirilmiş grafik belgesi** ve ardından **açık**.  
  
     Artık çözümünüzün klasörlerde görünmez boş bir harita var.  
  
##  <a name="SeeOverviewSource"></a>Genel bağımlılıkları bakın  
  
###  <a name="OverviewSource"></a>Çözümünüzü arasında bağımlılıkları bakın  
  
1.  Üzerinde **mimarisi** menüsünde seçin **çözüm için kod Haritası Oluştur**.  
  
     ![Bir kod Haritası komutu oluşturmak](../modeling/media/codemapsarchitecturemenu.png "CodeMapsArchitectureMenu")  
  
     Üst düzey derlemeler ve aralarındaki toplanmış bağlantıları gösteren bir harita alın. Daha geniş birleşik bağlantı, daha fazla bağımlılıkları temsil eder.  
  
2.  Kullanım **gösterge** düğmesini proje türü simgeler (örneğin, Test, Web ve telefon Proje), Listesi'ni göster veya gizle için kod Haritası araç çubuğundaki kod öğeleri (örneğin, sınıfları, yöntemleri ve özellikleri) ve ilişki türleri (örneğin, devralır gelen Uygular ve çağrıları).  
  
     ![Üst &#45; düzeyi bağımlılık grafiğinin derlemelerin](../modeling/media/dependencygraph_toplevelassemblies.png "DependencyGraph_TopLevelAssemblies")  
  
     Bu örnek bir çözüm çözüm klasörleri içerir (**testleri** ve **bileşenleri**), Test projeleri, Web projeleri ve derlemeler. Varsayılan olarak tüm kapsama ilişkileri görünür *grupları*, genişletme ve daraltma. **Externals** grubu platform bağımlılıklar dahil olmak üzere çözümünüzü dışında her şeyi içerir. Dış derlemeler yalnızca kullanılan öğeleri gösterir. Varsayılan olarak, sistem temel türleri görünmesine eşlemek gizlenir.  
  
3.  Eşlemeye detaya gitmek için projeler ve derlemeleri temsil eden Gruplar'ı genişletin. Her şeyi tuşlarına basarak genişletin **CTRL + A** tüm düğümler ve ardından seçme seçmek için **grup**, **genişletme** kısayol menüsünden.  
  
     ![Kod Haritası tüm gruplarında genişletme](../modeling/media/codemapsexpandallgroups.png "CodeMapsExpandAllGroups")  
  
4.  Ancak, bu büyük bir çözüm için yararlı olabilir. Aslında, karmaşık çözümleri için bellek sınırlamaları tüm grupları genişletme engelleyebilir. Bunun yerine, tek bir düğümde görmek için onu genişletin. Düğüm üzerinde fare işaretçisini taşıyın ve sonra (aşağı ok) Köşeli Çift Ayraca tıklayın zaman görünür.  
  
     ![Kod Haritası düğümü genişletme](../modeling/media/dependencygraph_containment.png "DependencyGraph_Containment")  
  
     Veya öğeyi seçerek ardından artı tuşuna basarak klavyeyi kullanma (**+**). Kod daha derin düzeylerini keşfetmek için ad alanlarını, türleri ve üyeleri için aynı işlemi yapın.  
  
    > [!TIP]
    >  Kodu ile çalışma hakkında daha fazla ayrıntı için kullanarak fare, klavye ve dokunma, bkz: eşlemeleri [göz atın ve haritalar kod sıralama](../modeling/browse-and-rearrange-code-maps.md).  
  
5.  Haritayı basitleştirmek ve tek tek parçaları üzerinde odaklanmak için tercih **filtreleri** kod Haritası araç ve yalnızca select düğümleri ve bağlantıları türlerini ilgilendiğiniz. Örneğin, tüm çözüm klasörü ve derleme kapsayıcıları gizleyebilirsiniz.  
  
     ![Kapsayıcıları filtreleyerek haritayı basitleştirmek](../modeling/media/codemapsfilterfoldersassemblies.png "CodeMapsFilterFoldersAssemblies")  
  
     Harita, gizleme veya bireysel gruplar ve öğeleri temel çözüm kodunu etkilemeden eşlemesinden kaldırarak da basitleştirebilir.  
  
6.  Öğeleri arasında ilişkiler görmek için bunları eşlemesinde seçin. Bağlantı renklerini gösterildiği gibi ilişki türlerini belirtmek **gösterge** bölmesi.  
  
     ![Çözümlerinizdeki bağımlılıkları görüntülemek](../modeling/media/codemapsmainintro.png "CodeMapsMainIntro")  
  
     Bu örnekte, çağrıları mor bağlantılardır, başvuruları noktalı bağlantılardır ve açık mavi alan erişimi bağlantılardır. Yeşil bağlantılar devralma olabilir ya da olabilir *toplama bağlantılar* birden fazla ilişki türünü belirtin (veya *kategori*).  
  
    > [!TIP]
    >  Yeşil bağlantı görürseniz, bu yalnızca bir devralma ilişkisi anlamına gelmez. Ayrıca yöntem çağrılarını de olabilir, ancak bunlar devralma ilişkisi tarafından gizlenir. Belirli bağlantı türlerini görmek için onay kutularını kullanın **filtreleri** ilginizi olmayan türleri gizlemek için bölmesi.  
  
7.  Bir öğe veya bağlantı hakkında daha fazla bilgi almak için bir araç ipucu görünene kadar işaretçiyi üzerine taşıyın. Kod öğesi veya bağlantısını temsil eder kategorileri ayrıntılarını gösterir.  
  
     ![Bir ilişki kategorileri göster](../modeling/media/codemapsshowlinkcatgories.png "CodeMapsShowLinkCatgories")  
  
8.  Öğeleri ve birleşik bir bağlantı tarafından temsil edilen bağımlılıkları incelemek için ilk bağlantıyı seçin ve ardından kısayol menüsünü açın. Seçin **bağlantılar katkıda bulunan Göster** (veya **yeni kod Haritası bağlantıları katkıda bulunan Göster**). Bu bağlantının her iki ucundaki gruplarını genişletir ve yalnızca öğe ve katılmak bağımlılıkları bağlantıyı gösterir.  
  
9. İçinde harita belirli kısımlarını odaklanmak için ilgi olmayan öğeleri kaldırmak devam edebilirsiniz. Örneğin, sınıf ve üye görünüme incelemek için yalnızca tüm ad alanı düğümlerin filtre **filtreleri** bölmesi.  
  
     ![Sınıf ve üye düzeye ayrıntılara](../modeling/media/dependencygraph_expandedselectedgroups_2012.png "DependencyGraph_ExpandedSelectedGroups_2012")  
  
10. Başka bir odakta bir karmaşık çözüm harita için mevcut bir haritayı gelen seçili öğeleri içeren yeni bir harita oluşturmak için yoludur. Tutun **CTRL** odaklanmak istediğiniz öğeleri seçerken kısayol menüsünü açın ve seçin **seçimden yeni bir grafik**.  
  
     ![Seçili öğeleri yeni bir kod haritasında Göster](../ide/media/codemapsshowonnewmap.png "CodeMapsShowOnNewMap")  
  
11. İçeren bağlamı için yeni eşleme devredilir. Çözüm klasörleri ve kullanarak görmesini istemiyorsanız kapsayıcıları Gizle **filtreleri** bölmesi.  
  
     ![Görünümü basitleştirmek için kapsayıcılara filtre](../modeling/media/codemapsexpandnewgroups.png "CodeMapsExpandNewGroups")  
  
12. Gruplar'ı genişletin ve ilişkileri görüntülemek için eşlemesinde öğeleri seçin.  
  
     ![İlişkileri görüntülemek için öğeleri seçin](../modeling/media/codemapsviewnewrelationships.png "CodeMapsViewNewRelationships")  
  
 Ayrıca bkz.:  
  
-   [Kod haritalarına göz atma ve bunları yeniden düzenleme](../modeling/browse-and-rearrange-code-maps.md)  
  
-   [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md)  
  
-   Kodunuzda tarafından olası sorunları bulma [çalışan bir çözümleyiciyi](../modeling/find-potential-problems-using-code-map-analyzers.md).  
  
###  <a name="OverviewCompiled"></a>Derlemeleri veya ikili dosyalar arasında bağımlılıkları bakın  
  
1.  [Bir boş kod Haritası oluşturma](#GetStarted), veya varolan bir kod eşlemesini (.dgml dosyası) açın.  
  
2.  Derlemeleri veya ikili dosyaları harita üzerine dış Visual Studio'dan eşlemek istediğiniz sürükleyin. Örneğin, derlemeler veya ikili dosyaları Windows Explorer veya dosya Gezgini'nden sürükleyin.  
  
> [!NOTE]
>  Aynı kullanıcı erişim denetimi (UAC) izinleri düzeyinde yalnızca ve Visual Studio çalıştırıyorsanız, Windows Gezgini veya dosya Gezgini'nden derlemeler veya ikili dosyaları sürükleyebilirsiniz. Örneğin, UAC açık olduğundan ve yönetici olarak Visual Studio çalıştırıyorsanız, Windows Gezgini veya dosya Gezgini'ni sürükleme işlemi engeller. Bu sorunu çözmek için hem aynı izin düzeyindeki çalışır durumdaki veya UAC kapatmak emin olun.  
  
##  <a name="SeeSpecificSource"></a>Belirli bağımlılıkları bakın  
 Örneğin, bazı dosyaları bekleyen değişiklikleri gerçekleştirmek için bir kod gözden geçirme olduğunu varsayalım. Bu değişiklikleri bağımlılıkları görmek için bu dosyaları bir kod Haritası oluşturabilirsiniz.  
  
 ![Belirli bağımlılıkları kod haritasında Göster](../modeling/media/codemapsspecificdependenciesintro.png "CodeMapsSpecificDependenciesIntro")  
  
### <a name="see-specific-dependencies-in-your-solution"></a>Çözümünüzdeki belirli bağımlılıkları bakın  
  
1.  Açık **Çözüm Gezgini**. Projeleri, derleme başvurularını, klasörleri, dosyaları, türleri ve sizi ilgilendiren üyeleri seçin. Türler veya üyeler bağımlı öğeleri bulmak için tür veya üye kısayol menüsünden açmak **Çözüm Gezgini**. Bağımlılık türü seçin ve ardından sonuçlar'ı seçin.  
  
2.  Öğelerinizi ve üyeleri eşleyin. Üzerinde **Çözüm Gezgini** araç çubuğunda **kod haritasında Göster**![oluşturma yeni grafik gelen seçili düğümleri düğmesini](../modeling/media/createnewgraphfromselectedbutton.gif "CreateNewGraphFromSelectedButton").  
  
     ![Eşleştirmek istediğiniz öğeleri seçin](../modeling/media/codemapsselectinsolutionexplorer.png "CodeMapsSelectInSolutionExplorer")  
  
3.  Harita seçili öğeleri içeren derlemelerini içinde gösterir.  
  
     ![Seçili öğeleri gruplar harita üzerinde gösterilen](../modeling/media/codemapsshowitemsfromsolnexplorer.png "CodeMapsShowItemsFromSolnExplorer")  
  
     Çözüm Gezgini, sınıf görünümü veya nesne boş bir tarayıcıya veya varolan bir kod Haritası ayrıca öğeleri sürükleyebilirsiniz. Boş bir harita oluşturmak için bkz: [boş kod Haritası oluşturma](#GetStarted). Üst hiyerarşi öğeleriniz için eklenecek basılı **CTRL** öğeleri sürükleyin ya da kullanmak anahtar **dahil üst** varsayılan eylem belirtmek için kod Haritası araç çubuğunda.  
  
    > [!NOTE]
    >  Windows Phone veya Windows Mağazası gibi birden fazla uygulama arasında paylaşılan bir projeden öğeler eklediğinizde, bu öğeler etkin olan projeyle eşlemede görünür. Bağlamı başka bir uygulama projesi olarak değiştirirseniz ve paylaşılan projeden daha fazla öğe eklerseniz, bu öğeler yeni etkin olan uygulama projesiyle görünür. Eşleme üzerinde bir öğeyle gerçekleştirdiğiniz işlemler, yalnızca aynı bağlamı paylaşılan öğeler için geçerlidir.  
  
4.  Öğeleri keşfetmek için bunları genişletin. Fare işaretçisini öğenin üzerine taşıyın ve sonra görüntülendiğinde Köşeli Çift Ayraca (aşağı ok) simgesine tıklayın.  
  
     ![Kod Haritası düğümü genişletme](../modeling/media/dependencygraph_containment.png "DependencyGraph_Containment")  
  
     Tüm öğeleri genişletmek için bunları seçin kullanarak **CTRL + A**, ardından harita kısayol menüsünü açın ve seçin **grup**, **genişletme**. Ancak, tüm grupları genişletme kullanılamaz bir eşlemesi veya bellek sorunları oluşturursa, bu seçenek kullanılamaz.  
  
5.  Öğeleri, gerekirse şu sınıf ve üye düzeye ilgilendiğiniz genişletmeye devam edin.  
  
     ![Sınıf ve üye düzeyi gruplar'ı genişletin](../modeling/media/codemapsexpandtoclassandmember.png "CodeMapsExpandToClassAndMember")  
  
     Kodda, ancak görünmüyor üyeleri haritada görmek için tıklatın **yeniden getirmesi alt** simgesi ![yeniden getirmesi alt simge](../modeling/media/dependencygraph_deletednodesicon.png "DependencyGraph_DeletedNodesIcon") üst bir grup sol üst köşesinin.  
  
6.  Bu harita üzerinde ilgili daha fazla öğe görüntülemek için birini seçin ve seçin **Göster ilgili** kod Haritası araç çubuğunda, sonra eşlemesine eklemek için ilgili öğeler türünü seçin. Alternatif olarak, bir veya daha fazla öğe seçin, kısayol menüsünü açın ve ardından **göster...**  eşlemesine eklemek için ilgili öğe türü için seçeneği. Örneğin:  
  
     İçin bir **derleme**, seçin:  
  
    |||  
    |-|-|  
    |**Bu başvuruları derlemeleri Göster**|Bu derlemenin başvurduğu derlemeleri ekleyin. Dış derlemeler görünür **Externals** grubu.|  
    |**Bu başvuru derlemeleri Göster**|Çözümde bu derlemeye başvuran derlemeleri ekleyin.|  
  
     İçin bir **ad alanı**, seçin **içeren derleme Göster**görünür değilse.  
  
     İçin bir **sınıfı** veya **arabirimi**, seçin:  
  
    |||  
    |-|-|  
    |**Taban türleri Göster**|Bir sınıf için taban sınıfı ve uygulanan arabirimleri ekleyin.<br /><br /> Bir arabirim için temel arabirimleri ekleyin.|  
    |**Türetilen türlerin Göster**|Bir sınıf için türetilmiş sınıfları ekleyin.<br /><br /> Bir arabirim için türetilmiş arabirimleri ve uygulama sınıflarını veya yapılarını ekleyin.|  
    |**Bu başvuruları türleri Göster**|Tüm sınıfları ve bu sınıfın kullandığı üyeleri ekleyin.|  
    |**Bu başvuru türleri Göster**|Tüm sınıfları ve bu sınıfı kullanan üyelerini ekleyin.|  
    |**Namespace içeren Göster**|Üst ad ekleyin.|  
    |**Namespace içeren ve derleme Göster**|Üst kapsayıcı hiyerarşisini ekleyin.|  
    |**Tüm temel türleri Göster**|Yinelemeli olarak taban sınıf veya arabirim hiyerarşisi ekleyin.|  
    |**Tüm türetilmiş türler Göster**|Bir sınıf için tüm türetilmiş sınıfları yinelemeli olarak ekleyin.<br /><br /> Bir arabirim için türetilmiş tüm arabirimleri ve uygulama sınıflarını veya yapılarını yinelemeli olarak ekleyin.|  
  
     İçin bir **yöntemi**, seçin:  
  
    |||  
    |-|-|  
    |**Bu çağıran yöntemleri Göster**|Bu yöntemin çağırdığı yöntemleri ekleyin.|  
    |**Bu başvurular alanları göster**|Bu yöntemin başvurduğu alanları ekleyin.|  
    |**Türünü içeren Göster**|Üst tür ekleyin.|  
    |**İçeren türü, Namespace ve derleme Göster**|Üst kapsayıcı hiyerarşisini ekleyin.|  
    |**Geçersiz kılınan yöntemleri Göster**|Diğer yöntemleri geçersiz kılan veya bir arabirimin yöntemini uygulayan bir yöntem için geçersiz kılınan taban sınıflardaki tüm soyut ya da sanal yöntemleri ve varsa arabirimin uygulanan yöntemini ekleyin.|  
  
     İçin bir **alan** veya **özelliği**, seçin:  
  
    |||  
    |-|-|  
    |**Türünü içeren Göster**|Üst tür ekleyin.|  
    |**İçeren türü, Namespace ve derleme Göster**|Üst kapsayıcı hiyerarşisini ekleyin.|  
  
     ![Bu üye tarafından adlı yöntemler Göster](../modeling/media/codemapsshowrelatedmethods.png "CodeMapsShowRelatedMethods")  
  
7.  Harita ilişkiler gösterilmektedir. Bu örnekte, yöntemleri tarafından çağrılır `Find` yöntemi ve konumlarını çözüm ya da dışarıdan.  
  
     ![Belirli bağımlılıkları kod haritasında Göster](../modeling/media/codemapsspecificdependenciesintro.png "CodeMapsSpecificDependenciesIntro")  
  
8.  Haritayı basitleştirmek ve tek tek parçaları üzerinde odaklanmak için tercih **filtreleri** kod Haritası araç ve yalnızca select düğümleri ve bağlantıları türlerini ilgilendiğiniz. Örneğin, çözüm klasörleri, derlemeler ve ad alanlarının görüntülenmesini devre dışı bırakın.  
  
     ![Görüntü basitleştirmek için Filtre bölmesini kullanın](../modeling/media/almcodemapfilterpane.png "ALMCodeMapFilterPane")  
  
##  <a name="SeeSourceHeader"></a>C ve C++ kaynak dosya ve üstbilgi dosyası arasındaki bağımlılıkları bakın  
 C++ projeleri için daha kapsamlı eşlemeleri oluşturmak isterseniz, Gözat bilgi derleyici seçeneği ayarlayın (**/FR**) o projelerde. Aksi durumda, bir ileti görüntülenir ve bu seçeneği ayarlamanızı ister. Seçerseniz **Tamam**, bu seçeneği yalnızca geçerli eşlemesi için ayarlar. Tüm sonraki eşlemeleri için iletisini gizlemek seçebilirsiniz. Bu iletiyi Gizle varsa, bunu yeniden görünür duruma getirebilirsiniz. Aşağıdaki kayıt defteri anahtarını ayarlamak `0` veya anahtarı silin:  
  
 **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\NativeProvider: AutoEnableSbr**  
  
 Visual C++ projeleri içeren bir çözümü açtığınızda, IntelliSense veritabanını güncelleştirmek biraz zaman alabilir. Bu süre boyunca, üstbilgi için kod haritalarını oluşturmak mümkün olmayabilir (.h veya `#include`) IntelliSense veritabanı güncelleştirme tamamlanana kadar dosyaları. Visual Studio durum çubuğunda güncelleştirme ilerleme durumunu izleyebilirsiniz. Sorunları veya belirli IntelliSense ayarları devre dışı bırakıldığı için görüntülenen iletileri çözümlemek için bkz: [maps C ve C++ kodu için sorun giderme](#Troubleshooting).  
  
-   Tüm kaynak dosya ve üstbilgi dosyası, çözümünüzdeki arasındaki bağımlılıkları görmek için **mimarisi** menüsünde seçin **oluşturmak grafik dahil dosyaların**.  
  
     ![Yerel kod için bağımlılık grafiğinin](../modeling/media/dependencygraphgeneral_nativecode.png "DependencyGraphGeneral_NativeCode")  
  
-   Şu anda açık dosya ile ilgili kaynak dosyaları ve başlık dosyaları arasındaki bağımlılıkları görmek için kaynak dosya veya üst bilgi dosyasını açın. Herhangi bir yere dosyası içindeki dosya kısayol menüsünü açın. Seçin **dosyaları Ekle grafiği oluşturmak**.  
  
     ![İlk &#45; .h dosyası düzeyi bağımlılık grafiğinin](../modeling/media/dependencygraph_native_firstlevel.png "DependencyGraph_Native_FirstLevel")  
  
###  <a name="Troubleshooting"></a>MAPS C ve C++ kodu için sorun giderme  
 Bu öğeler için C ve C++ kodu desteklenmez:  
  
-   Taban türleri üst hiyerarşiyi içeren eşlemeleri görünmüyor.  
  
-   Çoğu **Göster** menü öğeleri C ve C++ kodu için kullanıma sunulmaz.  
  
 C ve C++ kodu için kod haritalarını oluşturduğunuzda, bu sorunları oluşabilir:  
  
|**Sorunu**|**Olası neden**|**Çözümleme**|  
|---------------|------------------------|--------------------|  
|Kod Haritası oluşturma başarısız oldu.|Çözümdeki hiçbir proje başarıyla oluşturulmadı.|Oluştu derleme hataları düzeltin ve harita yeniden oluşturun.|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]kod eşlemesinden oluşturmaya çalıştığınızda yanıt vermeyi **mimarisi** menüsü.|Program veritabanı (.pdb) dosyası bozulmuş olabilir.<br /><br /> .pdb dosyası; tür, yöntem ve kaynak dosya bilgileri gibi hata ayıklama bilgilerini depolar.|Çözümü yeniden oluşturun ve tekrar deneyin.|  
|IntelliSense göz atma veritabanı için belirli ayarlar devre dışı bırakılır.|Bazı IntelliSense ayarları içinde devre dışı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **seçenekleri** iletişim kutusu.|Bunları etkinleştirmek için ayarları etkinleştirin.<br /><br /> Bkz: [seçenekler, metin düzenleyici, C/C++, Gelişmiş](../ide/reference/options-text-editor-c-cpp-advanced.md).|  
|İleti **bilinmeyen yöntemleri** yöntemi düğümünde görünür.<br /><br /> Yöntemin adı çözümlenemediği için bu sorun oluşur.|İkili dosya temel konum değişikliği tablosuna sahip olmayabilir.|Aç **/FIXED:NO** bağlayıcı seçeneği.|  
||Program veritabanı (.pdb) dosyası oluşturulmamış olabilir.<br /><br /> .pdb dosyası; tür, yöntem ve kaynak dosya bilgileri gibi hata ayıklama bilgilerini depolar.|Aç **/DEBUG** bağlayıcı seçeneği.|  
||.pdb dosyasını beklenen konumda açamıyor veya bulamıyor.|.pdb dosyasının beklenen konumlarda var olduğundan emin olun.|  
||Hata ayıklama bilgileri, .pdb dosyasından çıkarıldı.|Varsa **/PDBSTRIPPED** seçeneği bağlayıcı kullanıldı, bunun yerine tam .pdb dosyasını içerir.|  
||Arayan bir işlev değildir ve ikili dosyada bir dönüştürücü ya da veri bölümünde bir işaretçidir.|Çağıran bir dönüştürücü olduğunda kullanmayı deneyin `_declspec(dllimport)` dönüştürücü önlemek için.|  
  
##  <a name="RenderMoreQuickly"></a>Kod eşlemeleri daha hızlı bir şekilde işlemek olun  
 İlk kez bir harita oluşturduğunuzda, Visual Studio bulduğu tüm bağımlılıkları dizinler. Bu işlem özellikle büyük çözümler için biraz zaman alabilir ancak daha sonra performansı iyileştirir. Kodunuzu değişirse, Visual Studio yalnızca güncelleştirilmiş kod yeniden dizinler. Harita işleme tamamlamak geçen süreyi en aza indirmek için aşağıdakileri göz önünde bulundurun:  
  
-   [Sizi ilgilendiren bağımlılıkları eşleme.](#SeeSpecificSource)  
  
-   Çözümün tamamında harita oluşturmadan önce çözüm kapsamını azaltır.  
  
-   Otomatik derleme ile çözüm için devre dışı bırakma **Atla yapı** kod Haritası araç çubuğunda.  
  
-   Otomatik ile üst öğelerinin ekleme devre dışı bırakma **dahil üst** kod Haritası araç çubuğunda.  
  
-   Doğrudan düğümleri ve gerekli olmayan bağlantıları kaldırmak için kod Haritası dosyasını düzenleyin. Harita değiştirme, arka plandaki kod etkilemez. Bkz: [Özelleştir kod eşlemeleri DGML dosyalarını düzenleyerek](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
 ![Atla yapı ve dahil üst düğmeleri](../modeling/media/codemapsfilterskipbuildicons.png "CodeMapsFilterSkipBuildIcons")  
  
 Visual Studio 1 GB bellek ile çalıştırmanız mümkün olmakla birlikte, bilgisayarınızda en az 2 Visual Studio kod dizini oluştururken ve harita oluşturur uzun gecikmelerden kaçınmak için GB bellek olması önerilir.  
  
 Eşlemeleri oluşturmak veya öğeleri haritaya Çözüm Gezgini'nden bir proje öğesi, kullanıcının eklemek için daha fazla zaman alabilir **çıktı dizinine Kopyala** özelliği ayarlanmış **her zaman Kopyala**. Bu, artımlı yapılarla ve Visual Studio'nun projeyi her seferinde yeniden oluşturmasıyla ilgili sorunlara neden olabilir. Performansı artırmak için bu özelliği değiştirmek **yeniyse Kopyala** veya `PreserveNewest`. Bkz: [artımlı derlemeler](../msbuild/incremental-builds.md).  
  
 Tamamlanan Eşleme başarıyla oluşturulmuş kod için yalnızca bağımlılıkları gösterir. Derleme hataları belirli bileşenler meydana gelirse, bu hataları harita üzerinde görünür. Bir bileşenin gerçekten oluşturur ve haritada temel mimari kararlar önce bağımlılıkları olduğundan emin olun.  
  
##  <a name="SavingExporting"></a>Kod haritaları paylaşma  
  
### <a name="share-the-map-with-other-visual-studio-users"></a>Harita diğer Visual Studio kullanıcılarla paylaşma  
 Kullanım **dosya** harita kaydetmek için menüsünden.  
  
 veya  
  
 Harita belirli projesinin bir parçası harita kaydetmek için araç çubuğunda, seçin **paylaşımı**, **taşıma** \< *CodeMapName*>**.dgml içine**ve harita kaydetmek istediğiniz projesi'ni seçin.  
  
 ![Başka bir projeye bir harita taşıma](../modeling/media/codemapsmovemapmenu.png "CodeMapsMoveMapMenu")  
  
 Visual Studio harita Visual Studio Enterprise ve Visual Studio Professional diğer kullanıcılarla paylaşmak bir .dgml dosyası olarak kaydeder.  
  
> [!NOTE]
>  Visual Studio Professional kullananlar ile bir eşleme paylaşmadan önce tüm gruplar'ı genişletin, gizli düğümleri gösterin ve gruplar arası bağlantılar ve başkalarının harita üzerinde görmesini istediğiniz silinen tüm düğümleri almak emin olun. Aksi takdirde, diğer kullanıcıların bu öğeleri görmesi mümkün olmayacaktır.  
>   
>  Modelleme projesinde veya bir modelleme projesinden başka bir konuma kopyalanan bir harita kaydettiğinizde, aşağıdaki hata oluşabilir:  
>   
>  "Kaydedilemiyor *fileName* proje dizininin dışında. Bağlantılı öğeler desteklenmez."  
>   
>  Visual Studio hatayı gösterir, ancak kaydedilen sürümü de oluşturur. Hatayı önlemek için modelleme projesi dışında eşlemesi oluşturun. Ardından istediğiniz konuma kaydedebilirsiniz. Yalnızca çözümdeki başka bir konuma dosya kopyalama ve onu kaydetmeye çalışmak başarısızlıkla sonuçlanacaktır.  
  
### <a name="export-the-map-as-an-image-so-you-can-copy-it-into-other-applications-such-as-microsoft-word-or-powerpoint"></a>Microsoft Word veya PowerPoint gibi diğer uygulamalara kopyalamak için harita bir görüntü olarak dışarı aktarma  
  
1.  Kod Haritası araç çubuğunda seçin **paylaşımı**, **e-posta görüntüsü olarak** veya **görüntüsünü kopyalama**.  
  
2.  Görüntüyü başka bir uygulamaya yapıştırın.  
  
### <a name="export-the-map-as-an-xps-file-so-you-can-see-it-in-xml-or-xaml-viewers-like-internet-explorer"></a>Internet Explorer gibi XML ya da XAML görüntüleyiciler görebilmeniz için harita XPS dosyası olarak dışarı aktarma  
  
1.  Kod Haritası araç çubuğunda seçin **paylaşımı**, **e-posta olarak taşınabilir XPS** veya **taşınabilir XPS olarak Kaydet**.  
  
2.  Dosyayı kaydetmek istediğiniz yere göz atın.  
  
3.  Kod Haritası olarak adlandırın. Olduğundan emin olun **farklı türde Kaydet** kutusunu ayarlanmış **XPS dosyaları (\*.xps)**. Seçin **kaydetmek**.  
  
## <a name="what-else-can-i-do"></a>Başka ne yapabilirim?  
  
-   [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)  
  
-   [Hata ayıklarken çağrı yığınında yöntemler eşleştirme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)  
  
-   [Kod haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)  
  
-   [Kod haritalarına göz atma ve bunları yeniden düzenleme](../modeling/browse-and-rearrange-code-maps.md)  
  
-   [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md)
