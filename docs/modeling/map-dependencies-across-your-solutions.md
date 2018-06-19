---
title: Kod haritaları
ms.date: 05/16/2018
ms.topic: conceptual
f1_keywords:
- vs.progression.codemap
- vs.progression.standardgraphsdialog
helpviewer_keywords:
- DGML
- graph documents
- code visualization [Visual Studio]
- dependencies, visualizing
- dependency graphs
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 553e2437abc2d8f498b556300a9266c9e79297f7
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34265571"
---
# <a name="map-dependencies-with-code-maps"></a>Kod haritaları ile bağımlılıkları eşleme

Kod Haritası oluşturarak kodunuz boyunca bağımlılıkları görselleştirebilirsiniz. Kodu nasıl kodu birlikte dosyaları ve kod satırlarını aracılığıyla okumadan uygun gördüğünüz Yardım eşleşir.

![Çözümlerinizi arasında bağımlılıklarını görüntüleme](../modeling/media/codemapsmainintro.png)

Kod haritaları kullanmak için Visual Studio Enterprise veya Professional edition gerekir. Kod Haritası işlevselliği Professional edition'ın Enterprise Edition'da biraz daha daha sınırlıdır.

> [!NOTE]
> Visual Studio Professional kullanan Visual Studio kuruluşta başkalarıyla oluşturulan eşlemeleri paylaşmadan önce tüm öğeleri (örneğin, gizli öğeleri, genişletilmiş grupları ve çapraz grup bağlantılarını) harita üzerinde görünür olduğundan emin olun.

Bu dilde kodu bağımlılıklarını eşleyebilirsiniz:

- Visual C# veya Visual Basic'te bir çözüm ya da derlemeler (*.dll* veya *.exe*)

- Yerel veya yönetilen C veya C++ kodu Visual C++ projelerinde üstbilgi dosyaları (*.h* veya `#include`), ya da ikili dosyalar

- X ++ proje ve Microsoft Dynamics AX for .NET modüllerden yapılan derlemeler

> [!NOTE]
> C# veya Visual Basic dışında projeleri için kod Haritası başlatılıyor veya varolan bir kod Haritası öğeler ekleme için daha az seçenek vardır. Örneğin, C++ projesi metin düzenleyicisinde bir nesneye sağ tıklayın ve bir kod Haritası ekleyin. Ancak, sürükleyin ve tek tek kod öğeleri veya dosyalardan bırakma **Çözüm Gezgini**, **sınıf görünümü**, ve **Nesne Tarayıcısı**.

## <a name="install-code-map-and-live-dependency-validation"></a>Yükleme kod Haritası ve canlı bağımlılık doğrulama

Visual Studio 2017 içinde bir kod haritası oluşturmak için önce yükleme **kod Haritası** ve **Canlı bağımlılık doğrulama** bileşenleri:

1. Açık **Visual Studio yükleyicisi**. Windows Başlat menüsünden ya da Visual Studio içinde seçerek açabilirsiniz **Araçları** > **alma araçları ve özelliklerinin**.

1. Seçin **bileşenleri tek tek** sekmesi.

1. Ekranı aşağı kaydırarak **kod Araçları** bölümünde ve seçin **kod Haritası** ve **Canlı bağımlılık doğrulama**.

   ![Visual Studio yükleyicisinde kod Haritası ve canlı bağımlılık doğrulama bileşenleri](media/modeling-components.png)

1. Seçin **değiştirmek**.

   **Kod Haritası** ve **Canlı bağımlılık doğrulama** bileşenleri başlamak yükleme. Visual Studio'yu kapatın istenebilir.

## <a name="add-a-code-map"></a>Bir kod Eşlemesi Ekle

Bir boş kod Haritası oluşturma ve öğeleri, derleme başvuruları, dosya ve klasörleri de dahil olmak üzere sürükleyin ya da bir kod Haritası tüm ya da çözümünüzü parçası oluşturabilirsiniz.

Bir boş kod Haritası eklemek için:

1. İçinde **Çözüm Gezgini**, üst düzey çözüm düğümünüz için kısayol menüsünü açın. Seçin **ekleme** > **yeni öğe**.

2. İçinde **Yeni Öğe Ekle** iletişim altında **yüklü**, seçin **genel** kategorisi.

3. Seçin **yönlendirilmiş grafik Document(.dgml)** şablonu ve ardından **Ekle**.

   > [!TIP]
   > Bu şablon, burada görmüyorsanız şablon listenin altına kadar kaydırın alfabetik olarak görünmeyebilir.

   Boş bir harita çözümünüzün içinde görünür **çözüm öğeleri** klasör.

