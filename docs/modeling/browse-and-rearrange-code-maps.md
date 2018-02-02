---
title: "Gözat ve kod haritalarını yeniden | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.progression.dgmlgraph.layouthelp
- vs.progression.graphdocument
- vs.progression.dgmlgraph.message.notUlt.noexpandgroup
- vs.progression.colorsetpicker
- vs.progression.iconsetpicker
helpviewer_keywords:
- Visual Studio Ultimate, dependency graphs
- code visualization [Visual Studio ALM]
- graph documents, browsing
- Visual Studio ALM, dependency graphs
- code visualization
- Visual Studio ALM, graph documents
- Visual Studio Ultimate, graph documents
- dependency graphs, browsing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ce25077610d285cba59a6d379a68fd3be6c10bcf
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="browse-and-rearrange-code-maps"></a>Kod haritalarına göz atma ve bunları yeniden düzenleme
Okuma ve kendi performansını artırmak kolaylaştırmak için kod haritalarını öğeleri yeniden düzenleyin.  
  
 Bir çözümde arka plandaki kod etkilemeden kod haritalarını özelleştirebilirsiniz. Anahtar kodu öğelerde odaklanmak veya kod hakkında fikir iletişim kurmak istediğinizde kullanışlıdır. Örneğin, ilginç alanları vurgulamak için harita üzerinde kod öğeleri seçin ve bunları filtre, bağlantıların ve kod öğeleri stilini değiştirmek, Gizle veya kod öğeleri silin ve özellikler, kategoriler veya grupları kullanarak kod öğeleri düzenleyin.  
  
 **Gereksinimler**  
  
-   Kod haritaları oluşturmak için Visual Studio Enterprise olması gerekir.  
  
-   Kod haritaları görüntüleyin ve Visual Studio Professional kod eşlemeleri için sınırlı düzenlemeleri yapın.  
  
##  <a name="ManageLargeGraphs"></a>Kod haritaları ile çalışmaya başlama  
 Kod Haritası oluşturma (bkz [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md) daha fazla ayrıntı için). Eşleme oluşturma tamamlamak beklemek istemiyorsanız, **iptal** oluşturma işlemi durdurmak için herhangi bir zamanda bağlantı. Ancak, bunu yaparsanız tüm bağımlılıkları ve bağlantıları ayrıntılarını görmemeniz.  
  
 Harita oluşturduktan sonra kodunuzu gözden geçirme için aşağıdaki ipuçlarını başlayın:  
  
