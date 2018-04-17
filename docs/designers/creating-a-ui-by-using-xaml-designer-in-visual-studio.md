---
title: Visual Studio'da XAML Tasarımcısı kullanarak bir kullanıcı Arabirimi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.technology:
- vs-ide-designers
ms.topic: conceptual
f1_keywords:
- VS.XamlDesigner
- VS.DevicePanel
- VS.XamlEditor
- VS.DocumentOutline
ms.assetid: c54969a7-d75a-4a35-9b37-af7a596a7c24
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: eee5da84104e559d8e95ef022e4496cd3942627f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-ui-by-using-xaml-designer-in-visual-studio"></a>Visual Studio’da XAML Tasarımcısı’nı kullanarak kullanıcı arabirimi oluşturma
Visual Studio'da XAML Tasarımcısı tasarım XAML tabanlı Windows ve Web uygulamaları yardımcı olması için görsel bir arabirim sağlar. Denetimlerden sürükleyerek, uygulamalarınız için kullanıcı arabirimleri oluşturabilirsiniz **araç** ve özelliklerini ayarlama **özellikleri** penceresi. XAML doğrudan XAML görünümünde de düzenleyebilirsiniz.  
  
 Gelişmiş XAML tasarım görevler için animasyonları ve davranışları gibi bkz [Visual Studio için Blend'i kullanarak kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-blend-for-visual-studio.md). Ayrıca bkz. [Visual Studio ve Visual Studio için Blend'de XAML tasarlama](../designers/designing-xaml-in-visual-studio.md) araçları arasında bir karşılaştırma için.
  
## <a name="xaml-designer-workspace"></a>XAML Tasarımcısı çalışma  
 XAML Tasarımcısı'nda çalışma birkaç görsel bir arabirim öğelerden oluşur. XAML Düzenleyicisi'ni çalışma yüzeyi bunlar aygıt penceresi, Belge Anahattı penceresi ve Özellikler penceresi. XAML Tasarımcısı'nı açmak için XAML dosyası içinde sağ **Çözüm Gezgini** ve **Görünüm Tasarımcısı**.  
  