Benzer şekilde, yeni bir kod eşleme dosyası, çözümünüz için seçerek eklemeden oluşturabileceğiniz **mimarisi** > **yeni kod Haritası** veya **dosya**  >  **Yeni** > **dosya**.

## <a name="generate-a-code-map-for-your-solution"></a>Çözümünüz için kod Haritası Oluştur

Çözümünüzdeki tüm bağımlılıkları görmek için:

1. Menü çubuğunda seçin **mimarisi** > **çözüm için kod Haritası Oluştur**. En son ne zaman, derlendikten sonra kodunuzu değişmediğinden, seçebileceğiniz **mimarisi** > **olmadan çözüm oluşturmak için kod Haritası Oluştur** yerine.

   ![Bir kod Haritası komutu oluştur](../modeling/media/codemapsarchitecturemenu.png)

   Üst düzey derlemeler ve aralarındaki toplanmış bağlantıları gösteren bir harita oluşturulur. Daha geniş birleşik bağlantı, daha fazla bağımlılıkları temsil eder.

2. Kullanım **gösterge** düğmesini proje türü simgeler (örneğin, Test, Web ve telefon Proje), Listesi'ni göster veya gizle için kod Haritası araç çubuğundaki kod öğeleri (örneğin, sınıfları, yöntemleri ve özellikleri) ve ilişki türleri (örneğin, devralır gelen Uygular ve çağrıları).

   ![Derlemelerin en üst düzey bağımlılık grafiği](../modeling/media/dependencygraph_toplevelassemblies.png)

   Bu örnek bir çözüm çözüm klasörleri içerir (**testleri** ve **bileşenleri**), Test projeleri, Web projeleri ve derlemeler. Varsayılan olarak tüm kapsama ilişkileri görünür *grupları*, genişletme ve daraltma. **Externals** grubu platform bağımlılıklar dahil olmak üzere çözümünüzü dışında her şeyi içerir. Dış derlemeler yalnızca kullanılan öğeleri gösterir. Varsayılan olarak, sistem temel türleri görünmesine eşlemek gizlenir.

3. Eşlemeye detaya gitmek için projeler ve derlemeleri temsil eden Gruplar'ı genişletin. Her şeyi tuşlarına basarak genişletin **CTRL + A** tüm düğümler ve ardından seçme seçmek için **grup**, **genişletme** kısayol menüsünden.

   ![Kod Haritası tüm gruplarında genişletme](../modeling/media/codemapsexpandallgroups.png)

4. Ancak, bu büyük bir çözüm için yararlı olabilir. Aslında, karmaşık çözümleri için bellek sınırlamaları tüm grupları genişletme engelleyebilir. Bunun yerine, tek bir düğümde görmek için onu genişletin. Düğüm üzerinde fare işaretçisini taşıyın ve sonra (aşağı ok) Köşeli Çift Ayraca tıklayın zaman görünür.

   ![Kod Haritası düğümü genişletme](../modeling/media/dependencygraph_containment.png)

   Veya öğeyi seçerek ardından artı tuşuna basarak klavyeyi kullanma (**+**). Kod daha derin düzeylerini keşfetmek için ad alanlarını, türleri ve üyeleri için aynı işlemi yapın.

   > [!TIP]
   > Kodu ile çalışma hakkında daha fazla ayrıntı için kullanarak fare, klavye ve dokunma, bkz: eşlemeleri [göz atın ve haritalar kod sıralama](../modeling/browse-and-rearrange-code-maps.md).

5. Haritayı basitleştirmek ve tek tek parçaları üzerinde odaklanmak için tercih **filtreleri** kod Haritası araç ve yalnızca select düğümleri ve bağlantıları türlerini ilgilendiğiniz. Örneğin, tüm çözüm klasörü ve derleme kapsayıcıları gizleyebilirsiniz.

   ![Kapsayıcıları filtreleyerek haritayı basitleştirmek](../modeling/media/codemapsfilterfoldersassemblies.png)

   Harita, gizleme veya bireysel gruplar ve öğeleri temel çözüm kodunu etkilemeden eşlemesinden kaldırarak da basitleştirebilir.