-   Kod doğal bağımlılık kümelerde bakın. Map araç çubuğunda seçin **düzeni**, **hızlı kümeler**![Grafik araç çubuğu düğmesi hızlı kümeler](../modeling/media/quickclustersicon.gif "QuickClustersIcon"). Bkz: [harita düzenini değiştirme](#Selecting).  
  
     ![Bağımlılık grafiğinin &#45; Hızlı kümeler düzenine](../modeling/media/dependencygraph_quickclusters.png "DependencyGraph_QuickClusters")  
  
-   Harita küçük alanlarına, ilgili düğümleri gruplayarak düzenleyebilirsiniz. Otomatik olarak görünür yalnızca intergroup bağımlılıklarının görmek için bu gruplara daraltın. Bkz: [Grup düğümleri](#OrganizeGroups).  
  
-   Haritayı basitleştirmek ve düğümler veya ilgilendiğiniz bağlantılar türlerinin odaklanmak için filtreleri kullanın. Bkz: [filtre düğümleri ve bağlantıları](#FilterNodes).  
  
-   Büyük eşlemeleri performansını en üst düzeye çıkarın. Bkz: [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md) daha fazla bilgi için. Örneğin, Aç **Atla yapı** öğeleri harita üzerinde güncelleştirdiğinizde, Visual Studio çözümünüzü yeniden değil için harita araç çubuğunda.  
  
##  <a name="Selecting"></a>Harita düzenini değiştirme  
  
|**Hedef**|**Bu adımları uygulayın**|  
|------------|-----------------------------|  
|Belirli bir yönde tüm harita bağımlılık akışını düzenleyin. Bu kodda mimari katmanları görmenize yardımcı olabilir.|Map araç çubuğunda seçin **düzeni**ve ardından:<br /><br /> -   **Yukarıdan aşağıya doğru** ![alt grafik düğmesi yukarıdan](../modeling/media/topbottomgraphbutton.gif "TopBottomGraphButton")<br />-   **Aşağıdan yukarıya** ![üst Grafik düğmesini altına](../modeling/media/bottomtopgraphbutton.gif "BottomTopGraphButton")<br />-   **Soldan sağa** ![sağ düzeni düğmesini sol](../modeling/media/leftrightgraphbutton.gif "LeftRightGraphButton")<br />-   **Sağdan sola** ![sağdan sola Grafik düğmesini](../modeling/media/rightleftgraphbutton.gif "RightLeftGraphButton")|  
|Kümelerin merkezinde en bağımlı düğümleri ve bu kümelerin dışına en az bağımlı düğümleri koduyla doğal bağımlılık kümelerde bakın.|Map araç çubuğunda seçin **düzeni**ve ardından **hızlı kümeler**![Grafik araç çubuğu düğmesi hızlı kümeler](../modeling/media/quickclustersicon.gif "QuickClustersIcon").|  
|Harita üzerinde bir veya daha fazla düğüm seçin.|Bir düğümde seçmek için tıklatın. Seçin veya birden fazla düğüm seçimini kaldırmak için tutun **CTRL** tıklarken.<br /><br /> Klavye: basın **sekmesini** veya bir düğüm ve tuşuna noktalı odak dikdörtgeni taşımak için ok tuşlarını kullanın **alanı** seçin. Tuşuna **CTRL** + **alanı** çoklu seçim için veya düğümlerin seçimini kaldırın.|  
|Belirli düğümler haritada hareket ettirin.|Bunları taşımak için düğümleri sürükleyin. Diğer düğümleri ve bağlantıları düğümleri sürükleyin göz önünden basılı taşımak için **SHIFT** anahtarı.<br /><br /> Klavye: tutun **CTRL** ve OK tuşlarına basın.|  
|Bir grup diğer düğümlerin bağımsız olarak ve harita üzerinde gruplar içinde düzenini değiştirin.|Bir düğüm seçin ve kısayol menüsünü açın. Seçin **düzeni** ve bir düzen stili seçin.<br /><br /> - veya -<br /><br /> Bir düğüm seçin ve alt düğümleri göstermek için genişletin. Grup açılır araç çubuğunu göster ve açmak için düğümü başlığını tıklatarak **Grup düzen stilini değiştirme**![bağımlılık grafiğinin &#45;Grup araç &#45; Düzen](../modeling/media/dependencygraph_grouptoolbar.gif "DependencyGraph_ GroupToolbar") listesi. Ağaç düzenlerden birini seçin **hızlı kümeler**, veya **liste görünümü** (hangi düzenler grubun içeriğini bir liste olarak).<br /><br /> Bkz: [Grup düğümleri](#OrganizeGroups) daha fazla ayrıntı için.|  
|Harita bir eylemi geri al.|Tuşuna **CTRL** + **Z** veya Visual Studio'yu kullanma **geri** komutu.|  
  
##  <a name="Explore"></a>Harita Gözat  
  
|**Hedef**|**Bu adımları uygulayın**|  
|------------|-----------------------------|  
|Harita tarayın.|Harita fareyle herhangi bir yönde sürükleyin.<br /><br /> - veya -<br /><br /> Tutun **SHIFT** ve yatay olarak kaydırmak için fare tekerleği döndürün. Tutun **SHIFT** + **CTRL** ve yatay olarak kaydırmak için fare tekerleği döndürün.|  
|Yakınlaştırma veya harita dışında.|Fare tekerleği döndürün.<br /><br /> - veya -<br /><br /> Kullanım **yakınlaştırma** kod Haritası araç çubuğundaki aşağı açılan listesinde.<br /><br /> - veya -<br /><br /> Klavye kısayollarını kullanın. Yakınlaştırmak için basın **CTRL + SHIFT +.** (süre). Uzaklaştırmak için basın **CTRL + SHIFT +,** (virgül).|  
|Belirli bir alanında fare kullanarak yakınlaştırma.|İlgilendiğiniz o alanı etrafında bir dikdörtgen çizerken sağ fare düğmesini basılı tutun.|  
|Yeniden boyutlandırma ve onun penceresi eşlemesinde sığmayacak.|Seçin **sığacak kadar Yaklaştır** gelen **yakınlaştırma** kod Haritası araç çubuğundaki listesinde.<br /><br /> - veya -<br /><br /> Tıklatın **uyacak şekilde yakınlaştırma** simgesi ![map araç çubuğundaki Yakınlaştır simgesi](../modeling/media/almcodemapzoomicon.png "ALMCodeMapZoomIcon") kod Haritası araç çubuğunda. Klavye: basın **CTRL + 0** (sıfır).|  
|Bir düğüm haritada sunucu adına göre bulur. **İpucu:** bu yalnızca öğeler için harita üzerinde çalışır. Çözümünüzdeki ancak harita öğeleri bulmak için bunları Bul **Çözüm Gezgini**ve ardından bunları eşlemeye sürükleyin. (Seçiminizi sürükleyin ya da Çözüm Gezgini araç çubuğunda tıklatın **kod haritasında Göster**).|1.  Seçin **Bul** simgesi ![map araç çubuğunda Bul simgesini](../modeling/media/almcodemapfindicon.png "ALMCodeMapFindIcon") kod Haritası araç çubuğunda (klavye: basın **CTRL + F**) göstermek için Arama kutusuna sağ üst köşesinde harita.<br />2.  Öğe adı yazıp tuşuna **dönmek** veya "Büyüteç" simgesine tıklayın. Aramanızla eşleşen ilk öğe haritada seçilen görünür.<br />3.  Aramanızı özelleştirmek için açılır listeyi açın ve bir arama seçeneği belirleyin. Seçenekler şunlardır: **Sonrakini Bul**, **Öncekini Bul**, ve **Tümünü Seç**. Arama metin kutusuna yanındaki karşılık gelen bir düğme'ye tıklayın.<br />     ![Arama Seçenekleri açılan &#45; aşağı listesi](../modeling/media/almcodemapssearchdropdown.png "ALMCodeMapsSearchDropDown")<br />     Alternatif olarak, klavye kullanın: basın **F3** sonraki eşleşen düğümü seçmek için veya **SHIFT + F3** önceki eşleşen düğümü seçin.<br />4.  Arama metin kutusuna aşağıda simgelere tıklayarak arama terimleri nasıl işleneceğini belirtebilirsiniz seçeneklerinden herhangi birini seçin.<br />     ![Arama eşleşme seçenekleri](../modeling/media/almcodemapssearchmatchicons.png "ALMCodeMapsSearchMatchIcons")<br />     Seçenekler şunlardır soldan sağa, hassas eşleşen durumda, yalnızca tam sözcükleri eşleştirmeye, .NET normal ifade sözdizimini kullanın, otomatik olarak eşleşmeleri göstermek amacıyla grupları genişletmek kapalı öğelerine. **Önemli:** yalnızca bu gruplara daha önce genişlettiyseniz eşleşmeleri daraltılmış grupları bulmak için arama kutusunu kullanın. Bu eşleşmeler bulmak ve kendi üst grupları otomatik olarak genişletmek için arama kutusunun altında bu seçeneği seçin.|  
|Tüm seçili düğümleri seçin.|Seçili düğümlerin kısayol menüsünü açın. Seçin **seçin**, **Çevir seçimi**.|  
|Seçili olanlara bağlantı ek düğümleri seçin.|Seçili düğümlerin kısayol menüsünü açın. Seçin **seçin** ve bunlardan biri:<br /><br /> -Seçili düğüme doğrudan bağlantı ek düğümleri seçmek için Seç **gelen bağımlılıkları**.<br />-Bağlantı ek düğümleri doğrudan seçili düğümden seçmek için Seç **giden bağımlılıkları**.<br />-Bağlantı doğrudan ve seçili düğümden ek düğümleri seçmek için Seç **her ikisi de**.<br />-Seçili düğümün gelen ve giden bağlantı tüm düğümleri seçmek için Seç **bağlı Subgraph**.<br />-Tüm alt öğeleri Seçili düğümün seçmek istediğinizde **alt**.|  
  
##  <a name="FilterNodes"></a>Filtre düğümleri ve bağlantıları  
  
|**Hedef**|**Bu adımları uygulayın**|  
|------------|-----------------------------|  
|Gösterebilir veya Filtre bölmesini gizleyebilirsiniz.|Seçin **filtreleri** kod Haritası araç çubuğunda. Filtre bölmesini varsayılan olarak, varsayılan olarak Çözüm Gezgini penceresinde sekmeli sayfası olarak görüntülenir.|  
|Harita üzerinde gösterilen düğüm türlerini filtreleyin.|Ayarlayın veya içinde onay kutularını temizleyin **kod öğeleri** Filtre bölmesini listesinde.|  
|Harita üzerinde gösterilen bağlantı türlerini filtreleyin.|Ayarlayın veya içinde onay kutularını temizleyin **ilişkileri** Filtre bölmesini listesinde.|  
|Gösterip Test projesi düğümlerine harita üzerinde gizleyebilirsiniz.|Ayarlama veya kaldırma **Test varlıklar** onay kutusu **çeşitli** Filtre bölmesini listesinde.|  
  
 Harita göstergesi panelinde gösterilen simgeler listede yaptığınız ayarları yansıtır. Gösterge panelini göstermek veya gizlemek için tıklatın **gösterge** kod Haritası araç çubuğunda.  
  
##  <a name="Inspect"></a>Düğümleri ve bağlantıları inceleyin  
 Kod haritaları bu tür bir bağlantı gösterir:  
  
-   Tek bir bağlantı iki düğüm arasında tek bir ilişkiyi temsil eder.  
  
-   Gruplar arası bağlantı farklı gruplardaki iki düğüm arasında bir ilişki temsil eder.  
  
-   Birleşik bir bağlantıyı iki grupları arasında aynı yönde işaret eden tüm ilişkiler temsil eder.  
  
> [!TIP]
>  Varsayılan olarak, yalnızca seçili düğümler için çapraz grup bağlantılarını eşlemesini gösterir. Gruplar arasında toplanmış bağlantıları göstermek veya gizlemek için bu davranışı değiştirmek için tıklatın. **düzeni** kodu eşleme araç ve seçin **Gelişmiş**, ardından **tüm çapraz grup bağlantılarını göster** veya **Tüm çapraz grup bağlantılarını Gizle**. Bkz: [Gizle veya Göster düğümleri ve bağlantıları](#HidingShowing) daha fazla ayrıntı için.  
  
|**Hedef**|**Bu adımları uygulayın**|  
|------------|-----------------------------|  
|Bir düğüme veya bağlantıya hakkında daha fazla bilgi bakın.|Düğüm üzerinde fare işaretçisini veya ipucu görünene kadar bağlayın.<br /><br /> Toplanan bağlantı için araç ipucu temsil ettiği tek tek bağımlılıkları listeler.<br /><br /> - veya -<br /><br /> Düğüm veya bağlantı için kısayol menüsünü açın. Seçin **Düzenle**, **özellikleri**.|  
|Gösterin veya bir grup içeriğini gizleyin.|-Bir grubu genişletmek için düğümü için kısayol menüsünü açın ve seçin **grup**, **genişletme**.<br />     - veya -<br />     Köşeli Çift Ayraca (aşağı ok) düğmesini görünene kadar düğüm üzerinde fare işaretçisini taşıyın. Grubu genişletmek için bu düğmeye tıklayın. Klavye: seçilen grubu genişletmek veya daraltmak basın **artı** anahtarı (**+**) veya **eksi** anahtarı ( **-** ).<br />-Bir grubu daraltmak için düğümü için kısayol menüsünü açın ve seçin **grup**, **Daralt**.<br />     - veya -<br />     Köşeli Çift Ayraca (yukarı ok) düğmesini görünene kadar fare işaretçisi bir grup üzerine taşıyın. Grubu daraltmak için bu düğmeye tıklayın.<br />-Tüm grupları genişletmek için basın **CTRL** + **A** tüm düğümleri seçin. Harita kısayol menüsünü açın ve seçin **grup**, **genişletme**. **Not:** tüm grupları genişletme kullanılamaz bir eşlemesi veya bellek sorunları oluşturursa, bu komutu kullanılamaz. Yalnızca ilgilendiğiniz ayrıntı düzeyi için harita genişletin önerilir.<br />-Tüm grupları daraltmak için harita veya bir düğüm için kısayol menüsünü açın. Seçin **grup**, **Tümünü Daralt**.|  
|Ad alanı, tür veya üye için kod tanımına bakın.|Düğümü için kısayol menüsünü açın ve seçin **Tanıma Git**.<br /><br /> veya<br /><br /> Düğüme çift tıklayın. Genişletilmiş grupları için Grup başlığındaki çift tıklayın.<br /><br /> veya<br /><br /> Düğümü seçip tuşuna **F12**.<br /><br /> Örneğin:<br /><br /> -Tek bir sınıf içeren bir ad alanı için sınıf için kod dosyası o sınıfın tanımını göstermek için açılır. Diğer durumlarda **Bul simgesi sonuçlarınızı** penceresi kod dosyalarının listesini gösterir. **Not:** bir Visual Basic ad bu görevi gerçekleştirirken ad alanının arkasındaki kod dosya açılmaz. Visual Basic ad alanı dahil seçili düğüm bir grubu bu görevi gerçekleştirirken de bu sorun oluşur. Bu sorunu çözmek için el ile ad arkasındaki kod dosyasına göz atın veya ad alanından seçiminizi düğümünü atlayın.<br />-Bir sınıf veya bir parçalı sınıf için sınıf tanımını göstermek için bu sınıf için kod dosyası açılır.<br />-İçin bir yöntem, yöntem tanımı göstermek için üst sınıfı için kod dosyası açılır.|  
|Bağımlılıklar ve birleşik bir bağlantıya katıldığını öğeleri inceleyin.|İlgilendiğiniz ve kısayol menüsünü açmak için yaptığınız seçimi bağlantıları seçin. Seçin **bağlantılar katkıda bulunan Göster** veya **yeni kod Haritası bağlantıları katkıda bulunan Göster**.<br /><br /> Visual Studio, bağlantının her iki ucunda da grupları genişletir ve yalnızca bağlantıya katılan öğe ve bağımlılıkları gösterir. **Not:** kısmi gruplardaki öğeleri arasındaki bağımlılıkları incelediğinizde, bu davranış görebilirsiniz: <ul><li>Bu bağlantılar hala mevcut olsa bile, inceleme katılmak yok öğelerine bağlantılar eşlemesinden kaybolur.</li><li>Kısmi grubunda bir öğeyi bağlantısını inceleyin ve daha sonra aynı öğeye farklı bir bağlantı inceleyin varsayalım. İkinci, inceleme sırasında yalnızca ilk İnceleme öğelerinden hedef kısmi grubu gösterir. Bağlantılar ve alamadık, ilk İnceleme katılmak ancak, ikinci İnceleme katılmak hedef öğelerin görünmüyor.</li></ul> Bir gruptan öğeleri eksik görmek için seçin **yeniden getirmesi alt**![yeniden getirmesi alt simge](../modeling/media/dependencygraph_deletednodesicon.png "DependencyGraph_DeletedNodesIcon") (hangi gösteren tüm üyeleri bir Grup görünür haritada). Eylemleriniz geri almayı deneyebilirsiniz (klavye: basın **CTRL + Z**) ve yeni bir eşleme bağımlılıkları inceleyin.|  
|Farklı gruplarındaki birden çok düğüm arasında bağımlılıkları inceleyin.|Tüm alt öğeleri görebilmeniz için gruplar'ı genişletin. Bunların alt öğeleri de dahil olmak üzere sizi ilgilendiren tüm düğümleri seçin. Harita seçilen düğümler arasında çapraz grup bağlantılarını gösterir.<br /><br /> Bir gruptaki tüm düğümleri seçmek için basılı **SHIFT** ve o grup etrafında bir dikdörtgen çizerken sol fare düğmesini. Bir harita tüm düğümleri seçmek için basın **CTRL**+**A**. **İpucu:** çapraz grup bağlantılarını her zaman, görüntülemeyi **düzeni** map araç çubuğunda **Gelişmiş**, **tüm çapraz grup bağlantılarını göster**.|  
|Bir düğüme veya bağlantıya başvuran öğeleri görüntüleyin.|Düğümü için kısayol menüsünü açın ve seçin **tüm başvuruları Bul**. **Not:** bu yalnızca geçerlidir `Reference` özniteliği düğüme veya bağlantıya için ayarlanmış haritanın .dgml dosyasındaki. Düğümlerden veya bağlantılardan öğelere başvurular eklemek için bkz: [Özelleştir kod eşlemeleri DGML dosyalarını düzenleyerek](../modeling/customize-code-maps-by-editing-the-dgml-files.md).|  
  
##  <a name="HidingShowing"></a>Düğümleri ve bağlantıları gösterme veya gizleme  
 Düğümlerin gizlenmesi, düzen algoritmasına katılmalarını engeller. Varsayılan olarak, çapraz grup bağlantıları gizlidir. Çapraz grup bağlantıları, düğümleri gruplar arasında bağlayan tek bağlantılardır. Gruplar daraltıldığında harita tüm çapraz grup bağlantılarını gruplar arasındaki tek bağlantılar içine toplar. Bir grubu genişlettiğinizde veya grup içindeki düğümleri seçtiğinizde, çapraz grup bağlantıları görünür ve o gruptaki bağımlılıkları gösterir.  
  
> [!CAUTION]
>  Visual Studio Enterprise Visual Studio Professional kullananlar ile oluşturulmuş bir harita paylaşmadan önce herhangi bir düğüm veya başkalarının görmesini istediğiniz çapraz grup bağlantıları göstermek emin olun. Aksi takdirde, bu kullanıcılar bu öğelerin gizliliğini kaldıramayacaktır.  
  
### <a name="to-hide-or-show-nodes"></a>Düğümleri gizlemek veya göstermek için  
  
|**Hedef**|**Bu adımları uygulayın**|  
|------------|-----------------------------|  
|Seçili düğümleri gizleyin.|1.  Gizlemek istediğiniz düğümleri seçin.<br />2.  Harita veya seçili düğümler için kısayol menüsünü açın. Seçin **seçin**, **seçili Gizle**.|  
|Seçili olmayan düğümleri gizleyin.|1.  Görünür kalmasını istediğiniz düğümleri seçin.<br />2.  Harita veya seçili düğümler için kısayol menüsünü açın. Seçin **seçin**, **seçilmemiş Gizle**.|  
|Gizli düğümleri gösterin.|-Bir grup içindeki tüm gizli düğümleri göstermek için öncelikle Grup genişletilmiş emin olun. Kısayol menüsünü açın ve seçin **seçin**, **Göster alt**.<br />     - veya -<br />     ' I tıklatın **Göster alt**![Göster alt simge](../modeling/media/dependencygraph_filtericon_hiddennodes.gif "DependencyGraph_FilterIcon_HiddenNodes") (Bu, yalnızca görünür olduğunda grup sol üst köşesindeki simgesi Gizli alt düğümleri yoktur).<br />-Tüm gizli düğümleri göstermek için harita veya bir düğüm için kısayol menüsünü açın ve seçin **seçin**, **Tümünü Göster**.|  
  
### <a name="to-hide-or-show-links"></a>Bağlantıları göstermek veya gizlemek için  
  
|**Hedef**|**Map araç çubuğunda düzenini seçin ve Gelişmiş seçin**|  
|------------|----------------------------------------------------------------------|  
|Gruplar arası bağlantılar her zaman göster.|**Tüm çapraz grup bağlantıları göstermek**. Bu, gruplar arasında toplanmış bağlantıları gizler.|  
|Gruplar arası bağlantılar her zaman gizleyin.|**Tüm çapraz grup bağlantılarını Gizle**|  
|Yalnızca seçili düğümler için çapraz grup bağlantılarını gösterir.|**Seçilen düğümler üzerinde çapraz grup bağlantılarını göster**|  
|Tüm bağlantılar gizleyin.|**Tüm bağlantıları gizle**. Bağlantıları yeniden göstermek için yukarıda listelenen seçeneklerden birini seçin.|  
  
##  <a name="OrganizeGroups"></a>Düğümleri gruplandırın.  
  
|**Hedef**|**Bu adımları uygulayın**|  
|------------|-----------------------------|  
|Kapsayıcı düğümleri Grup düğümleri veya yaprak düğümlerin olarak göster.|Kapsayıcı düğümleri yaprak düğümlerin olarak göstermek için: düğümleri seçin, seçiminiz için kısayol menüsünü açın ve **grup**, **yaprak Dönüştür**.<br /><br /> Kapsayıcı düğümleri Grup düğümleri olarak göstermek için: düğümleri seçin, seçiminiz için kısayol menüsünü açın ve **grup**, **gruba Dönüştür**.|  
|Bir grup içindeki düzenini değiştirin.|Grup seçin, kısayol menüsünü açın, **düzeni**, istediğiniz düzen stili seçin.<br /><br /> - veya -<br /><br /> 1.  Grubu seçin ve genişletilmiş emin olun.<br />2.  Grup başlığını tekrar tıklatın ve Grup araç çubuğu görüntülenir.<br />     ![Bağımlılık grafiğinin &#45; Grup araç](../modeling/media/dependencygraph_group.png "DependencyGraph_Group")<br />3.  Açık **Grup düzen stilini değiştirme** listesi ![bağımlılık grafiğinin &#45;Grup araç &#45; Düzen](../modeling/media/dependencygraph_grouptoolbar.gif "DependencyGraph_GroupToolbar") ve düzenini seçin istediğiniz stili.<br /><br /> **Liste görünümü** grubun üyeleri listeye yeniden düzenler. **Grafik varsayılan** Grup düzeni harita varsayılan düzene sıfırlar. Diğer seçenekler için bkz: [harita düzenini değiştirme](#Selecting).|  
|Bir düğüm bir gruba ekleyin.|Düğümü gruba sürükleyin.<br /><br /> Düğüm sürükleme, Visual Studio düğüme taşıdığınızdan emin göstermek için bir gösterge görüntüler.<br /><br /> Düğümleri grubun dışına da sürükleyebilirsiniz.|  
|Bir düğüm bir grubu olmayan düğümüne ekleyin.|Düğümü hedef düğüme sürükleyin. Düğüm ekleyerek bir gruba herhangi bir hedef düğümü dönüştürebilirsiniz.|  
|Seçili düğümleri gruplandırın.|1.  Gruplandırmak istediğiniz düğümleri seçin. Açılır bir araç çubuğu seçtiğiniz son düğümü görünür.<br />     ![Bağımlılık Grafik araç çubuğu](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")<br />2.  Araç çubuğunda, dördüncü simgesini seçin **grup seçili düğümleri** (düğümünü genişlettiyseniz beş dört simgeleri yerine sahip olacaktır). Tuşuna basın ve yeni grubun adını yazın **iade**.<br />     - veya -<br />     Grup ve seçiminizi için kısayol menüsünü açmak istediğiniz düğümleri seçin. Seçin **grup**, **üst Grup Ekle**, yeni Grup ve ENTER tuşuna basın yazın **iade**.<br /><br /> Bir grubu yeniden adlandırabilirsiniz. Grup için kısayol menüsünü açın ve seçin **Düzenle**, **özellikleri** Visual Studio Özellikler penceresini açın. İçinde **etiketi** özelliği, grubu gerektiği gibi yeniden adlandırın.|  
|Grupları kaldırın.|Kaldırmak istediğiniz grup veya grupları seçin. Seçiminiz için kısayol menüsünü açın ve seçin **grup**, **grubu Kaldır**.|  
|Düğüm, kendi üst gruptan kaldırın.|Taşımak istediğiniz düğümleri seçin. Seçiminiz için kısayol menüsünü açın ve seçin **grup**, **Üst Gruptan Kaldır**. Hiçbir iki üst grubunuz varsa bu düğümler yukarı kendi iki üst veya çok dışında grubu kaldırır.<br /><br /> - veya -<br /><br /> Düğümleri seçin ve grubun dışında sürükleyin.|  
  
##  <a name="AddRemoveNodesLinks"></a>Ekleme, kaldırma veya düğümler, bağlantılar ve açıklamaları yeniden adlandırma  
 Detaya için veya haritayı basitleştirmek için bir harita üzerinde daha fazla veya daha az öğeleri görüntüleyebilirsiniz. Öğeleri yeniden adlandırmanız ve öğeleri yorumlar ekleyin.  
  
> [!CAUTION]
>  Visual Studio Enterprise Visual Professional kullananlar ile kullanılarak oluşturulmuş bir harita paylaşmadan önce başkalarının görmesini istediğiniz herhangi bir kod öğe harita üzerinde görünür olduğundan emin olun. Aksi takdirde, bu kullanıcıların silinen kod öğeleri almak mümkün olmayacaktır.  
  
### <a name="add-a-node-for-a-code-element"></a>Kod öğesi için bir düğüm ekleme  
  
|**Hedef**|**Bu adımları uygulayın**|  
|------------|-----------------------------|  
|Yeni bir genel düğüm geçerli fare işaretçisini konumda ekleyin.|1.  Fare işaretçisini basın ve yeni bir kod öğesi yerleştirmek istediğiniz yere haritada taşıyın **Ekle**.<br />     - veya -<br />     Harita kısayol menüsünü açın ve seçin **Düzenle**, **Ekle**, **genel düğüm**.<br />2.  Tuşuna basın ve yeni bir düğüm için bir ad yazın **iade**.|  
|Kod öğesi düğümü belirli bir türdeki geçerli fare işaretçisini konumda ekleyin.|1.  Fare işaretçisini yeni bir kod öğesi koyun ve eşleme için kısayol menüsünü açmak istediğiniz yere haritada taşıyın.<br />2.  Seçin **Düzenle**, **Ekle**ve istediğiniz düğümü seçin.<br />3.  Tuşuna basın ve yeni bir düğüm için bir ad yazın **iade**.|  
|Genel veya özel türde bir kod öğesi düğümü bir gruba ekleyin.|1.  Grubu düğümünü seçin ve kısayol menüsünü açın.<br />2.  Seçin **Düzenle**, **Ekle**ve istediğiniz düğümü seçin.<br />3.  Tuşuna basın ve yeni bir düğüm için bir ad yazın **iade**.|  
|Aynı türde yeni bir düğüm eklemek ve varolan bir düğümü, bağlanır.|1.  Kod öğesini seçin. Açılır bir araç çubuğu görünür.<br />     ![Bağımlılık Grafik araç çubuğu](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")<br />2.  Araç çubuğunda, ikinci simgesini seçin **bu düğümde aynı kategoride ile bir düğüm oluşturabilirsiniz ve yeni bir bağlantı ekleyin**.<br />3.  Sol fare düğmesini tıklatıp yeni bir kod öğesi put harita üzerinde bir yer seçin.<br />4.  Tuşuna basın ve yeni bir düğüm için bir ad yazın **iade**.|  
|Bağlı yeni bir genel düğümü odağa sahip varolan bir kod öğeyi ekleyin.|1.  Klavyeyi kullanarak basın **sekmesini** bağlantı için kod (noktalı dikdörtgen) odaktaki öğeyi kadar.<br />2.  Tuşuna **Alt**+**Ekle**.<br />3.  Tuşuna basın ve yeni bir düğüm için bir ad yazın **iade**.|  
|Odağa sahip varolan bir kod öğesi bağlantıları yeni bir genel düğümünü ekleyin.|1.  Klavyeyi kullanarak basın **sekmesini** bağlamak için kod (noktalı dikdörtgen) odaktaki öğeyi kadar.<br />2.  Tuşuna **Alt**+**Shift**+**Ekle**.<br />3.  Tuşuna basın ve yeni bir düğüm için bir ad yazın **iade**.|  
  
|**Kod öğeleri eklemek için**|**Bu adımları uygulayın**|  
|----------------------------------|-----------------------------|  
|Çözümdeki kod öğeleri.|1.  Kod öğesi bulunamıyor **Çözüm Gezgini**. Kullanım **Çözüm Gezgini** arama kutusu veya çözüm göz atın. **İpucu:** bir tür veya üye bağımlı kod öğeleri bulmak için tür veya üye için kısayol menüsünü açın **Çözüm Gezgini**. Sizi ilgilendiren ilişkiyi seçin. **Çözüm Gezgini** yalnızca belirtilen bağımlılıkları olan kod öğeleri gösterir.<br />2.  Harita yüzeye ilgilendiren kod öğeleri sürükleyin. Sınıf Görünümü veya Nesne Tarayıcısı ayrıca kod öğeleri sürükleyebilirsiniz.<br />     - veya -<br />     İçinde **Çözüm Gezgini**, eşlemek istediğiniz kod öğeleri seçin. Ardından **Çözüm Gezgini** araç tıklatın **kod haritasında Göster**.<br /><br /> Varsayılan olarak, yeni kod öğeleri için üst kapsayıcı hiyerarşisi haritada gösterilir. Kullanım **dahil üst** bu davranışı değiştirmek için kod Haritası araç çubuğunda. Devre dışı bırakıldığında, yalnızca kod öğenin kendisinin eşlemeye eklenir. Bu davranış tek sürükleme için ters çevirmek ve eylem, basılı tutarak bırakma için **CTRL** tutarak eşlemeye kod öğeleri sürükleyin anahtar.<br /><br /> Visual Studio seçiminizde en üst düzey kod öğeleri için kod öğeleri ekler. Kod öğesi diğer kod öğeleri içerip içermediğini görmek için böylece Köşeli Çift Ayraca (aşağı ok) görünür fare işaretçisini code öğesi üzerine taşıyın. Kod öğesi genişletmek için köşeli çift Ayraca seçin. Tüm kod öğeleri genişletmek için basın **CTRL**+**A** tüm öğeleri seçmek için harita kısayol menüsünü açın ve seçin **grup**, **genişletme** . Tüm grupları genişletme kullanılamaz bir harita oluşturmak ya da bellek sorunları yetersizliği neden bu komutu kullanılamaz.|  
|Kod öğeleri harita üzerinde ilgili kod öğeleri.|Tıklatın **Göster ilgili** kod Haritası araç çubuğunda düğmesini ve ilgili öğeler ilgilendiğiniz türünü seçin.<br /><br /> - veya -<br /><br /> Kod öğesi için kısayol menüsünü açın. Aşağıdakilerden birini seçin **göster...**  ilginizi çeken ilişki türüne bağlı olarak menüsündeki öğeler. Örneğin, geçerli öğesine başvuruyor, sınıflar, yöntemini arayanlar ve içeren sınıfları, ad alanları ve derlemeler için temel ve türetilen türlerin, geçerli öğenin başvuran öğeleri öğeleri görebilirsiniz.<br /><br /> Daha fazla ayrıntı için bkz: [bu konuda](../modeling/map-dependencies-across-your-solutions.md).|  
|Derlenmiş .NET derlemelerini (.dll veya .exe) veya ikili dosyaları.|Derlemeleri veya ikili dosyaları dışında Visual Studio'dan haritaya sürükleyin.<br /><br /> Aynı kullanıcı erişim denetimi (UAC) izinleri düzeyinde yalnızca ve Visual Studio çalıştırıyorsanız, Windows Gezgini veya dosya Gezgini'nden sürükleyebilirsiniz. Örneğin, UAC açık olduğundan ve yönetici olarak Visual Studio çalıştırıyorsanız, Windows Gezgini veya dosya Gezgini'ni sürükleme işlemi engeller.|  
  
###  <a name="AddNodes"></a>   
##### <a name="add-a-link-between-existing-code-elements"></a>Varolan kod öğeleri arasında bir bağlantı Ekle  
  
1.  Kaynak kodu öğesini seçin. Kod öğesi bir araç çubuğu görüntülenir.  
  
     ![Bağımlılık Grafik araç çubuğu](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")  
  
2.  Araç çubuğunda, ilk simgesini seçin **oluşturma hakkında İleri'yi tıklatın ve ever düğüme bu düğümden yeni bağlantı**.  
  
3.  Hedef kod öğesini seçin. İki kod öğeleri arasında bir bağlantı görüntülenir.  
  
 \-veya -  
  
1.  Harita üzerinde kaynak kodu öğesini seçin.  
  
2.  Yüklü bir fare varsa, fare işaretçisini harita sınırları dışına taşıyın.  
  
3.  Kod öğenin kısayol menüsünü açın ve seçin **Düzenle**, **Ekle**, **genel bağlantı**.  
  
4.  İçin sekme ve bağlantının hedef kod öğesini seçin.  
  
5.  Tuşuna **iade**.  
  
###  <a name="AddComments"></a>   
##### <a name="add-a-comment-to-an-existing-node-on-the-map"></a>Harita üzerinde varolan bir düğümü için bir açıklama ekleyin  
  
1.  Kod öğesini seçin. Araç çubuğu görünür.  
  
     ![Bağımlılık Grafik araç çubuğu](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")  
  
2.  Araç çubuğunda, üçüncü simgeyi seçin **Seçili düğümün yeni bir bağlantı içeren yeni bir açıklama düğümü oluşturma**.  
  
     \-veya -  
  
     Kod öğesi için kısayol menüsünü açın ve seçin **Düzenle**, **yeni yorum**.  
  
3.  Açıklamalarınızı yazın. Yeni bir satıra yazın için basın **SHIFT** + **iade**.  
  
##### <a name="add-a-comment-to-the-map-itself"></a>Eşleme için bir açıklama ekleyin  
  
1.  Harita kısayol menüsünü açın ve seçin **Düzenle**, **yeni yorum**.  
  
2.  Açıklamalarınızı yazın. Yeni bir satıra yazın için basın **SHIFT** + **iade**.  
  
###  <a name="RenameNodes"></a>   
##### <a name="rename-a-code-element-or-link"></a>Kod öğesi veya bağlantısı yeniden adlandırma  
  
1.  Kod öğesi veya yeniden adlandırmak istediğiniz bağlantı seçin.  
  
2.  Tuşuna **F2**, veya kısayol menüsünü açın ve seçin **Düzenle**, **yeniden adlandırma**.  
  
3.  Haritada düzenleme kutusu belirdiğinde code öğesi veya bağlantısını yeniden adlandırın.  
  
     \-veya -  
  
4.  Kısayol menüsünü açın ve seçin **Düzenle**, **özellikleri**.  
  
5.  Düzen **etiket** Visual Studio özellikleri penceresinde özelliği.  
  
##### <a name="remove-a-code-element-or-link-from-the-map"></a>Kod öğesi veya bağlantı eşlemesinden Kaldır  
  
1.  Kod öğesi veya bağlantı tuşuna seçip **silmek** anahtarı.  
  
     \-veya -  
  
     Kod öğesi veya bağlantı için kısayol menüsünü açın ve seçin **Düzenle**, **kaldırmak**.  
  
2.  Öğe veya bağlantı bir grubun parçası ise **yeniden getirmesi alt** düğmesini ![yeniden getirmesi alt simge](../modeling/media/dependencygraph_deletednodesicon.png "DependencyGraph_DeletedNodesIcon") grubu içinde görüntülenir. Eksik öğeleri ve bağlantıları almak için burayı tıklatın.  
  
-   Arka plandaki kod etkilemeden bir eşlemesinden kod öğeleri ve bağlantıları kaldırabilirsiniz. Bunları sildiğinizde, tanımlarını DGML (.dgml) dosyasından kaldırılır.  
  
-   DGML düzenleyerek, tanımlanmamış kod öğeleri ekleme veya bazı Visual Studio'nun önceki sürümleri kullanılarak oluşturulmuş eşlemeler, bu özelliği desteklemez.  
  
##### <a name="flag-a-code-element-for-follow-up"></a>Kod öğesi izleme için bayrak  
  
1.  Kod öğesi veya izleme için bayrak istediğiniz bağlantısını seçin.  
  
2.  Kısayol menüsünü açın ve seçin **Düzenle**, **izleme bayrağı**.  
  
-   Varsayılan olarak, kırmızı bir arka plan kod öğesi kazanır. Göz önünde bulundurun [açıklama ekleme](#AddComments) ile ilgili izleme bilgileri için.  
  
-   Öğenin arka plan rengini değiştirmek veya seçerek izleme bayrağını Temizle **Düzenle**, **diğer bayrağı renkleri**.  
  
##  <a name="ChangeStyleCodeOrLink"></a>Kod öğesi veya bağlantı stilini değiştirme  
 Kod öğeleri simgeleri ve kod öğeleri ve önceden tanımlanmış simge ve renkler kullanarak bağlantı renklerini değiştirebilirsiniz. Örneğin, kod öğeleri ve belirli bir kategori veya özellik sahip bağlantıları vurgulamak için bir renk seçebilirsiniz. Bu belirleyip harita belirli alanlara odaklanmanıza olanak tanır. Haritanın .dgml dosyasını düzenleyerek özel simgeleri ve renkleri belirtebilirsiniz; bkz: [Özelleştir kod eşlemeleri DGML dosyalarını düzenleyerek](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
#### <a name="to-apply-a-predefined-color-or-icon-to-code-elements-or-links-with-a-certain-category-or-property"></a>Kod öğeleri veya belirli bir kategori veya özellik bağlantılarıyla önceden tanımlanmış renk veya simge uygulamak için  
  
1.  Map araç çubuğunda seçin **gösterge**.  
  
2.  İçinde **gösterge** kutusu, kod öğesi kategori veya özellik zaten listede görüntülenip görüntülenmediğine bakın.  
  
3.  Liste kategori veya özellik içermiyorsa seçin  **+**  içinde **gösterge** kutusuna ve ardından **düğüm özelliği**, **düğüm kategorisi** , **Bağlantı özelliğinin**, veya **bağlantı kategori**. Ardından özelliği veya kategori seçin. Kategori veya özellik artık görünür **gösterge** kutusu.  
  
    > [!NOTE]
    >  Oluşturmak ve bir kategori veya bir özellik için bir kod öğesi atamak için haritanın .dgml dosyasını düzenleyebilirsiniz; bkz: [Özelleştir kod eşlemeleri DGML dosyalarını düzenleyerek](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
4.  İçinde **gösterge** kutusunda, değiştirmek istediğiniz veya, kategori veya özellik eklediğiniz yanındaki simgesine tıklayın.  
  
5.  Değiştirmek istediğiniz stili seçmek için aşağıdaki tabloyu kullanın:  
  
    |**Değiştirmek için**|**Seçin**|  
    |-----------------------|----------------|  
    |Arka plan rengi|**Arka plan**|  
    |Anahat rengi|**Stroke**|  
    |Metin rengi (harf "f" sonucunu göstermek için görüntülenir)|**Ön plan**|  
    |Simge|**Simgeler**|  
  
     **Renk Seçici ayarlamak** veya **simgesi ayarlamak Seçici** iletişim kutusu görüntülenirse, bir renk veya simgesini seçin.  
  
6.  İçinde **Renk Seçici ayarlamak** veya **simgesi ayarlamak Seçici** iletişim kutusunda, aşağıdakilerden birini yapın:  
  
    |**Uygulanacak bir**|**Bu adımları uygulayın**|  
    |--------------------|-----------------------------|  
    |Renkleri ya da simgeler|Açık **seçin renk** (veya **simgesi**) **ayarlamak** listesi. Renkleri veya simgeler kümesi seçin.|  
    |Belirli bir renk veya simgesi|Kategori veya özellik değer listesini açın. Bir renk veya simgesini seçin.|  
  
    > [!NOTE]
    >  Yeniden düzenleme, silme veya geçici olarak stillerde devre dışı bırak **gösterge** kutusu. Bkz: [Düzenle gösterge kutusu](#ModifyLegend).  
  
##  <a name="ModifyLegend"></a>Gösterge kutusunu Düzenle  
 Yeniden düzenleme, silme veya geçici olarak stillerde devre dışı bırak **gösterge** kutusunda:  
  
1.  Bir stili için kısayol menüsünü açın **gösterge** kutusu.  
  
2.  Aşağıdaki görevlerden birini uygulayın:  
  
    |**Hedef**|**Seçin**|  
    |------------|----------------|  
    |Kod öğesini devre dışı bırakma|**Devre Dışı Bırak**|  
    |Kod öğesini sil|**Sil**|  
    |Stili yukarı taşıyın|**Yukarı Taşı**|  
    |Kod öğesi Aşağı Taşı|**Aşağı Taşı**|  
  
##  <a name="CopyLegend"></a>Stiller bir eşlemesinden kopyalama  
  
1.  Emin olun **gösterge** kutusu kaynak harita üzerinde görüntülenir. Map araç çubuğunda görünür durumda değilse, tıklatın **gösterge**.  
  
2.  Kısayol menüsünü açın **gösterge** kutusu. Seçin **kopyalama gösterge**.  
  
3.  Gösterge hedef harita üzerine yapıştırın.  
  
##  <a name="MergeMaps"></a>Kod haritaları birleştirme  
 Kod öğeleri arasındaki eşlemeleri yapıştırarak eşlemeleri birleştirebilirsiniz. Kod öğesi Tanımlayıcıları eşlenirse, ardından yapıştırma kod öğeleri bir birleştirme işlemi gibi çalışır. Bu görev kolaylaştırmak için tüm derlemeleri veya her derleme ya da ikili tam yolunu birleştirmek istediğiniz her eşleme için aynı böylece aynı klasörde görselleştirmek için istediğiniz ikili dosyaları yerleştirin.  
  
 Alternatif olarak, bu klasörden aynı Eşle bu derlemeler veya ikili dosyaları sürükleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)   
 [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Kod Haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)   
 [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md)   
 [Yönlendirilmiş Grafik İşaretleme Dili (DGML) başvurusu](../modeling/directed-graph-markup-language-dgml-reference.md)