## <a name="authoring-views"></a>Görünümleri yazma  
 XAML Tasarımcısı XAML görünümü ve uygulamanızın işlenmiş XAML işaretleme eşzamanlı bir Tasarım görünümünü sağlar. Visual Studio'da Aç XAML dosyasıyla, Tasarım görünümü ve XAML görünümü arasında kullanarak geçebilirsiniz **tasarım** ve **XAML** sekmeleri. Kullanabileceğiniz **takas bölmeleri** hangi penceresinde geçiş yapmak için düğmesi görünür üstte: çalışma yüzeyi ya da XAML Düzenleyicisi'ni.  
  
 Tasarım görünümünde pencere içeren *çalışma yüzeyi* etkin pencere ve bir birincil çalışma yüzeyi olarak kullanın. Ekleyerek veya öğeleri çizim ve bunları değiştirerek bir sayfa uygulamanızda görsel olarak tasarlamak için kullanabilirsiniz. Daha fazla bilgi için bkz: [XAML Tasarımcısı'nda öğeleri ile çalışma](../designers/working-with-elements-in-xaml-designer.md). Bu örnekte çalışma yüzeyi Tasarım görünümünde gösterilmiştir.  
  
 ![Tasarım görünümü XAML Tasarımcısı'nın](../designers/media/xaml_editor_design_view.png "xaml_editor_design_view")  
  
 Bu özellikler, çalışma yüzeyine kullanılabilir:  
  
 **Dayama çizgileri**  
 Dayama çizgileri olan *hizalama sınırları* zaman denetimlerin kenarlarını hizalanır veya ne zaman metin taban çizgileri hizalanmış göstermek için kırmızı kesikli satır olarak görünür. Hizalama sınırları yalnızca görünür **dayama çizgileri için tutturma** etkinleştirilir.  
  
 **Kılavuz rayları**  
 `Grid` rayları satırları ve sütunları yönetmek için kullanılan bir [kılavuz](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx) paneli. Oluşturun ve satırları ve sütunları Sil ve bunların göreli genişlik ve yükseklik ayarlayabilirsiniz. Çalışma yüzeyi soldaki bölmede görünür, dikey kılavuz raylar satırlar için kullanılır ve üstünde görünür, yatay çizgi sütunlar için kullanılır.  
  
 **Kılavuz Donatıcılar**  
 A `Grid` donatıcı görünür üzerinde ekli dikey veya yatay çizgi bulunan bir üçgen olarak `Grid` raylar. Sürüklediğinizde bir `Grid` donatıcı, genişlik ve bitişik sütunlara veya satırlara uzunluklarının fareyi hareket ederken güncelleştirin.  
  
 `Grid` Donatıcılar genişlik ve yüksekliğini denetlemek için kullanılan bir `Grid`'s satırları ve sütunları. Tıklayarak yeni bir sütun veya satır ekleyebilirsiniz `Grid` rayları. İçin yeni bir satır veya sütun satır eklediğinizde bir `Grid` sahip iki veya daha fazla sütun veya satır, kısa bir araç çubuğu paneli genişlik ve yükseklik açıkça ayarlamanıza olanak tanır raylar dışında görüntülenir. Mini Araç boyutlandırma seçeneklerini ayarlamanıza olanak tanır `Grid` satırları ve sütunları.  
  
 **Tanıtıcıları yeniden boyutlandırma**  
 Yeniden boyutlandırma tanıtıcıları seçili denetimlere görünür ve denetimi yeniden boyutlandırma imkan tanır. Denetim yeniden boyutlandırdığınızda genişlik ve yükseklik değerleri genellikle denetimi size yardımcı olması için görüntülenir. Tasarım görünümünde denetimleri düzenleme hakkında daha fazla bilgi için bkz: [XAML Tasarımcısı'nda öğeleri ile çalışma](../designers/working-with-elements-in-xaml-designer.md).  
  
 **Kenar boşlukları**  
 Kenar boşlukları kenarın bir denetimin kapsayıcısının kenarı arasındaki sabit alan miktarını temsil eder. Kullanarak bir denetim kenar boşluklarını ayarlayabilirsiniz [kenar boşluğu](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.frameworkelement.margin.aspx) özellikleri altında **düzeni** Özellikleri penceresinde.  
  
 **Kenar boşluğu Donatıcılar**  
 Kenar boşluğu Donatıcılar düzeni kapsayıcısı göreli bir öğenin kenar boşluklarını değiştirmek için kullanabilirsiniz. Kenar boşluğu donatıcı açık olduğunda, kenar boşluğu ayarlı değildir ve kenar boşluğu donatıcı kopuk bir zincirini görüntüler. Kenar ayarlanmadığında öğeleri bir düzen kapsayıcı çalışma zamanında boyutlandırıldığında yerinde kalmaya devam edecek. Kenar boşluğu donatıcı kapalı olduğunda bir kenar boşluğu donatıcı sertifikalarından zinciri görüntüler ve düzen kapsayıcı (kenar sabit kalır) çalışma zamanında boyutlandırıldığında öğeleri ile kenar taşınır.  
  
 **Öğe tanıtıcıları**  
 Bir öğenin bir öğe çevreleyen mavi kutu köşeleri üzerinde işaretçiyi yüzeyinde görünür öğesi tanıtıcıları kullanarak değiştirebilirsiniz. Bu tanıtıcıları döndürün, yeniden boyutlandırma, çevir, taşımak veya köşe RADIUS öğesine eklemek etkinleştirin. Öğe tanıtıcı simgesi işlevi tarafından değişir ve işaretçiyi tam konumu bağlı olarak değişir. Öğe tanıtıcıları görmüyorsanız, öğesinin seçili olduğundan emin olun.  
  
 Tasarım görünümünde, aşağıda gösterildiği gibi ek çalışma yüzeyi komutları ekranın sol alt bölgesine kullanılabilir:  
  
 ![Tasarım görünümü komutları](../designers/media/xaml_editor_design_controls.png "xaml_editor_design_controls")  
  
 Bu komutlar, bu araç çubuğunda kullanılabilir:  
  
 **Yakınlaştır**  
 Yakınlaştırma tasarım yüzeyine boyut sağlar. %800 %12,5 yakınlaştırma veya gibi seçeneklerini **seçime uygun** ve **tümüne uyan**.  
  
 **Göster/Gizle ek kılavuz**  
 Kılavuz çizgilerini gösterir ek kılavuz gizler veya gösterir. Kılavuz çizgileri kullanılır olduğunda ya da **için kılavuz çizgilerini tutturma** veya **dayama çizgileri için tutturma** etkinleştirilir.  
  
 **Açın veya kılavuz çizgileri için tutturma kapatın**  
 Varsa **için kılavuz çizgilerini tutturma** yüzeyinde öğenin sürüklediğinizde etkin öğesinin en yakın yatay ve dikey kılavuz çizgisi ile hizalar eğilimindedir.  
  
 **Açın veya dayama çizgileri için tutturma kapatın**  
 Dayama çizgileri Yardım, Hizala birbirlerine göreli denetler. Varsa **dayama çizgileri için tutturma** denetimi diğer denetimleri göre sınırları kenarları ve bazı denetimler metnin yatay veya dikey olarak Hizala tıklattığınızda görünür hizalama sürüklediğinizde olarak etkinleştirilir. Hizalama sınır kırmızı kesikli bir çizgi olarak görünür.  
  
 XAML görünümünde XAML Düzenleyicisi'ni içeren etkin penceresidir ve XAML Düzenleyicisi'ni, birincil geliştirme aracıdır. Genişletilebilir uygulama biçimlendirme dili (XAML), bir uygulamanın kullanıcı arabiriminde belirlemek için bir bildirim temelli, XML tabanlı sözlüğünü sağlar. XAML görünümü IntelliSense, otomatik biçimlendirme, sözdizimi vurgulama ve etiket Gezinti içerir. Bu çizim XAML görünüm gösterir:  
  
 ![XAML görünümü](../designers/media/xaml_editor.png "xaml_editor")  
  
 **Bölme Görünüm Çubuğu**  
 XAML Düzenleyicisi'ni alt pencerede olduğunda bölme Görünüm Çubuğu XAML görünümü üstünde görünür. Bölme Görünüm Çubuğu Tasarım görünümü ve XAML görünümü boyutlarını denetlemenize olanak sağlar. Görünümleri konumlarını gönderip alabilir (kullanarak **takas bölmeleri** düğmesi), görünümleri yatay veya dikey olarak düzenlenmiş belirtin ve ya da Görünüm daraltın.  
  
 **Biçimlendirme yakınlaştırma**  
 Biçimlendirme Yakınlaştırma boyutu XAML görünüm sağlar. %400 %20 değerinden yakınlaştırabilirsiniz.  
  
## <a name="device-window"></a>Aygıt penceresi  
 XAML Tasarımcısı'nda Aygıt penceresi, çeşitli görünümleri, görüntüler, tasarım zamanında benzetimini ve görüntüleme seçeneklerini projeniz için olanak sağlar. Aygıt penceresi kullanılabilir **tasarım** XAML Tasarımcısı'nda çalışırken menüsü. İşte bu şekilde görünür:  
  
 ![Aygıt penceresi](../designers/media/xaml_editor_device_panel.png "xaml_editor_device_panel")  
  
 Cihaz penceresindeki Seçenekler şunlardır:  
  
 **Görüntüleme**  
 Farklı görüntüleme boyutları ve uygulama çözümü belirtir.  
  
 **Yönlendirme**  
 Uygulama için farklı yönleri belirtir: **yatay** veya **dikey**.  
  
 **Edge**  
 Uygulamanız için farklı sınır hizalamaları belirtir: **her ikisi de**, **sol**, **sağ**, veya **hiçbiri**.  
  
 **Yüksek Karşıtlık**  
 Seçili Karşıtlık ayarına göre uygulama önizlemede. Ne zaman dışında bir değere ayarlayın, bu ayar **varsayılan**, geçersiz kılar `RequestedTheme` özelliği App.xaml ayarlanmış.  
  
 **Ölçeklendirme geçersiz kıl**  
 Açma ve kapatma içinde tasarım yüzeyi ölçeklendirme belgenin öykünme kapatır. Bu bir faktörüyle ölçeğe artırmanıza olanak sağlar. Öykünme üzerinde etkinleştirmek için onay kutusunu seçin. Örneğin, ölçekleme yüzdesi % 100 ise, belge tasarım yüzeyine içinde %140 ölçeklendirin. Geçerli ölçekleme yüzdesi 180 yoksa bu seçenek devre dışı bırakılır.  
  
 **En küçük genişliği**  
 En küçük genişliği ayarı belirtir. En küçük genişliği App.xaml içinde değiştirilebilir.  
  
 **Tema**  
 Uygulama tema belirtir. Örneğin, bir koyu ve açık bir tema arasında geçiş.  
  
 **Chrome Göster**  
 Açar ve uygulamanızın Tasarım görünümünde etrafında benzetimli tablet çerçeve kapatır. Çerçeve göstermek için bu onay kutusunu seçin.  
  
 **Görüntülenecek küçük**  
 Görüntü modu belirtir. Görüntü boyutu belge boyutunu küçük için onay kutusunu seçin.  
  
## <a name="document-outline-window"></a>Belge Anahattı penceresi  
 Belge Anahattı penceresi XAML Tasarımcısı'nda bu görevleri gerçekleştirmenize yardımcı olur:  
  
-   Tüm öğeleri hiyerarşik yapısını yüzeyinde görüntüleyin.  
  
-   Öğeleri seçin, böylece bunları (hiyerarşisinde etrafında yüzeyinde değiştirmek, Özellikler penceresinde özelliklerini ayarlayın ve benzeri Taşı) değiştirebilirsiniz. Daha fazla bilgi için bkz: [XAML Tasarımcısı'nda öğeleri ile çalışma](../designers/working-with-elements-in-xaml-designer.md)  
  
-   Oluşturun ve denetimleri olan öğeler için şablonlar değiştirin.  
  
-   Bağlam menüsü seçili öğeler için kullanın. Aynı menü ayrıca çalışma yüzeyi seçilen öğeleri için kullanılabilir.  
  
 Belge Anahattı penceresi görüntülemek için menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **belge anahattı**.  
  
 ![Belge Anahattı penceresi](../designers/media/xaml_editor_doc_outline.png "xaml_editor_doc_outline")  
  
 Belge Anahattı penceresi kullanılabilir seçenekleri şunlardır:  
  
 **Belge Anahattı**  
 Belge Anahattı penceresi ana görünümünde bir ağaç yapısında bir belge hiyerarşisini görüntüler. Belge Anahattı hiyerarşik yapısını, ayrıntı, değişen düzeylerinde belgeyi inceleyin ve kilitlemek ve ayrı olarak veya gruplar halinde öğelerini gizleme için kullanabilirsiniz.  
  
 **Göster/Gizle**  
 Belge Anahattı öğelere karşılık gelen çalışma yüzeyi öğeleri gizler veya gösterir. Kullanım **Göster/Gizle** gösterilen bir göz simgesini görüntüleme veya öğelerini gizlemek için CTRL + H, bunları görüntülemek için SHIFT + CTRL + H basın düğmeler.  
  
 **Kilitle/Kilidini Aç**  
 Kilitler veya belge anahattı öğelere karşılık gelen çalışma yüzeyi öğeler kilidini açar. Kilitli öğeler değiştirilemez. Kullanım **kilit ve kilidini** asma görüntüleme düğmeleri sembol kilitli olduğunda ya da kilitlerini için CTRL + L kilit öğelerine ve SHIFT + CTRL + L tuşlarına basın.  
  
 **PageRoot dönüş kapsamına**  
 Yukarı ok simgesi gösterir, Belge Anahattı penceresi üstündeki seçeneği Belge Anahattı önceki kapsama döndürür. Yalnızca bir stil veya şablon kapsamında olduğunuzda yukarı kapsamı için geçerlidir.  
  
## <a name="properties-window"></a>Özellik penceresi  
 Özellikler penceresini denetimlerinde özellik değerlerini ayarlamanıza olanak tanır. İşte bu şekilde görünür:  
  
 ![Özellikler penceresi](../designers/media/xaml_editor_prop_window.png "xaml_editor_prop_window")  
  
 Özellikler penceresini üstündeki çeşitli seçenekler vardır. Seçili olan öğenin adını kullanarak değiştirebilirsiniz **adı** kutusu. Sol üst köşesinde şu anda seçilen öğeyi temsil eden bir simge yoktur. Kategoriye göre veya alfabetik olarak özelliklerini düzenlemek için tıklayın **kategori**, **adı**, veya **kaynak** içinde **düzenleme ölçütü** listesi. Bir denetim için olayların listesini görmek için tıklatın **olayları** Şimşek Cıvata simgesi görüntüler düğmesi. Özelliğin adını yazmanız bir özellik için arama yapmak için başlangıç **arama özellikleri** kutusu. Özellikler penceresini yazarken aramanızla eşleşen özelliklerini görüntüler. Bazı özellikler, Gelişmiş Özellikler aşağı ok düğmesini seçerek ayarlamanıza olanak tanır. Olayları işleme ve özelliklerini kullanma daha fazla bilgi için bkz: [hızlı başlangıç: denetimler ekleme ve olayları işleme](http://go.microsoft.com/fwlink/?LinkID=247983)  
  
 Her bir özellik sağında değeri olan bir *özelliği işaret* kutu simgesi görünür. Özellik işaretçisi görünümünü veri bağlama veya özelliğine uygulanan bir kaynak olup olmadığını gösterir. Örneğin, varsayılan değeri beyaz kutu simgesi gösterir, siyah kutu simgesi genellikle bir yerel kaynağı uygulanan ve veri bağlama uygulanan bir turuncu kutusu genellikle gösterir gösterir. Özellik işaretçisi tıklattığınızda, bir stil tanımını gidin, veri bağlama Oluşturucusu'nu açmak veya kaynak seçici açın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XAML Tasarımcısı'nda öğeleri ile çalışma](../designers/working-with-elements-in-xaml-designer.md)   
 [Oluşturma ve kaynak Uygula](../designers/how-to-create-and-apply-a-resource.md)   
 [İzlenecek yol: XAML Tasarımcısı’nda verileri bağlama](../designers/walkthrough-binding-to-data-in-xaml-designer.md)