6. Öğeleri arasında ilişkiler görmek için bunları eşlemesinde seçin. Bağlantı renklerini gösterildiği gibi ilişki türlerini belirtmek **gösterge** bölmesi.

   ![Çözümlerinizi arasında bağımlılıklarını görüntüleme](../modeling/media/codemapsmainintro.png)

   Bu örnekte, çağrıları mor bağlantılardır, başvuruları noktalı bağlantılardır ve açık mavi alan erişimi bağlantılardır. Yeşil bağlantılar devralma olabilir ya da olabilir *toplama bağlantılar* birden fazla ilişki türünü belirtin (veya *kategori*).

   > [!TIP]
   > Yeşil bağlantı görürseniz, bu yalnızca bir devralma ilişkisi anlamına gelmez. Ayrıca yöntem çağrılarını de olabilir, ancak bunlar devralma ilişkisi tarafından gizlenir. Belirli bağlantı türlerini görmek için onay kutularını kullanın **filtreleri** ilginizi olmayan türleri gizlemek için bölmesi.

7. Bir öğe veya bağlantı hakkında daha fazla bilgi almak için bir araç ipucu görünene kadar işaretçiyi üzerine taşıyın. Kod öğesi veya bağlantısını temsil eder kategorileri ayrıntılarını gösterir.

   ![Bir ilişki kategorileri göster](../modeling/media/codemapsshowlinkcatgories.png)

8. Öğeleri ve birleşik bir bağlantı tarafından temsil edilen bağımlılıkları incelemek için ilk bağlantıyı seçin ve ardından kısayol menüsünü açın. Seçin **bağlantılar katkıda bulunan Göster** (veya **yeni kod Haritası bağlantıları katkıda bulunan Göster**). Bu bağlantının her iki ucundaki gruplarını genişletir ve yalnızca öğe ve katılmak bağımlılıkları bağlantıyı gösterir.

9. İçinde harita belirli kısımlarını odaklanmak için ilgi olmayan öğeleri kaldırmak devam edebilirsiniz. Örneğin, sınıf ve üye görünüme incelemek için yalnızca tüm ad alanı düğümlerin filtre **filtreleri** bölmesi.

   ![Sınıf ve üye düzeye ayrıntılara](../modeling/media/dependencygraph_expandedselectedgroups_2012.png)

10. Başka bir odakta bir karmaşık çözüm harita için mevcut bir haritayı gelen seçili öğeleri içeren yeni bir harita oluşturmak için yoludur. Tutun **Ctrl** odaklanmak istediğiniz öğeleri seçerken kısayol menüsünü açın ve seçin **seçimden yeni bir grafik**.

   ![Seçili öğeleri yeni bir kod haritasında Göster](../modeling/media/codemapsshowonnewmap.png)

11. İçeren bağlamı için yeni eşleme devredilir. Çözüm klasörleri ve kullanarak görmesini istemiyorsanız kapsayıcıları Gizle **filtreleri** bölmesi.

   ![Filtre görünümü basitleştirmek için kapsayıcılar](../modeling/media/codemapsexpandnewgroups.png)

12. Gruplar'ı genişletin ve ilişkileri görüntülemek için eşlemesinde öğeleri seçin.

   ![İlişkileri görüntülemek için öğeleri seçin](../modeling/media/codemapsviewnewrelationships.png)

Ayrıca bkz.:

- [Kod haritalarına göz atma ve bunları yeniden düzenleme](../modeling/browse-and-rearrange-code-maps.md)
- [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md)
- Kodunuzda tarafından olası sorunları bulma [çalışan bir çözümleyiciyi](../modeling/find-potential-problems-using-code-map-analyzers.md)

## <a name="view-specific-dependencies-in-a-code-map"></a>Kod Haritası belirli bağımlılıklarını görüntüleme

Bekleyen değişiklikler bazı dosyalarıyla gerçekleştirmek için bir kod gözden geçirme olduğunu varsayalım. Bu değişiklikleri bağımlılıkları görmek için bu dosyaları bir kod Haritası oluşturabilirsiniz.

   ![Belirli bağımlılıkları kod haritasında Göster](../modeling/media/codemapsspecificdependenciesintro.png)

1. İçinde **Çözüm Gezgini**, projeler, derleme başvurularını, klasörleri, dosyaları, türleri veya eşlemek istediğiniz üyeleri seçin.

   ![Eşleştirmek istediğiniz öğeleri seçin](../modeling/media/codemapsselectinsolutionexplorer.png)

