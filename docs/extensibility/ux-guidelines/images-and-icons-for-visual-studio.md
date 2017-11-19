---
title: "Görüntüleri ve Visual Studio için simgeler | Microsoft Docs"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f410325e-9cf2-4f39-b6d7-b672121c2691
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7856f8fac7e986f3e5383fa91261de39fe815a28
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="images-and-icons-for-visual-studio"></a>Görüntüleri ve Visual Studio için simgeler
##  <a name="BKMK_ImageUseInVisualStudio"></a>Visual Studio görüntü kullanımda  
 Yapma resmi oluşturmadan önce göz önünde bulundurun 1.000 + görüntülerinde kullanımını [Visual Studio görüntü kitaplığı](http://www.microsoft.com/en-my/download/details.aspx?id=35825).  
  
### <a name="types-of-images"></a>Görüntü türleri  
  
-   **Simgeler**. Komutları, hiyerarşileri, şablonları ve benzeri görünür küçük görüntüler. Visual Studio'da kullanılan varsayılan simge boyutu 16 x 16 PNG ' dir. Yansıma hizmeti tarafından otomatik olarak üretilen simgeler HDPI desteği için XAML biçimi oluşturur.  
  
     **Not:** resimleri menü sisteminde kullanılırken, her komut için bir simge oluşturmamalısınız. Başvurun [menüleri ve Visual Studio için komutları](../../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md) komutunuzu bir simge almak olup olmadığını görmek için.  
  
-   **Küçük resim.** Yeni Proje iletişim kutusu gibi bir iletişim kutusu Önizleme bölümünde kullanılan görüntüler.  
  
-   **İletişim kutusu görüntüler.** İletişim kutuları veya sihirbazlar, açıklayıcı grafik veya ileti göstergeleri olarak görünür görüntüler. Seyrek ve zor bir kavramı göstermeye veya kullanıcının dikkatini (uyarı, uyarı) elde etmek için yalnızca gerekli olduğunda kullanın.  
  
-   **Animasyonlu görüntüler.** İlerleme göstergesi, durum çubukları ve işlem iletişim kutuları kullanılır.  
  
-   **İmleçler.** Fareyi, burada bir nesne bırakılabilir vb. kullanarak bir işlem izin verilip verilmeyeceğini belirtmek için kullanılır.  
  
##  <a name="BKMK_IconDesign"></a>Simge tasarım  
  
### <a name="overview"></a>Genel Bakış  
 Visual Studio temiz geometri ve olumlu/olumsuz (Açık/Koyu) 50/50 dengesi varsa ve doğrudan, anlaşılabilir metaphors kullanmak modern stili simgeleri kullanır. Önemli simgesi Tasarım Merkezi daha anlaşılır olması, basitleştirme ve bağlam etrafında işaret eder.  
  
-   **Netlik:** odaklanmak simge anlamı ve bireyselliğinizi sağlayan çekirdek benzetimini.  
  
-   **Basitleştirme:** çekirdek anlamlarını simge Küçült - yalnızca gerekli öğe ve hiçbir frills tema alın.  
  
-   **Bağlam:** hangi öğelerin simgesinin çekirdek benzetimini oluşturan karar verirken önemlidir kavram geliştirme sırasında bir simge rolü tüm yönlerini göz önünde bulundurun.  
  
 Simgeler ile önlemek için tasarım noktası sayısı vardır:  
  
-   Uygun olduğunda kullanıcı Arabirimi öğeleri dışında belirtmek simgeleri kullanmayın. Kullanıcı Arabirimi öğesi ne ortak, korumalı ne benzersiz olduğunda daha soyut veya sembolik bir yaklaşım seçin.  
  
-   Belgeler, klasörleri, okları ve Büyüteç gibi ortak öğeler aşırı yok. Bu öğeler simgenin anlamı için yalnızca gerekli olduğunda kullanın. Sağ taraftaki Büyüteç yalnızca arama, örneğin, belirtmelidir göz atın ve bulabilirsiniz.  
  
-   Bazı eski simge öğeleri perspektif kullanımını korumak rağmen daha anlaşılır olması olmadan öğesi eksik sürece yeni simgeler perspektif ile oluşturmayın.  
  
-   Çok fazla bilgisi simge içine cram yok. Kolay tanınan ya da bilinen bir simge öğrenilen basit bir görüntü fazla karmaşık bir görüntü daha kullanışlıdır. Simge Yazının tamamını bildiremez.  
  
### <a name="icon-creation"></a>Simge oluşturma  
  
#### <a name="concept-development"></a>Kavram geliştirme  
 Visual Studio kullanıcı Arabiriminde içinde çok çeşitli simge türü vardır. Simge türü geliştirme sırasında dikkatlice. Belirsiz veya seyrek kullanıcı Arabirimi nesneleri simgesi öğeleriniz için kullanmayın. Bu durumda, sembolik için gibi akıllı etiket simgesiyle kabul et. Sol taraftaki soyut etiketi anlamını sağdaki belirsiz, UI tabanlı sürümden daha belirgin olduğuna dikkat edin:  
  
|||  
|-|-|  
|**Simgesel görüntülerin doğru kullanımı**|**Simgesel görüntülerin yanlış kullanımı**|  
|![Doğru akıllı etiket simgesi](../../extensibility/ux-guidelines/media/0404-01_smarttagcorrect.png "0404 01_SmartTagCorrect")|![Hatalı akıllı etiket simgesi](../../extensibility/ux-guidelines/media/0404-02_smarttagincorrect.png "0404 02_SmartTagIncorrect")|  
  
 Standart, anlaşılacak kullanıcı Arabirimi öğeleri de simgelerini çalışma örneği vardır. Bu tür bir örnek penceredir ekleyin:  
  
|||  
|-|-|  
|**Simge doğru UI öğe**|**Yanlış kullanıcı Arabirimi öğesi bir simgesi**|  
|![Doğru pencere Ekle simgesi](../../extensibility/ux-guidelines/media/0404-03_addwindowcorrect.png "0404 03_AddWindowCorrect")|![Yanlış pencere Ekle simgesi](../../extensibility/ux-guidelines/media/0404-04_addwindowincorrect.png "0404 04_AddWindowIncorrect")|  
  
 Simge anlamı gerekli olmadıkça bir belge temel bir öğe kullanmayın. Belge öğesi ile yenileme anlamı iletişim kurmak gerekli değildir ancak belgenin Belge Ekle bir öğede (aşağıda) anlamı, kaybolur.  
  
|||  
|-|-|  
|**Belge simgesi doğru kullanımı**|**Belge simgesi yanlış kullanımı**|  
|![Doğru belge simgesi](../../extensibility/ux-guidelines/media/0404-05_documenticoncorrect.png "0404 05_DocumentIconCorrect")|![Yanlış belge simgesi](../../extensibility/ux-guidelines/media/0404-06_documenticonincorrect.png "0404 06_DocumentIconIncorrect")|  
  
 "Göster" kavramı, en iyi ne gösterilir, gibi tüm dosyaları göster örnek olarak gösterilmiştir simgesiyle temsil. Mercek benzetimini "Görünüm" gibi gerekiyorsa, kaynak görünümü örnekle kavramını göstermek için kullanılabilir.  
  
|||  
|-|-|  
|**"Göster"**|**"View"**|  
|![Simgesini göster](../../extensibility/ux-guidelines/media/0404-07_show.png "0404 07_Show")|![Görünüm simgesi](../../extensibility/ux-guidelines/media/0404-08_view.png "0404 08_View")|  
  
 Sağ taraftaki cam simgesini temsil yalnızca arayacağı büyütme, bulma ve göz atın. Artı veya eksi işareti ile sol taraftaki değişken, yalnızca yakınlaştırma temsil / Uzaklaştır.  
  
|||  
|-|-|  
|**"Ara"**|**"Yakınlaştırma"**|  
|![Arama simgesine](../../extensibility/ux-guidelines/media/0404-09_search.png "0404 09_Search")|![Yakınlaştır simgesi](../../extensibility/ux-guidelines/media/0404-10_zoom.png "0404 10_Zoom")|  
  
 Ağaç görünümlerde klasör simgesine ve bir değiştiricisi kullanmayın. Kullanılabilir olduğunda, yalnızca değiştiricisini kullanın.  
  
|||  
|-|-|  
|**Doğru ağaç görünümü simgesi**|**Yanlış ağaç görünümü simgesi**|  
|![Doğru ağaç görünümü simgesi &#40; 1 &#41; ] (../../extensibility/ux-guidelines/media/0404-11_treeviewcorrect1.png "0404 11_TreeViewCorrect1") ![düzeltmek ağaç görünümü simgesi &#40; 2 &#41;] (../../extensibility/ux-guidelines/media/0404-12_treeviewcorrect2.png "0404 12_TreeViewCorrect2")|![Yanlış ağaç görünümü simgesi &#40; 1 &#41; ] (../../extensibility/ux-guidelines/media/0404-13_treeviewincorrect1.png "0404 13_TreeViewIncorrect1") ![yanlış ağaç görünümü simgesi &#40; 2 &#41;] (../../extensibility/ux-guidelines/media/0404-14_treeviewincorrect2.png "0404 14_TreeViewIncorrect2")|  
  
### <a name="style-details"></a>Stil ayrıntıları  
  
#### <a name="layout"></a>Düzen  
 Standart 16 x 16 simgelerini gösterildiği gibi yığın öğeleri:  
  
 ![16 x 16 simgeler için Düzen yığın](../../extensibility/ux-guidelines/media/0404-15_layoutstack.png "0404 15_LayoutStack")<br />Düzen yığını için 16 x 16 simgeler
  
 Durum bildirim öğeleri daha iyi tek başına simgeler olarak kullanılır. İçinde bir bildirim temel öğede gibi görev tamamlanma simgesiyle Yığılmış bağlamları vardır:  
  
 ![Visual Studio'da tek başına bildirimleri](../../extensibility/ux-guidelines/media/0404-16_standalonenotificationicons.png "0404 16_StandaloneNotificationIcons")<br />Tek başına bildirim simgeleri
  
 ![Görev tamamlandı simgesi](../../extensibility/ux-guidelines/media/0404-17_taskcomplete.png "0404 17_TaskComplete")<br />Görev tamamlandı simgesi
  
 Proje simgeler genellikle birden çok boyutu içeren .ico dosyalarıdır. Çoğu 16 x 16 simgeler aynı öğeler içerir. Proje türü uygulanabilir olduğunda dahil daha fazla ayrıntı 32 x 32 sürümlerde.  
  
 ![Simgeler Visual Studio Proje](../../extensibility/ux-guidelines/media/0404-18_iconprojectthreesizes.png "0404 18_IconProjectThreeSizes")<br />16 x 16 ve 32 x 32 VB Windows Denetim Kitaplığı projesi simgelerini 
  
 Merkezi kendi piksel çerçevesinde bir simge. Bu mümkün değilse, üstüne ve/veya sağ çerçevenin simgesi hizalayın.  
  
 ![Piksel çerçevesinde ortalanmış simgesi](../../extensibility/ux-guidelines/media/0404-19_iconcentered.png "0404 19_IconCentered")<br />Piksel çerçevesinde ortalanmış simgesi
  
 ![Simge hizalanan üst piksel çerçeve sağındaki](../../extensibility/ux-guidelines/media/0404-20_icontopright.png "0404 20_IconTopRight")<br />Simge hizalı en üstüne sağ çerçevenin
  
 ![Simge Ortalanan ve piksel çerçeve dön hizalı](../../extensibility/ux-guidelines/media/0404-21_icontopalign.png "0404 21_IconTopAlign")<br />Ortalanmış ve çerçeve dön hizalı simgesi
  
 İdeal hizalama ve Bakiye elde etmek için eylem karakterlerin olan temel öğesi simgenin engellemekte kaçının. İlk karakter temel öğenin sol getirin. Ek bir öğe eklerken hizalama ve simge bakiyesini göz önünde bulundurun.  
  
|||  
|-|-|  
|**Doğru hizalama ve eşit olarak dengele.**|**Yanlış hizalama ve eşit olarak dengele.**|  
|![Doğru simge bakiye ve hizalama](../../extensibility/ux-guidelines/media/0404-22_alignbalancecorrect.png "0404 22_AlignBalanceCorrect")|![Hatalı simge bakiye ve hizalama](../../extensibility/ux-guidelines/media/0404-23_alignbalanceincorrect.png "0404 23_AlignBalanceIncorrect")|  
  
 Boyutu eşlik öğelerini paylaşma ve kümelerinde kullanılan simgeler için emin olun. Yanlış eşleştirme, oku ve daire büyük boyutlu olduğunu unutmayın ve eşleşmiyor.  
  
|||  
|-|-|  
|**Doğru boyutta eşlik**|**Boyut yanlış eşlik**|  
|![Doğru simge boyutu ve eşlik](../../extensibility/ux-guidelines/media/0404-24_sizeparitycorrect.png "0404 24_SizeParityCorrect")|![Hatalı simge boyutu ve eşlik](../../extensibility/ux-guidelines/media/0404-25_sizeparityincorrect.png "0404 25_SizeParityIncorrect")|  
  
 Tutarlı satır ve görsel ağırlıkları kullanın. Yan yana karşılaştırma kullanarak oluşturmakta olduğunuz simgesi diğer simgeleri nasıl karşılaştırır değerlendirin. Hiçbir zaman tüm 16 x 16 çerçeve kullanma 15 x 15 veya daha küçük. Negatif pozitif (Koyu hafif) oranı 50/50 olmalıdır.  
  
|||  
|-|-|  
|**Doğru negatif pozitif oranı**|**Hatalı negatif pozitif oranı**|  
|![Görsel ağırlık simgeleri &#40; 1 &#41;düzeltin; ] (../../extensibility/ux-guidelines/media/0404-26_visualweightcorrect1.png "0404 26_VisualWeightCorrect1")<br /><br /> ![Görsel ağırlık simgeleri &#40; 2 &#41;düzeltin; ] (../../extensibility/ux-guidelines/media/0404-27_visualweightcorrect2.png "0404 27_VisualWeightCorrect2")<br /><br /> ![Görsel ağırlık simgeleri &#40; 3 &#41;düzeltin; ] (../../extensibility/ux-guidelines/media/0404-28_visualweightcorrect3.png "0404 28_VisualWeightCorrect3")|![Simgeler için yanlış visual ağırlık](../../extensibility/ux-guidelines/media/0404-29_visualweightincorrect.png "0404 29_VisualWeightIncorrect")|  
  
 Basit, karşılaştırılabilir şekiller ve Tamamlayıcı açıları öğesi bütünlüğü ödün vermeden öğelerinizi oluşturmak için kullanın. 45 ° veya 90 derece açıları mümkün olduğunca kullanın.  
  
 ![Düzeltmek simgesi açıları](../../extensibility/ux-guidelines/media/0404-30_iconanglescorrect.png "0404 30_IconAnglesCorrect")  
  
#### <a name="perspective"></a>Perspektif  
 NET ve anlaşılır simgesi tutun. Perspektif ve açık bir kaynak yalnızca gerekli olduğunda kullanın. Simge öğelerde perspektifini kullanarak kaçınılmalıdır rağmen bazı öğeler olmadan tanınmayan bağlıdır. Böyle durumlarda, öğenin netlik stilize perspektif iletişim kurar.  
  
 ![3 noktası perspektif](../../extensibility/ux-guidelines/media/0404-31_3pointperspective.png "0404 31_3PointPerspective")<br />3 noktası perspektifi
  
 ![1-noktası perspektif](../../extensibility/ux-guidelines/media/0404-32_1pointperspective.png "0404 32_1PointPerspective")<br />1-noktası perspektifi
  
 Öğelerin çoğu karşılıklı veya sağ açılı:  
  
 ![Simgeler açılı sağ](../../extensibility/ux-guidelines/media/0404-33_angledright.png "0404 33_AngledRight")  
  
 Yalnızca gerekli daha anlaşılır olması için bir nesne eklenirken ışık kaynağı kullanın.  
  
|||  
|-|-|  
|**Doğru açık kaynak**|**Yanlış açık kaynak**|  
|![Düzeltmek simgeler için açık kaynakları](../../extensibility/ux-guidelines/media/0404-34_lightsourcescorrect.png "0404 34_LightSourcesCorrect")|![Simgeler için yanlış ışık kaynakları](../../extensibility/ux-guidelines/media/0404-35_lightsourcesincorrect.png "0404 35_LightSourcesIncorrect")|  
  
 Anahatları yalnızca okunabilirliği geliştirmek için ya da daha iyi benzetimini iletişim kurmak için kullanın. Negatif pozitif (Koyu-light) Bakiye 50/50 olmalıdır.  
  
|||  
|-|-|  
|**Anahatları doğru kullanımı**|**Anahatları yanlış kullanımı**|  
|![Anahatları düzeltmek](../../extensibility/ux-guidelines/media/0404-36_outlinescorrect.png "0404 36_OutlinesCorrect")|![Yanlış anahatları](../../extensibility/ux-guidelines/media/0404-37_outlinesincorrect.png "0404 37_OutlinesIncorrect")|  
  
#### <a name="icon-types"></a>Simge türü  
 **Kabuğu ve komut çubuğu** simgeleri en fazla üç aşağıdaki öğelerden oluşur: bir temel bir değiştiricisi, bir eylem veya bir durum.  
  
 ![Kabuğu ve komut çubuğu simgeleri örnekleri](../../extensibility/ux-guidelines/media/0404-38_shellicons.png "0404 38_ShellIcons")<br />Kabuğu ve komut çubuğu simgeleri örnekleri
  
 **Araç penceresi komut çubuğu** simgeleri en fazla üç aşağıdaki öğelerden oluşur: bir temel bir değiştiricisi, bir eylem veya bir durum.  
  
 ![Araç penceresi örnekleri komut simgeleri](../../extensibility/ux-guidelines/media/0404-39_toolwindowcommandbaricons.png "0404 39_ToolWindowCommandBarIcons")<br />Araç penceresi komut çubuğu simgeleri örnekleri
  
 **Ağaç görünümü disambiguator** simgeleri en fazla üç aşağıdaki öğelerden oluşur: bir temel bir değiştiricisi, bir eylem veya bir durum.  
  
 ![Ağaç örnekleri görüntülemek disambiguator simgeleri](../../extensibility/ux-guidelines/media/0404-40_treeviewicons.png "0404 40_TreeViewIcons")<br />Ağaç örnekleri disambiguator simgelerini görüntüleme
  
 **Durum tabanlı değeri sınıflandırma** simgeleri aşağıdaki durumlarda var: etkin, devre dışı etkin ve etkin olmayan devre dışı bırakıldı.  
  
 ![Durum tabanlı değeri sınıflandırma simgeleri örnekleri](../../extensibility/ux-guidelines/media/0404-41_statebasedtaxonomy.png "0404 41_StateBasedTaxonomy")<br />Durum tabanlı değeri sınıflandırma simgeleri örnekleri
  
 **IntelliSense** simgeleri en fazla üç aşağıdaki öğelerden oluşur: bir temel, bir değiştirici ve bir durum.  
  
 ![IntelliSense simgeleri örnekleri](../../extensibility/ux-guidelines/media/0404-42_intellisenseicons.png "0404 42_IntelliSenseIcons")<br />IntelliSense simgeleri örnekleri
  
 **Küçük (16 x 16) proje** simgeleri en fazla iki öğe bulunmalıdır: bir temel ve bir değiştiricisi.  
  
 ![Küçük (16 x 16) örnekleri proje simgeler](../../extensibility/ux-guidelines/media/0404-43_16x16project1.png "0404 43_16x16Project1") ![16 x 16 proje simgesini &#40; 2 &#41;] (../../extensibility/ux-guidelines/media/0404-44_16x16project2.png "0404 44_16x16Project2") ![16 x 16 proje simgesini &#40; 3 &#41;] (../../extensibility/ux-guidelines/media/0404-45_16x16project3.png "0404 45_16x16Project3")<br />Küçük (16 x 16) proje simgeler örnekleri
  
 **Büyük (32 x 32) proje** simgeleri en fazla dört aşağıdaki öğelerden oluşur: bir temel, bir veya iki değiştiricileri ve kaplama bir dili.  
  
 ![Büyük (32 x 32) örnekleri proje simgeler](../../extensibility/ux-guidelines/media/0404-46_32x32project.png "0404 46_32x32Project")<br />Büyük (32 x 32) proje simgeler örnekleri
  
### <a name="production-details"></a>Üretim ayrıntıları  
 Windows Presentation Foundation (WPF) kullanarak tüm yeni kullanıcı Arabirimi öğeleri oluşturulması gereken ve tüm yeni simgeleri WPF için 32-bit PNG biçiminde olmalıdır. 24 bit PNG saydamlığı desteklemez ve bu nedenle simgelerini önerilmez eski bir biçimidir.  
  
 96 DPI'de çözünürlükte kaydedin.  
  
#### <a name="file-types"></a>Dosya türleri  
  
-   **32-bit PNG:** simgeleri için tercih edilen biçimi. Bir tek ızgara (piksel) görüntüsü depolayabilir kayıpsız veri sıkıştırma dosya biçimi. 32-bit PNG dosyaları alfa kanal saydamlık, gama düzeltmesi ve tarama destekler.  
  
-   **32-bit BMP:** olmayan WPF denetimleri için. Ayrıca XP ya da yüksek renk, 32-bit BMP alfa kanal saydamlık true renk görüntüsüyle bir RGB/A görüntü biçimi olarak da adlandırılır. Alfa kanal bir bit eşlem (Dördüncü) bir ek olarak içinde sonra kaydedilmiş Adobe Photoshop belirtilen saydamlığı katmanıdır renk kanalı. Siyah bir arka plan resmi üretim renk derinliği hakkında hızlı bir görsel ipucu sağlamak için tüm dosyalara 32-bit BMP sırasında eklenir. Bu siyah arka plan kullanıcı Arabiriminde çıkışı maskelenecek alanını temsil eder.  
  
-   **32-bit ICO:** proje simgeleri ve öğesi Ekle. 32-bit true alfa kanal saydamlık renkle tüm ICO dosyalardır (RGB/A). ICO dosyaları birden çok boyut ve renk derinliğinde depolayabileceğiniz Vista simgeler genellikle 16 x 16 ve 32 x 32, 48 x 48 ve 256 x 256 görüntü boyutları içeren bir ICO biçimindedir. Windows Explorer'da düzgün görüntülemek için ICO dosyaları kaydedilen her görüntü boyutu için 24 bit ve 8 bit renk derinliği için aşağı gerekir.  
  
-   **XAML:** tasarım yüzeyleriyle ve Windows Donatıcılar için. XAML simgeler ölçeklendirme, döndürme, dosyalama ve saydamlık destekleyen vektör tabanlı görüntü dosyalarıdır. Bunlar, bugün Visual Studio'da ortak değildir ancak kendi esnekliğinde nedeniyle yaygınlaşmaktadır.  
  
-   **SVG**  
  
-   **24 bit BMP:** Visual Studio komut çubuğu için. True renk RGB görüntü biçimi 24 bit BMP alta gizleme kullanıma saydamlık katmanı için renk anahtar olarak macenta (R = 255, G = 0, B = 255) kullanarak bir katman saydamlık oluşturur simgesi kuraldır. 24 bit BMP içinde arka plan rengini kullanarak tüm macenta yüzeyleri görüntülenir.  
  
-   **24 bit GIF:** Visual Studio komut çubuğu için. Saydamlığı destekleyen true renk RGB görüntü biçimi. GIF dosyaları genellikle Sihirbazı resmi ve GIF animasyonları kullanılır.  
  
### <a name="icon-construction"></a>Simge oluşturma  
 Visual Studio'da en küçük simge boyutu 16 x 16 ' dir. En büyük ortak kullanım 32 x 32'dir. Tüm 16 x 16, 24 x 24 veya 32 x 32 çerçevesi simge tasarlarken değil doldurmaya göz önünde bulundurun. Okunabilir ve Tekdüzen simge yapım kullanıcı tanıma için gereklidir. Aşağıdaki noktalarına simgeler oluştururken uyması.  
  
-   Simgeler, Temizle, anlaşılabilir ve tutarlı olması gerekir.  
  
-   Tek simgeler olarak durumunu bildirim öğeleri kullanın ve bunları yığın simgesi temel öğenin üzerine değil daha iyi olur. Bazı bağlamlarda UI temel bir öğesiyle eşleştirilmek üzere durum öğesi gerektirebilir.  
  
-   Proje simgeler genellikle çeşitli boyutlarda içeren .ico dosyalarıdır. Yalnızca 16 x 16, 24 x 24 ve 32 x 32 simgelerini güncelleştiriliyor. Çoğu 16 x 16 ve 24 x 24 simgeleri aynı öğeleri içerir. 32 x 32 simgeler proje dil türüne uygun olduğu gibi daha ayrıntılı bilgiler içerir.  
  
-   32 x 32 simgelerini temel öğeler, genellikle 2-piksel çizgi kalınlığı sahiptir. 1 veya 2 piksel çizgi kalınlığı ayrıntı öğeler için kullanılabilir. En iyi sağduyunuzu, daha uygun olduğunu belirlemek için kullanın.  
  
-   16 x 16 için öğeleri ve 24 x 24 simgeleri arasında en az bir 1 piksel boşluk var. 2-piksel aralığı ve değiştirici ile temel öğe öğeleri arasındaki 32 x 32 simgelerini kullanın.  
  
 ![Simgeler 16 x 16, 24 x 24 ve 32 x 32 boyutta için öğe aralığı](../../extensibility/ux-guidelines/media/0404-47_elementspacing.png "0404 47_ElementSpacing")<br />Öğe aralığı simgeler için 16 x 16, 24 x 24 ve 32 x 32 boyutlu
  
#### <a name="color-and-accessibility"></a>Renk ve erişilebilirlik  
 Visual Studio uyumluluk yönergelerine üründeki tüm simgeleri renk ve karşıtlık erişilebilirlik gereksinimleri geçmesini gerektirir. Bu simge ters çevirmeyi sağlanır ve tasarlarken, bunlar programlı olarak üründe ters farkında olmalıdır.  
  
 Visual Studio simgeleri renk kullanarak daha fazla bilgi için bkz: [Renk görüntülerini kullanarak](../../extensibility/ux-guidelines/images-and-icons-for-visual-studio.md#BKMK_UsingColorInImages).  
  
##  <a name="BKMK_UsingColorInImages"></a>Renk görüntüleri kullanma  
  
### <a name="overview"></a>Genel Bakış  
 Visual Studio'da öncelikle tek renkli simgelerdir. Renk belirli bilgileri iletmek için ayrılmıştır ve düzenlemesi için hiçbir zaman. Renk kullanılır:  
  
-   bir eylem belirtmek için  
  
-   Uyarı durumu bildirimi kullanıcıya  
  
-   Dil ilişkisi atamak için  
  
-   IntelliSense içinde öğeleri ayırt etmek için  
  
### <a name="accessibility"></a>Erişilebilirlik  
 Visual Studio uyumluluk yönergelerine tüm simgeleri renk ve karşıtlık erişilebilirlik gereksinimleri ürün geçişinde işaretli gerektirir. Görsel dil palet renklerini, test edilmiş ve bu gereksinimleri karşılayan.  
  
#### <a name="color-inversion-for-dark-themes"></a>Koyu Temalar için renk ters çevirme  
 Visual Studio koyu tema içinde doğru Karşıtlık oranıyla görünür simgeleri yapmak için bir ters çevirmeyi program aracılığıyla uygulanır. Böylece doğru çevir bu kılavuzdaki renkleri kısmen seçildi. Renk kullanımınız için bu paletin kısıtlayabilir veya ters çevirmeyi uygulandığında öngörülemeyen sonuçlara alırsınız.  
  
 ![Kendi renkleri ters beklendiğinden simgeleri örnekleri](../../extensibility/ux-guidelines/media/0405-01_darkthemeinversion.png "0405 01_DarkThemeInversion")<br />Kendi renkleri ters beklendiğinden simgeleri örnekleri
  
### <a name="base-palette"></a>Temel paleti  
 Tüm standart simgeleri üç temel renkleri içerir. Simgeler hiçbir gradyan içeren veya 3B aracı simgeler için bir veya iki istisnalar gölgeleri bırakılamıyor.  
  
|Kullanım|Ad|Değer (açık tema)|Renk örneği|Örnek|  
|-----------|----------|---------------------------|------------|-------------|  
|Arka plan/koyu|VS BG|424242 / 66,66,66|![Renk örneği 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|![Temel palet örnek](../../extensibility/ux-guidelines/media/0405-02_basepaletteexample.png "0405 02_BasePaletteExample")|  
|Ön plan/hafif|VS FG|F0EFF1 / 240,239,241|![Renk örneği F0EFF1](../../extensibility/ux-guidelines/media/0405_f0eff1.png "0405_F0EFF1")||  
|Anahat|VS çıkışı|F6F6F6 / 246,246,246|![Renk örneği F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")||  
  
 Ek olarak temel renkler, her bir simgeyi genişletilmiş paletinden bir ek renk içerebilir.  
  
### <a name="extended-palette"></a>Genişletilmiş paleti  
  
#### <a name="action-modifiers"></a>Eylem Değiştiriciler  
 Aşağıdaki dört renkleri Eylem Değiştiriciler tarafından gerekli eylemleri türlerini belirtin:  
  
|Kullanım|Ad|Değer (tüm temalar)|Renk örneği|  
|-----------|----------|--------------------------|------------|  
|Pozitif|VS eylem yeşil|388A34 / 56,138,52|![Renk örneği 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|Negatif|VS eylem kırmızı|A1260D / 161,38,13|![Renk örneği A1260D](../../extensibility/ux-guidelines/media/0405_a1260d.png "0405_A1260D")|  
|Nötr|VS eylem mavi|00539C / 0,83,156|![Renk örneği 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|/ Yeni Oluştur|VS eylem turuncu|C27D1A / 194,156,26|![Renk örneği C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|  
  
##### <a name="examples"></a>Örnekler  
 Yeşil "Ekle" gibi pozitif Eylem Değiştiriciler için kullanıldığından "Çalışma," "Kullan" ve "Doğrula."  
  
|||||  
|-|-|-|-|  
|![Çalıştır simgesi](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "0405 03_ActionModifierRun")<br />Çalıştır|![Sorgu simgesi yürütme](../../extensibility/ux-guidelines/media/0405-04_executequery.png "0405 04_ExecuteQuery")<br />Sorgu yürütme|![Tüm adımlar simgesinin yürütmek](../../extensibility/ux-guidelines/media/0405-05_playallsteps.png "0405 05_PlayAllSteps")<br />Tüm adımları Yürüt|![Denetim simgesi ekleme](../../extensibility/ux-guidelines/media/0405-06_addcontrol.png "0405 06_AddControl")<br />Denetim ekleme|  
  
 Kırmızı ","Durdur"Delete"gibi negatif Eylem Değiştiriciler için kullanılan "İptal" ve "Kapatın."  
  
|||||  
|-|-|-|-|  
|![Sil ilişki simgesi](../../extensibility/ux-guidelines/media/0405-07_deleterelationship.png "0405 07_DeleteRelationship")<br />İlişkiyi sil|![Sil sütun simgesi](../../extensibility/ux-guidelines/media/0405-08_deletecolumn.png "0405 08_DeleteColumn")<br />Sütun Sil|![Stop sorgu simgesi](../../extensibility/ux-guidelines/media/0405-09_stopquery.png "0405 09_StopQuery")<br />Sorguyu Durdur|![Bağlantı çevrimdışı simgesi](../../extensibility/ux-guidelines/media/0405-10_connectionoffline.png "0405 10_ConnectionOffline")<br />Çevrimdışı bağlantı|  
  
 Mavi değiştiricileri en yaygın olarak ","İleri","Önceki,"Aç"gibi okları gösterilen "Al" ve "Ver." nötr eyleme uygulanan  
  
|||||  
|-|-|-|-|  
|![Alan simgesi gidin](../../extensibility/ux-guidelines/media/0405-11_gotofield.png "0405 11_GoToField")<br />Alanına gidin|![Onay &#45; toplu hale simgesi](../../extensibility/ux-guidelines/media/0405-12_batchedcheckin.png "0405 12_BatchedCheckIn")<br />Toplu iade etme|![Adres Düzenleyicisi simgesinin](../../extensibility/ux-guidelines/media/0405-13_addresseditor.png "0405 13_AddressEditor")<br />Adres Düzenleyicisi|![İlişkilendirme Düzenleyicisi simgesi](../../extensibility/ux-guidelines/media/0405-14_associationeditor.png "0405 14_AssociationEditor")<br />İlişkilendirme Düzenleyicisi|  
  
 Koyu Altın öncelikle "Yeni" değiştiricisi için kullanılır.  
  
|||||  
|-|-|-|-|  
|![Yeni Proje simgesi](../../extensibility/ux-guidelines/media/0405-15_newproject.png "0405 15_NewProject")<br />Yeni Proje|![Yeni bir grafik simge oluşturma](../../extensibility/ux-guidelines/media/0405-16_createnewgraph.png "0405 16_CreateNewGraph")<br />Yeni bir grafik oluşturma|![Yeni birim testi simgesi](../../extensibility/ux-guidelines/media/0405-17_newunittest.png "0405 17_NewUnitTest")<br />Yeni birim testi|![Yeni liste öğesi simgesi](../../extensibility/ux-guidelines/media/0405-18_newlistitem.png "0405 18_NewListItem")<br />Yeni liste öğesi|  
  
#### <a name="special-cases"></a>Özel durumlar  
 Özel durumlarda renkli eylem değiştirici bağımsız olarak tek başına simgesi olarak kullanılabilir. Simge için kullanılan renk simgesi ile ilişkili eylemler yansıtır. Bu simgeler de dahil olmak üzere, küçük bir kısmı sınırlıdır:  
  
||||||  
|-|-|-|-|-|  
|![Çalıştır simgesi](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "0405 03_ActionModifierRun")<br />Çalıştır|![Stop simgesi](../../extensibility/ux-guidelines/media/0405-19_stop.png "0405 19_Stop")<br />Durdur|![Sil simgesi](../../extensibility/ux-guidelines/media/0405-20_delete.png "0405 20_Delete")<br />Sil|![Kaydet simgesine](../../extensibility/ux-guidelines/media/0405-21_save.png "0405 21_Save")<br />Kaydet|![Geri simgesi gidin](../../extensibility/ux-guidelines/media/0405-22_navigateback.png "0405 22_NavigateBack")<br />Geri gidin|  
  
### <a name="code-hierarchy-palette"></a>Kod hiyerarşi paleti  
  
#### <a name="folder"></a>Klasör  
  
|Kullanım|Ad|Değer (tüm temalar)|Renk örneği|Örnek|  
|-----------|----------|--------------------------|------------|-------------|  
|Klasörleri|Klasör|DCB67A / 220,182,122|![Renk örneği DCB67A](../../extensibility/ux-guidelines/media/0405_dcb67a.png "0405_DCB67A")|![Klasör renk simgesi](../../extensibility/ux-guidelines/media/0405-23_foldercolor.png "0405 23_FolderColor")|  
  
#### <a name="visual-studio-languages"></a>Visual Studio dilleri  
 Her ortak diller veya platformlar Visual Studio'da kullanılabilir ilişkili bir renk olur. Bu renkleri temel simgesine veya bileşik simgeler sağ üst köşesinde görüntülenen Dil değiştiricileri kullanılır.  
  
|Kullanım|Ad|Değer (tüm temalar)|Renk örneği|  
|-----------|----------|--------------------------|------------|  
|ASP, HTML, WPF|ASP HTML WPF mavi|0095D 7 / 0,149,215|![Renk örneği 0095 D 7](../../extensibility/ux-guidelines/media/0405_0096d7.png "0405_0096D7")|  
|C++|CPP mor|9B4F96 / 155,79,150|![Renk örneği 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|  
|C#|CS yeşil (VS eylem yeşil)|388A34 / 56,138,52|![Renk örneği 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|CSS|CSS kırmızı|BD1E2D / 189,30,45|![Renk örneği BD1E2D](../../extensibility/ux-guidelines/media/0405_bd1e2d.png "0405_BD1E2D")|  
|F#|FS mor|672878 / 103,40,120|![Renk örneği 672878](../../extensibility/ux-guidelines/media/0405_672878.png "0405_672878")|  
|JavaScript|JS turuncu|F16421 / 241,100,33|![Renk örneği F16421](../../extensibility/ux-guidelines/media/0405_f16421.png "0405_F16421")|  
|VB|VB mavi (VS eylem mavi)|00539C / 0,83,156|![Renk örneği 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|TypeScript|TS turuncu|E04C06 / 224,76,6|![Renk örneği E04C06](../../extensibility/ux-guidelines/media/0405_e04c06.png "0405_E04C06")|  
|Python|PY yeşil|879636 / 135,150,54|![Renk örneği 879636](../../extensibility/ux-guidelines/media/0405_879636.png "0405_879636")|  
  
##### <a name="examples-of-icons-with-language-modifiers"></a>Dil değiştiricileri simgelerle örnekleri  
  
|||||||  
|-|-|-|-|-|-|  
|![Visual Basic simgesi](../../extensibility/ux-guidelines/media/0405-25_vb.png "0405 25_VB")<br />VB|![C &#35; simge](../../extensibility/ux-guidelines/media/0405-26_csharp.png "0405 26_CSharp")<br />C#|![C# 43; &#43; simge](../../extensibility/ux-guidelines/media/0405-27_cplusplus.png "0405 27_CPlusPlus")<br />C++|![F &#35; simge](../../extensibility/ux-guidelines/media/0405-28_fsharp.png "0405 28_FSharp")<br />F#|![JavaScript simgesi](../../extensibility/ux-guidelines/media/0405-29_javascript.png "0405 29_JavaScript")<br />JavaScript|![Python simgesi](../../extensibility/ux-guidelines/media/0405-30_python.png "0405 30_Python")<br />Python|  
|![HTML simge](../../extensibility/ux-guidelines/media/0405-31_html.png "0405 31_HTML")<br />HTML|![WPF simgesi](../../extensibility/ux-guidelines/media/0405-32_wpf.png "0405 32_WPF")<br />WPF|![ASP simgesi](../../extensibility/ux-guidelines/media/0405-33_asp.png "0405 33_ASP")<br />ASP|![CSS simgesi](../../extensibility/ux-guidelines/media/0405-34_css.png "0405 34_CSS")<br />CSS|![TypeScript simgesi](../../extensibility/ux-guidelines/media/0405-35_typescript.png "0405 35_TypeScript")<br />TypeScript||  
  
#### <a name="intellisense"></a>IntelliSense  
 Özel renk paletini IntelliSense simgelerini kullanın. Bu renkleri IntelliSense açılan listesinde farklı öğeleri arasında hızlı bir şekilde ayırmak için kullanıcılara yardımcı olmak için kullanılır.  
  
|Kullanım|Ad|Değer (tüm temalar)|Renk örneği|  
|-----------|----------|--------------------------|------------|  
|Sınıf, olay|VS eylem turuncu|C27D1A / 194,125,26|![Renk örneği C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|  
|Genişletme yöntemi, yöntem, modül temsilcisi|VS eylem mor|652D 90 / 101,45,144|![Renk örneği 652D 90](../../extensibility/ux-guidelines/media/0405_652d90.png "0405_652D90")|  
|Arabirimi alan, liste öğesi, makrosu, yapısı işlecini bileşim değer türü|VS eylem mavi|00539C / 0,83,156|![Renk örneği 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|Nesne|VS eylem yeşil|388A34 / 56,138,52|![Renk örneği 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|Sabit, özel durum, liste öğesi, harita, harita öğesi, Namespace, şablon, tür tanımı|Arka plan (VS BG)|424242 / 66,66,66|![Renk örneği 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|  
  
##### <a name="examples-of-intellisense-icons"></a>IntelliSense simgeleri örnekleri  
  
||||||  
|-|-|-|-|-|  
|![IntelliSense sınıf simgesi](../../extensibility/ux-guidelines/media/0405-36_intellisenseclass.png "0405 36_IntelliSenseClass")<br />örneği|![IntelliSense özel olay simgesi](../../extensibility/ux-guidelines/media/0405-37_intellisenseprivateevent.png "0405 37_IntelliSensePrivateEvent")<br />Özel olay|![IntelliSense temsilci simgesi](../../extensibility/ux-guidelines/media/0405-38_intellisensedelegate.png "0405 38_IntelliSenseDelegate")<br />Temsilci|![IntelliSense yöntemi arkadaş simgesi](../../extensibility/ux-guidelines/media/0405-39_intellisensemethodfriend.png "0405 39_IntelliSenseMethodFriend")<br />Arkadaş yöntemi|![Alan simgesi](../../extensibility/ux-guidelines/media/0405-40_field.png "0405 40_Field")<br />Alan|  
|![IntelliSense korumalı enum öğesi simgesi](../../extensibility/ux-guidelines/media/0405-41_intellisenseprotectedenumitem.png "0405 41_IntelliSenseProtectedEnumItem")<br />Korumalı Enum öğesi|![IntelliSense nesne simgesi](../../extensibility/ux-guidelines/media/0405-42_intellisenseobject.png "0405 42_IntelliSenseObject")<br />Nesne|![IntelliSense şablon simgesi](../../extensibility/ux-guidelines/media/0405-43_intellisensetemplate.png "0405 43_IntelliSenseTemplate")<br />Şablon|![IntelliSense özel kısayol simgesini](../../extensibility/ux-guidelines/media/0405-44_intellisenseexceptionshortcut.png "0405 44_IntelliSenseExceptionShortcut")<br />Özel durum kısayol||  
  
### <a name="notifications"></a>Bildirimler  
 Visual Studio bildirimleri durumunu belirtmek için kullanılır. Bildirim palet siyah veya beyaz ön plan dolgu seçeneklerini yanı sıra aşağıdaki dört renk aşağıdaki durum düzeyleri ile bildirimleri tanımlamak için kullanır.  
  
|Kullanım|Ad|Değer (tüm temalar)|Renk örneği|  
|-----------|----------|--------------------------|------------|  
|Durum: nötr|Bildirim mavi (VS mavi)|1BA1E2 / 27,161,226|![Renk örneği 1BA1E2](../../extensibility/ux-guidelines/media/0405_1ba1e2.png "0405_1BA1E2")|  
|Durum: pozitif|Bildirim yeşil (VS yeşil)|339933 / 51,153,51|![Renk örneği 339933](../../extensibility/ux-guidelines/media/0405_339933.png "0405_339933")|  
|Durum: negatif|Bildirim kırmızı (VS kırmızı)|E51400 / 229,20,0|![Renk örneği E51400](../../extensibility/ux-guidelines/media/0405_e51400.png "0405_E51400")|  
|Durum: uyarı|Bildirim sarı (VS turuncu)|FFCC00 / 255,204,0|![Renk örneği FFCC00](../../extensibility/ux-guidelines/media/0405_ffcc00.png "0405_FFCC00")|  
|Ön plan doldurma|Bildirim siyah (siyah)|000000 / 0,0,0|![Renk örneği &#35; 000000](../../extensibility/ux-guidelines/media/0405_000000.png "0405_000000")|  
|Ön plan doldurma|Bildirim beyaz (beyaz)|FFFFFF / 255,255,255|![Renk örneği FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
  
#### <a name="examples-of-notification-icons"></a>Bildirim simgelerini örnekleri  
  
|||||  
|-|-|-|-|  
|![Uyarı simgesi](../../extensibility/ux-guidelines/media/0405-45_alert.png "0405 45_Alert")<br />Uyarı|![Uyarı simgesi](../../extensibility/ux-guidelines/media/0405-48_warning.png "0405 48_Warning")<br />Uyarı|![Tam simgesi](../../extensibility/ux-guidelines/media/0405-46_complete.png "0405 46_Complete")<br />Tamamlayın|![Stop simgesi](../../extensibility/ux-guidelines/media/0405-47_stop.png "0405 47_Stop")<br />Durdur|  
  
### <a name="visual-studio-online"></a>Visual Studio Team Services  
 Genel olarak, Visual Studio Online, tarayıcıda barındırılan özellikleri oluşur. Farklı ortamlarda rengi değişir, ancak stil aynı kalır.  
  
|Grup|Kullanım|Ad|Değer (tüm temalar)|Renk örneği|  
|-----------|-----------|----------|--------------------------|------------|  
|TFS|Arka Plan|TFSO BG|656565/ 101, 101, 101|![Renk örneği 656565](../../extensibility/ux-guidelines/media/0405_656565.png "0405_656565")|  
|TFS|Anahat|TFSO ÇIKIŞI|FFFFFF / 255, 255 255|![Renk örneği FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|Napa|Arka Plan|Beyaz|FFFFFF / 255, 255 255|![Renk örneği FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|Monaco|Arka Plan|Beyaz|FFFFFF / 255, 255 255|![Renk örneği FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|F12|Arka Plan|Beyaz|FFFFFF / 255, 255 255|![Renk örneği FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|F12|Normal|F12 Grey_Primary|555555 / 85, 85, 85|![Renk örneği 555555](../../extensibility/ux-guidelines/media/0405_555555.png "0405_555555")|  
|F12|Vurgulu|F12 Blue_Hover|2279BF / 34,121,191|![Renk örneği 2279BF](../../extensibility/ux-guidelines/media/0405_2279bf.png "0405_2279BF")|  
|F12|Devre dışı|F12 LtGrey_Disabled|ABABAC / 171,171,172|![Renk örneği ABABAC](../../extensibility/ux-guidelines/media/0405_ababac.png "0405_ABABAC")|  
|F12|Arka plan getirin|BG getirin|D9EBF7 / 217,235,247|![Renk örneği D9EBF7](../../extensibility/ux-guidelines/media/0405_d9ebf7.png "0405_D9EBF7")|  
|F12|Basılı arka plan|Basılı bg|B2D7F0 / 178,215,240|![Renk örneği B2D7F0](../../extensibility/ux-guidelines/media/0405_b2d7f0.png "0405_B2D7F0")|  
|F12|Anahat|VS ÇIKIŞI|F6F6F6 / 246,246,246|![Renk örneği F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")|  
|F12|Bilgiler|Bilgiler|00BCF2 / 0,188,242|![Renk örneği 00BCF2](../../extensibility/ux-guidelines/media/0405_00bcf2.png "0405_00BCF2")|  
|F12|Uyarı|Uyarı|F28300 / 242,131,0|![Renk örneği F28300](../../extensibility/ux-guidelines/media/0405_f28300.png "0405_F28300")|  
|F12|Hata / negatif|Error_Negative|E81123 / 232,17,35|![Renk örneği E81123](../../extensibility/ux-guidelines/media/0405_e81123.png "0405_E81123")|  
|F12|Başlat / pozitif|Start_Positive|009E49 / 0,158,73|![Renk örneği 009E49](../../extensibility/ux-guidelines/media/0405_009e49.png "0405_009E49")|  
|F12|Kesme türü|Kesme türü|9B4F96 / 155,79,150|![Renk örneği 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|  
|F12|Olay işareti|Olay işareti|A51F00 / 165,31,0|![Renk örneği A51F00](../../extensibility/ux-guidelines/media/0405_a51f00.png "0405_A51F00")|  
|F12|Kullanıcı işareti|Kullanıcı işareti|F16220 / 241,98,32|![Renk örneği F16220](../../extensibility/ux-guidelines/media/0405_f16220.png "0405_F16220")|  
  
#### <a name="examples-of-visual-studio-online-icons"></a>Visual Studio Online simgeleri örnekleri  
  
|TFS çevrimiçi||||  
|----------------|-|-|-|  
|![TFS çevrimiçi takım simgesi](../../extensibility/ux-guidelines/media/0405-49_tfsonlineteam.png "0405 49_TFSOnlineTeam")<br />Online ekibi|![TFS bilgi simgesi](../../extensibility/ux-guidelines/media/0405-50_tfsinformation.png "0405 50_TFSInformation")<br />Bilgiler|![TFS geçmişi simgesi](../../extensibility/ux-guidelines/media/0405-51_tfshistory.png "0405 51_TFSHistory")<br />Geçmiş|![TFS şube simgesi](../../extensibility/ux-guidelines/media/0405-52_tfsbranch.png "0405 52_TFSBranch")<br />Dal|  
  
|Napa||||  
|----------|-|-|-|  
|![Napa içerik simgesi](../../extensibility/ux-guidelines/media/0405-53_napacontent.png "0405 53_NapaContent")<br />İçerik|![Napa office posta simgesi](../../extensibility/ux-guidelines/media/0405-54_napaofficemail.png "0405 54_NapaOfficeMail")<br />Office posta|![Napa SharePoint simgesini](../../extensibility/ux-guidelines/media/0405-55_napasharepoint.png "0405 55_NapaSharePoint")<br />SharePoint|![Napa görev bölmesi simgesi](../../extensibility/ux-guidelines/media/0405-56_napataskpane.png "0405 56_NapaTaskPane")<br />Görev bölmesi|  
  
|Monaco||||  
|------------|-|-|-|  
|![Monaco dosyalar simgesi](../../extensibility/ux-guidelines/media/0405-57_monacofiles.png "0405 57_MonacoFiles")<br />Dosyalar|![Monaco Git simgesi](../../extensibility/ux-guidelines/media/0405-58_monacogit.png "0405 58_MonacoGit")<br />Git|![Monaco arama simgesine](../../extensibility/ux-guidelines/media/0405-59_monacosearch.png "0405 59_MonacoSearch")<br />Ara|![Monaco metin simgesi](../../extensibility/ux-guidelines/media/0405-60_monacotext.png "0405 60_MonacoText")<br />Metin|  
  
|F12|||  
|---------|-|-|  
|![F12 asıl kod simgesini](../../extensibility/ux-guidelines/media/0405-61_f12prettycode.png "0405 61_F12PrettyCode")<br />Asıl kodu|![F12 uyarı simgesi](../../extensibility/ux-guidelines/media/0405-62_f12warning.png "0405 62_F12Warning")<br />Uyarı|![F12 öykünmek simgesi](../../extensibility/ux-guidelines/media/0405-63_f12emulate.png "0405 63_F12Emulate")<br />Öykünme|