1. Üzerinde **Çözüm Gezgini** araç seçin **kod haritasında Göster** ![oluşturma yeni grafik gelen seçili düğümleri düğmesini](../modeling/media/createnewgraphfromselectedbutton.gif). Veya, bir ya da bir öğe grubunu için kısayol menüsünü açın ve seçin **kod haritasında Göster**.

   Öğelerden sürükleyebilirsiniz **Çözüm Gezgini**, **sınıf görünümü**, veya **Nesne Tarayıcısı**, içine bir [yeni](#add-a-code-map) veya var olan kodu eşleyin. Üst hiyerarşi öğeleriniz için eklenecek basılı **Ctrl** öğeleri sürükleyin ya da kullanmak anahtar **dahil üst** varsayılan eylem belirtmek için kod Haritası araç çubuğunda. Ayrıca Dış Visual Studio derleme dosyalarından gibi gelen sürükleyebilirsiniz **Windows Explorer**.

   > [!NOTE]
   > Windows Phone veya Microsoft Store, gibi birden çok uygulama arasında paylaşılan bir projeden öğeleri eklediğinizde öğelerden şu anda etkin uygulama projesi ile harita üzerinde görünür. Bağlamı başka bir uygulama projesi olarak değiştirirseniz ve paylaşılan projeden daha fazla öğe eklerseniz, bu öğeler yeni etkin olan uygulama projesiyle görünür. Eşleme üzerinde bir öğeyle gerçekleştirdiğiniz işlemler, yalnızca aynı bağlamı paylaşılan öğeler için geçerlidir.

3. Harita seçili öğeleri içeren derlemelerini içinde gösterir.

   ![Harita üzerinde gruplar olarak gösterilen seçili öğeler](../modeling/media/codemapsshowitemsfromsolnexplorer.png)

4. Öğeleri keşfetmek için bunları genişletin. Fare işaretçisini öğenin üzerine taşıyın ve sonra görüntülendiğinde Köşeli Çift Ayraca (aşağı ok) simgesine tıklayın.

   ![Kod Haritası düğümü genişletin](../modeling/media/dependencygraph_containment.png)

   Tüm öğeleri genişletmek için bunları seçin kullanarak **Ctrl**+**A**, ardından harita kısayol menüsünü açın ve seçin **grup**  >   **Genişletme**. Ancak, tüm grupları genişletme kullanılamaz bir eşlemesi veya bellek sorunları oluşturursa, bu seçenek kullanılamaz.

5. Öğeler, şu sınıf ve üye düzeye gerekirse ilgilendiğiniz genişletmeye devam edin.

   ![Sınıf ve üye düzeyi gruplar'ı genişletin](../modeling/media/codemapsexpandtoclassandmember.png)

   Kodda, ancak görünmüyor üyeleri haritada görmek için tıklatın **yeniden getirmesi alt** simgesi ![yeniden getirmesi alt simge](../modeling/media/dependencygraph_deletednodesicon.png) bir grup sol üst köşesindeki.

6. Bu harita üzerinde ilgili daha fazla öğe görüntülemek için birini seçin ve seçin **Göster ilgili** kod Haritası araç çubuğunda, sonra eşlemesine eklemek için ilgili öğeler türünü seçin. Alternatif olarak, bir veya daha fazla öğe seçin, kısayol menüsünü açın ve ardından **Göster** eşlemesine eklemek için ilgili öğe türü için seçeneği. Örneğin:

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

    ![Bu üye tarafından adlı yöntemler Göster](../modeling/media/codemapsshowrelatedmethods.png)

7. Harita ilişkiler gösterilmektedir. Bu örnekte, harita çağıran yöntemleri gösterir. `Find` yöntemi ve konumlarını çözüm ya da dışarıdan.

   ![Belirli bağımlılıkları kod haritasında Göster](../modeling/media/codemapsspecificdependenciesintro.png)

8. Haritayı basitleştirmek ve tek tek parçaları üzerinde odaklanmak için tercih **filtreleri** kod Haritası araç ve yalnızca select düğümleri ve bağlantıları türlerini ilgilendiğiniz. Örneğin, çözüm klasörleri, derlemeler ve ad alanlarının görüntülenmesini devre dışı bırakın.

   ![Görüntü basitleştirmek için Filtre bölmesini kullanın](../modeling/media/almcodemapfilterpane.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Video: Visual Studio 2015 kod haritalarını koduyla tasarımdan anlamak](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2015/502)]
- [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)
- [Hata ayıklarken çağrı yığınında yöntemler eşleştirme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
- [Kod haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)
- [Kod haritalarına göz atma ve bunları yeniden düzenleme](../modeling/browse-and-rearrange-code-maps.md)
- [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md)
