---
title: Düzenleyici içinde | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - architecture
ms.assetid: 822cbb8d-7ab4-40ee-bd12-44016ebcce81
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 181a414d4cf1b9def941f32560d41158c0ed92fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="inside-the-editor"></a>İçinde Düzenleyicisi
Metin görünümü ve kullanıcı arabirimi düzenleyici metin modeli ayrı tutmak için tasarlanmış farklı alt sistemleri sayısının Düzenleyicisi oluşur.  
  
 Bu bölümlerde Düzenleyicisi farklı yönlerini açıklanmaktadır:  
  
-   [Alt sistemleri genel bakış](../extensibility/inside-the-editor.md#overview)  
  
-   [Metin modeli](../extensibility/inside-the-editor.md#textmodel)  
  
-   [Metin görünümü](../extensibility/inside-the-editor.md#textview)  
  
 Bu bölümlerde Düzenleyicisi özellikleri:  
  
-   [Etiketleri ve sınıflandırıcı](../extensibility/inside-the-editor.md#tagsandclassifiers)  
  
-   [Adornments](../extensibility/inside-the-editor.md#adornments)  
  
-   [Projeksiyon](../extensibility/inside-the-editor.md#projection)  
  
-   [Anahat Oluşturma](../extensibility/inside-the-editor.md#outlining)  
  
-   [Fare bağlamaları](../extensibility/inside-the-editor.md#mousebindings)  
  
-   [Düzenleyici işlemleri](../extensibility/inside-the-editor.md#editoroperations)  
  
-   [IntelliSense](../extensibility/inside-the-editor.md#intellisense)  
  
##  <a name="overview"></a> Alt sistemleri genel bakış  
  
### <a name="text-model-subsystem"></a>Metin Model alt sistemi  
 Metin model alt metin temsil eden ve onun işleme etkinleştirme sorumludur. Metin model alt içeren <xref:Microsoft.VisualStudio.Text.ITextBuffer> Düzenleyicisi tarafından görüntülenecek olan karakter dizisi açıklar arabirimi. Bu metin değiştirilebilir, izlenen ve aksi takdirde birçok yolla değiştirilebilir. Metin modeli türleri için aşağıdaki konuları da sağlar:  
  
-   Metin dosyaları ile ilişkilendirir ve okuma ve dosya sistemindeki yazma yöneten bir hizmet.  
  
-   En az iki sıraları nesnelerin farklarını bulur bir fark kayıt hizmeti.  
  
-   Metin arabelleği diğer arabellekleri metinde kümelerine bakımından açıklayan bir sistem.  
  
 Metin model alt sistemi, kullanıcı arabirimi (UI) kavramlarını ücretsizdir. Örneğin, metin biçimlendirme veya metin düzenini sorumlu değildir ve metni ile ilişkili visual adornments olanağıyla sahiptir.  
  
 Metin model alt sisteminin genel tür yalnızca .NET Framework temel sınıf kitaplığını ve Yönetilen Genişletilebilirlik Çerçevesi (MEF) bağlı Microsoft.VisualStudio.Text.Data.dll ve Microsoft.VisualStudio.CoreUtilitiy.dll, yer alır.  
  
### <a name="text-view-subsystem"></a>Metin görünümü alt sistemi  
 Metin görünümü alt sistemi, biçimlendirme ve metin görüntüleme sorumludur. Bu alt sistemi türlerinde olup türleri Windows Presentation Foundation (WPF) kullanan bağlı olarak iki katmanlara ayrılır. En önemli türleri <xref:Microsoft.VisualStudio.Text.Editor.ITextView> ve <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>, görüntülenecek metin satırlarını kümesini ve ayrıca düzeltme işareti, seçim ve WPF kullanıcı Arabirimi öğeleri kullanarak metin eklemek için tesis denetim. Bu alt sistemi, metnin kenar boşluklarını görüntüleme alanı de sağlar. Bu kenar boşluklarını genişletilebilir ve farklı türde içerik ve görsel efektler içerebilir. Satır numarası görüntüler ve kaydırma çubukları kenar boşluklarını örnekleridir.  
  
 Metin görünümü alt genel türleri Microsoft.VisualStudio.Text.UI.dll ve Microsoft.VisualStudio.Text.UI.Wpf.dll yer alır. İlk derleme platformdan bağımsız öğelerini içeren ve ikinci WPF özgü öğeler içerir.  
  
### <a name="classification-subsystem"></a>Sınıflandırma alt sistemi  
 Sınıflandırma alt sistemi, metin yazı tipi özelliklerini belirlemek için sorumludur. Bir sınıflandırıcı, örneğin, "anahtar" veya "comment" olmak üzere farklı sınıflar metni keser. Örneğin, gerçek yazı tipi özelliklerine sınıflandırma biçim eşlemesi bu sınıfların ilişkili "mavi Consolas 10 pt". Bu bilgiler biçimlendirir ve metin işler metin görünüm tarafından kullanılır. Etiketleme, bu konunun ilerleyen bölümlerinde daha ayrıntılı anlatılan sağlar metin yayılma ile ilişkilendirilecek veri.  
  
 Genel türler sınıflandırma alt sisteminin Microsoft.VisualStudio.Text.Logic.dll içinde yer alır ve Microsoft.VisualStudio.Text.UI.Wpf.dll içinde bulunan sınıflandırma görsel yönlerini etkileşim.  
  
### <a name="operations-subsystem"></a>Operations alt sistemi  
 Operations alt sistemi Düzenleyicisi davranışını tanımlar. Visual Studio Düzenleyici komutları uygulamasını ve geri alma sistemi sağlar.  
  
## <a name="a-closer-look-at-the-text-model-and-the-text-view"></a>Metin modeli ve metin görünümü yakından inceleyin  
  
###  <a name="textmodel"></a> Metin modeli  
 Metin model alt metin türleri farklı gruplandırmaları oluşur. Bunlar, metin arabelleği, metin anlık görüntüler ve metin yayılma içerir.  
  
#### <a name="text-buffers-and-text-snapshots"></a>Metin arabelleği ve metin anlık görüntüleri  
 <xref:Microsoft.VisualStudio.Text.ITextBuffer> Arabirimi temsil eder, kodlama tarafından kullanılan olan UTF-16 kullanılarak kodlanan bir Unicode karakter dizisi `String` .NET Framework türü. Bir metin arabelleği bir dosya sistemi belgesi olarak kalıcı, ancak bu zorunlu değildir.  
  
 <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService> Boş metin arabelleğini ya da bir dize ya da başlatılmamış bir metin arabelleği oluşturmak için kullanılan <xref:System.IO.TextReader>. Dosya sistemi olarak için metin arabelleği kalıcı bir <xref:Microsoft.VisualStudio.Text.ITextDocument>.  
  
 Bir iş parçacığı metin arabelleğinin çağırarak aittir kadar metin arabelleği hiçbir iş parçacığı tarafından düzenlenebilir <xref:Microsoft.VisualStudio.Text.ITextBuffer.TakeThreadOwnership%2A>. Bundan sonra yalnızca o iş parçacığı düzenlemeler gerçekleştirebilirsiniz.  
  
 Bir metin arabelleği birçok sürümleri yaşam süresi boyunca gidebilirsiniz. Yeni bir sürüm arabellek düzenlenebilir her zaman ve sabit bir oluşturulan <xref:Microsoft.VisualStudio.Text.ITextSnapshot> arabellek sürümünün içeriğini temsil eder. Metin anlık görüntüleri değişmez olduğundan değiştirmek temsil ettiği metin arabelleğini devam olsa bile, kısıtlama olmadan tüm iş parçacığı üzerinde metin anlık görüntü erişebilir.  
  
#### <a name="text-snapshots-and-text-snapshot-lines"></a>Metin anlık görüntüler ve metin anlık görüntü satırları  
 Bir karakter dizisi veya bir dizi satır olarak bir metin anlık görüntü içeriğini görüntüleyebilirsiniz. Karakterler ve satırlar her ikisi de sıfırda başlangıç dizini görünüyor. Boş metin anlık görüntü sıfır karakter ve bir boş satır içerir. Bir satır, tüm geçerli Unicode satır sonu karakter dizisi veya başında ve sonunda arabellek tarafından sınırlandırılır. Satır sonu karakterleri açıkça metin anlık temsil edilir ve satır sonları metin anlık görüntüdeki tümü aynı olması gerekir.  
  
> [!NOTE]
>  Visual Studio düzenleyicisinde satır sonu karakterleri hakkında daha fazla bilgi için bkz: [Kodlamalar ve satır sonları](../ide/encodings-and-line-breaks.md).  
  
 Metin satırının tarafından temsil edilen bir <xref:Microsoft.VisualStudio.Text.ITextSnapshotLine> belirli satır numarası veya belirli bir karakterin metin anlık penceresinden nesne.  
  
#### <a name="snapshotpoints-snapshotspans-and-normalizedsnapshotspancollections"></a>SnapshotPoints, SnapshotSpans ve NormalizedSnapshotSpanCollections  
 A <xref:Microsoft.VisualStudio.Text.SnapshotPoint> bir anlık görüntü içinde karakterin konumu temsil eder. Konumu sıfır ve anlık görüntü uzunluğu arasında sağlanır. A <xref:Microsoft.VisualStudio.Text.SnapshotSpan> bir anlık görüntü metin aralığını temsil eder. Bitiş konumunu sıfır ve anlık görüntü uzunluğu arasında sağlanır. <xref:Microsoft.VisualStudio.Text.NormalizedSnapshotSpanCollection> Kümesinden oluşur <xref:Microsoft.VisualStudio.Text.SnapshotSpan> aynı anlık görüntü nesneleri.  
  
#### <a name="spans-and-normalizedspancollections"></a>Yayılımları ve NormalizedSpanCollections  
 A <xref:Microsoft.VisualStudio.Text.Span> metin metin anlık görüntüdeki uygulanabilir bir aralık temsil eder. Yayılma sıfır dahil olmak üzere herhangi bir konumda başlatılabilmesi için anlık görüntü konumlar sıfır tabanlı,. `End` Bir aralık özelliği için toplamını eşittir kendi `Start` özelliği ve kendi `Length` özelliği. A `Span` tarafından dizine karakteri içermeyen `End` özelliği. Örneğin, başlangıç bir aralık = 5 ve uzunluğu = 3 olan son = 8, ve 5, 6 ve 7 konumlarda karakterleri içerir. Bu aralık için gösterim 5..8 şeklindedir).  
  
 Bunlar tüm pozisyonlar ortak, bitiş konumu dahil olmak üzere varsa, iki yayılma kesiştiği. Bu nedenle, kesişimi [3, 5) ve [2, 7) olan [3, 5) ve kesişimi [3, 5) ve [5, 7) olduğundan [5, 5). (Dikkat [5, 5) boş bir aralığın olan.)  
  
 Bunlar konumlar ortak dışında bitiş konumu varsa iki yayılma çakışıyor. Boş bir aralığın hiçbir zaman başka bir aralık çakışıyor ve iki yayılma çakışmasını hiçbir zaman boştur.  
  
 A <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> yayılma yayılma başlangıç özelliklerini sırasına göre listelenmiştir. Listede, çakışan veya bitişik yayılma birleştirilir. Örneğin, yayılma kümesi verilen [5..9), [0..1), [3..6), ve [9..10), yayılma normalleştirilmiş listesi [0..1), [3..10).  
  
#### <a name="itextedit-textversion-and-text-change-notifications"></a>ITextEdit, TextVersion ve metin değişikliği bildirimleri  
 Bir metin arabelleği içeriğini kullanarak değiştirilebilir bir <xref:Microsoft.VisualStudio.Text.ITextEdit> nesnesi. Böyle bir nesne oluşturma (birini kullanarak `CreateEdit()` yöntemlerinin <xref:Microsoft.VisualStudio.Text.ITextBuffer>) metin düzenlemeleri oluşan bir metin hareket başlatır. Her düzenleme bazı yayılma bir dizeyle arabelleğinde metin alanının yerini almıştır. İşlem başlatıldığında koordinatları ve her düzenleme içeriği arabellek anlık görüntü göre ifade edilir. <xref:Microsoft.VisualStudio.Text.ITextEdit> Nesnesi aynı işlemde başka düzenlemeler etkilenir düzenlemeleri koordinatlarını ayarlar.  
  
 Örneğin, bu dizeyi içeren bir metin arabelleği göz önünde bulundurun:  
  
```  
abcdefghij  
```  
  
 İki düzenlemeler, aralık adresindeki değiştiren bir düzen içeren bir işlem uygulayın [2..4) karakter kullanarak `X` ve konumundaki aralık değiştirir ikinci bir düzenleme [6..9) karakter kullanarak `Y`. Bu arabelleğin oluşur:  
  
```  
abXefYj  
```  
  
 İlk düzenleme uygulanmadan koordinatları ikinci düzenleme için işlem başlangıcında arabellek içeriğini göre hesaplanan.  
  
 Arabellek yapılan değişiklikler etkili zaman <xref:Microsoft.VisualStudio.Text.ITextEdit> nesne kaydedilmiş çağırarak kendi `Apply()` yöntemi. En az bir boş olmayan düzenleme, yoksa yeni bir <xref:Microsoft.VisualStudio.Text.ITextVersion> , yeni bir oluşturulur <xref:Microsoft.VisualStudio.Text.ITextSnapshot> oluşturulan ve bir `Changed` olayı oluşturulur. Her metin farklı bir sürümde metin anlık görüntü. Metin anlık bir düzen işlem sonra tam metin arabelleği durumunu temsil eder, ancak bir metin sürümü yalnızca bir anlık görüntü'dan sonraki değişiklikler açıklanmaktadır. Genel olarak, metin anlık görüntüler bir kez kullanılması amaçlanmıştır ve atılan, metin sürümleri için biraz zaman canlı kalması gereken sırada.  
  
 Bir metin sürümünü içeren bir <xref:Microsoft.VisualStudio.Text.INormalizedTextChangeCollection>. Bu koleksiyon değişiklikleri açıklar, anlık görüntüye uygulandığında sonraki anlık görüntü oluşturur. Her <xref:Microsoft.VisualStudio.Text.ITextChange> koleksiyonda karakterin değişikliği değiştirilen dize ve değiştirme dizesini içerir. Değiştirilen dize için bir temel ekleme boştur ve değiştirme dizesini temel silme işlemi için boştur. Normalleştirilmiş her zaman koleksiyonudur `null` metin arabelleği en son sürümü için.  
  
 Yalnızca bir <xref:Microsoft.VisualStudio.Text.ITextEdit> nesne oluşturulabilir metin arabelleği için herhangi bir zamanda ve tüm metin düzenlemeleri (sahipliği istenmişti değilse), metin arabelleği sahip iş parçacığında gerçekleştirilmesi gerekir. Bir metin düzenleme çağırarak terk, `Cancel` yöntemi veya kendi `Dispose` yöntemi.  
  
 <xref:Microsoft.VisualStudio.Text.ITextBuffer> Ayrıca sağlar `Insert()`, `Delete()`, ve `Replace()` olanlar benzer yöntemleri bulunan <xref:Microsoft.VisualStudio.Text.ITextEdit> arabirimi. Bunlar çağırma oluşturma aynı etkiye sahip bir <xref:Microsoft.VisualStudio.Text.ITextEdit> nesne benzer araması yapmadan ve düzenleme uygulanıyor.  
  
#### <a name="tracking-points-and-tracking-spans"></a>Noktaları izleme ve yayılma izleme  
 Bir <xref:Microsoft.VisualStudio.Text.ITrackingPoint> bir karakterin metin arabelleği temsil eder. Arabellek kaydırılacak karakterin neden olan bir şekilde düzenlenirse, izleme noktası ile kayar. Örneğin, bir izleme noktası arabellek konumunu 10 belirtir ve beş karakter arabellek başında eklenir, izleme noktası sonra 15 konuma başvuruyor. Tam olarak izleme noktası tarafından belirtilen konumdaki bir ekleme meydana gelirse davranışını tarafından belirlenen kendi <xref:Microsoft.VisualStudio.Text.PointTrackingMode>, hangi olabilir ya da `Positive` veya `Negative`. İzleme Modu İzleme noktası ekleme sonunda sunulmuştur aynı karakterin başvuruyor pozitifse; İzleme Modu negatifse, özgün konumunda ilk eklenen karakter İzleme noktası başvuruyor. Bir izleme noktası tarafından temsil edilen konumunda bulunan karakteri silinirse, izleme noktası silinen aralığın izleyen ilk karakter kayar. Örneğin, bir izleme noktası 5 konumunda bulunan karakteri başvuruyor ve 3'ten 6 konumlarda karakterler silinir, izleme noktası 3 konumunda bulunan karakteri ifade eder.  
  
 Bir <xref:Microsoft.VisualStudio.Text.ITrackingSpan> bir aralıktaki karakterleri yerine yalnızca bir konumu temsil eder. Davranışını tarafından belirlenen kendi <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>. Aralık izleme modu ise <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, aralık izleme modu ise kendi kenarlarında; eklenen metin eklemenizi izleme aralık büyür <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, izleme aralık kendi kenarlarında eklenen metin dahil değildir. Ancak, aralık izleme modu ise <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, bir ekleme geçerli konumu başlangıç doğru iter ve aralık izleme modu <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, geçerli konumu sonuna doğru bir ekleme iter.  
  
 İzleme noktasının konumunu veya izleme yayılma alanının yayılma için metin arabelleğinin ait oldukları herhangi bir anlık görüntü elde edebilirsiniz. Güvenli bir şekilde noktaları izleme ve yayılma izleme herhangi bir iş parçacığından başvurulabilir.  
  
#### <a name="content-types"></a>İçerik türleri  
 İçeriği farklı türde tanımlamak için bir mekanizma içerik türleridir. Bir içerik türü "metin", "code" veya "ikili" gibi bir dosya türü veya "xml", "vb" veya "c#" gibi bir teknoloji türü olabilir. Örneğin, word "kullanarak" hem C# ve Visual Basic, ancak diğer programlama dillerinin bir anahtar sözcüktür. Bu nedenle, bu anahtar sözcük tanımı "c#" ve "vb" içerik türleri için sınırlı olacaktır.  
  
 İçerik türleri adornments ve diğer öğeleri Düzenleyicisi için bir filtre olarak kullanılır. Birçok Düzenleyicisi özellikleri ve uzantı noktaları içerik türü tanımlanmadı; Örneğin, metin renklendirme düz metin dosyaları, XML dosyalarını ve Visual Basic kaynak kodu dosyaları için farklıdır. Metin arabelleği, genellikle oluşturuldukları ve bir metin arabelleği içerik türü değiştirilebilir bir içerik türü atanır.  
  
 İçerik türleri birden çok-diğer içerik türlerinden devralabilirsiniz. <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> Verilen bir içerik türü üst birden çok taban türleri belirtmenize olanak sağlar.  
  
 Geliştiriciler kendi içerik türlerini tanımlayın ve bunları kullanarak kaydedin <xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>. Birçok Düzenleyicisi özelliklerini kullanarak belirli bir içerik türüne göre tanımlanabilir <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>. Belirli içerik türlerini görüntüleyen düzenleyicileri geçerli olacak şekilde, örneğin, düzenleyici kenar boşlukları, adornments ve fare işleyicileri tanımlanabilir.  
  
###  <a name="textview"></a> Metin görünümü  
 Model görünümü denetleyici (MVC) deseni görünüm parçası biçimlendirme görünümü, grafik öğeleri kaydırma çubuğu ve düzeltme işareti gibi metin görünümü, tanımlar. Visual Studio düzenleyicisinde tüm sunu öğelerini, WPF temel alır.  
  
#### <a name="text-views"></a>Metin görünümleri  
 <xref:Microsoft.VisualStudio.Text.Editor.ITextView> Metin görünümü platformdan bağımsız gösterimini bir arabirimdir. Öncelikle bir pencerede metin belgeleri görüntülemek için kullanılır, ancak bu aynı zamanda başka bir amaçla Örneğin, bir araç ipucunda kullanılabilir.  
  
 Metin görünümü metin arabelleği farklı türde başvurur. <xref:Microsoft.VisualStudio.Text.Editor.ITextView.TextViewModel%2A> Özelliği başvurduğu bir <xref:Microsoft.VisualStudio.Text.Editor.ITextViewModel> bu üç farklı metin arabellekleri işaret nesnesi: üst veri düzeyi arabellek hangi düzenleme oluşur ve olduğu arabellek visual arabellek düzenleme arabelleği veri arabelleği metin görünümünde görüntülenir.  
  
 Metin alttaki metin arabelleğini bağlı sınıflandırıcı göre biçimlendirilmiş ve metin görünümü kendisine bağlı adornment sağlayıcılarını kullanarak donatılan.  
  
#### <a name="the-text-view-coordinate-system"></a>Metin görünümü koordinat sistemi  
 Metin görünümü koordinat sistemi metin görünümünde konumları belirtir. Bu koordinat sistemi x değeri 0,0 görüntülenen metnin sol köşesine karşılık gelir ve y değeri 0,0 görüntülenen metnin üst köşesine karşılık gelir. X koordinatını soldan sağa artırır ve y koordinatını üstten alta artırır.  
  
 Dikey olarak kaydırılan gibi bir Görünüm penceresi (metin penceresinde görünür metin parçası) aynı şekilde yatay kaydırılan olamaz. Bir görünüm penceresinin sol kendi koordinat çizim yüzeyini göre hareket değiştirerek yatay kaydırılan. Ancak, bir görünüm penceresinin dikey neden İşlenmiş metin yalnızca değiştirerek kaydırılabileceğini bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> çıkarılmasına olay.  
  
 Koordinat sistemi uzaklıklar mantıksal piksel karşılık gelir. Metin işleme yüzeyi ölçeklendirme dönüştürme gösterilirse, ardından bir metin işleme koordinat sistemi biriminde ekranındaki bir piksel karşılık gelir.  
  
#### <a name="margins"></a>Kenar boşlukları  
 <xref:Microsoft.VisualStudio.Text.Editor.ITextViewMargin> Arabirimi kenar boşluğu temsil eder ve denetim kenar boşluklarını ve boyutuna görünürlüğü sağlar. "Üst", "Sol", "Sağ" ve "Alt" adlı ve üst, alt, sol veya sağ kenarı bir görünümün bağlı dört önceden tanımlanmış kenar vardır. Bu kenar boşlukları başka kenar boşluklarını yerleştirilebilir kapsayıcılardır. Arabirim kenar boşluğu boyutu ve kenar boşlukları görünürlüğünü döndüren yöntemleri tanımlar. Kenar boşlukları bağlı olan metin Görünüm hakkında ek bilgiler sağlayan visual öğelerdir. Örneğin, satır numarası kenar boşluğu metin görünümü için satır numaralarını görüntüler. Karakter kenar boşluğu UI öğelerini görüntüler.  
  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMarginProvider> Arabirimi oluşturma ve kenar boşlukları yerleşimini işler. Kenar boşlukları başka kenar boşluklarını göre sıralanabilir. Daha yüksek öncelikli kenar boşluklarını metni görünümüne bir yakın bulunur. Örneğin, iki sol kenar, kenar boşluğuna ve kenar boşluğu B vardır ve kenar boşluğu B kenar boşluğuna daha düşük önceliğe sahipse, kenar boşluğu A. sol kenar boşluğu B görünür  
  
#### <a name="the-text-view-host"></a>Metin görünümü konak  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> Metin görünümü ve görünüm, örneğin, kaydırma çubukları eşlik herhangi bitişik düzenlemelerinin arabirimi içerir. Metin görünümü ana görünümün kenarlık bağlı kenar boşluklarını de içerir.  
  
#### <a name="formatted-text"></a>Biçimlendirilmiş metin  
 Bir metin görünümünde görüntülenen metin oluşan <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> nesneleri. Her metin görünümü satır bir metin görünümünde metin satırı karşılık gelir. Temel metin arabelleği uzun satırları ya da kısmen (sözcük kaydırma etkin değilse) örtülü veya birden çok metin görünümü satırlarına bozuk. <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> Yöntemleri ve özellikleri içeren satırı ilişkilendirilebilir adornments ve koordinatları ve karakter arasında eşleme için arabirimi içerir.  
  
 <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> nesneleri kullanılarak oluşturulan bir <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource> arabirimi. Yalnızca şu anda görünümünde görüntülenen metin hakkında endişeleriniz biçimlendirme kaynağını yoksayabilirsiniz. Değil metin biçiminde ilgileniyorsanız (örneğin desteklenmesi için zengin metin kesme ve yapıştırma,), görünümünde görüntülenen kullanabileceğiniz <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource> biçimi Text metin arabelleği.  
  
 Metin görünümü bir biçimleri <xref:Microsoft.VisualStudio.Text.ITextSnapshotLine> birer birer.  
  
## <a name="editor-features"></a>Düzenleyicisi özellikleri  
 Düzenleyici özelliklerini özellik tanımını kendi uygulamasından ayrı şekilde tasarlanmıştır. Düzenleyici, şu özellikleri içerir:  
  
-   Etiketleri ve sınıflandırıcı  
  
-   Adornments  
  
-   Projeksiyon  
  
-   Anahat Oluşturma  
  
-   Fare ve anahtar bağlamaları  
  
-   İşlemler ve temelleri  
  
-   IntelliSense  
  
###  <a name="tagsandclassifiers"></a> Etiketleri ve sınıflandırıcı  
 Bir metin aralığı ile ilişkili işaretçileri etiketleridir. Bunlar farklı şekilde, örneğin, metin renklendirme, alt çizgiler, grafik veya açılır pencereleri kullanılarak sunulabilir. Sınıflandırıcı etiketi bir tür var.  
  
 Diğer etiketler türleridir <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> metni vurgulama için <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> anahat için ve <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag> derleme hataları.  
  
#### <a name="classification-types"></a>Sınıflandırma türleri  
 Bir <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType> arabirimi soyut bir kategori metnin bir eşdeğer sınıfı temsil eder. Sınıflandırma türleri birden çok-diğer sınıflandırma türlerinden devralabilirsiniz. Örneğin, dil sınıflandırmaları programlama "anahtar", "comment" ve "tanımlayıcı", "code" devralan tüm hangi içerebilir. Doğal dil sınıflandırma türleri "isim", "eylem" ve "gelen", "doğal dili" devralan tüm hangi içerebilir.  
  
#### <a name="classifications"></a>Sınıflandırmalar  
 Bir sınıflandırma belirli sınıflandırma türü genellikle bir metin aralığını örneğidir. A <xref:Microsoft.VisualStudio.Text.Classification.ClassificationSpan> bir sınıflandırmasını temsil etmek için kullanılır. Sınıflandırma span, belirli bir metin aralığını kapsayan ve belirli sınıflandırma türü bu aralığa metin sistemi söyleyen bir etiket düşünülebilir.  
  
#### <a name="classifiers"></a>Sınıflandırıcı  
 Bir <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> sınıflandırmaları kümesine metni keser bir mekanizmadır. Sınıflandırıcı belirli içerik türleri için tanımlanır ve belirli bir metni arabellekleri için örneği. İstemcileri uygulanmalı <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> metin sınıflandırmasında katılmayı.  
  
#### <a name="classifier-aggregators"></a>Sınıflandırıcı toplayıcısını  
 Bir sınıflandırıcı toplayıcısı sınıflandırmaları tek kümesine bir metin arabelleği için tüm sınıflandırıcı birleştiren bir mekanizmadır. Örneğin, C# sınıflandırıcı ve İngilizce dil sınıflandırıcı C# dosyasında bir yorum üzerinden sınıflandırmalar oluşturabilirsiniz. Bu açıklama göz önünde bulundurun:  
  
```  
// This method produces a classifier  
```  
  
 Bir C# sınıflandırıcı bir açıklama olarak tüm aralık etiket ve İngilizce dil sınıflandırıcı "üretir" "eylem" ve "isim" olarak "yöntemi" olarak sınıflandırmak. Toplayıcı çakışmayan sınıflandırmaları kümesi üretir ve küme türü üzerinde tüm Katkıları dayanır.  
  
 Sınıflandırmaları kümesine metni keser sınıflandırıcı toplayıcısı ayrıca bir sınıflandırıcı olmasıdır. Sınıflandırıcı toplayıcısı ayrıca hiçbir çakışan sınıflandırmaları olduğunu ve sınıflandırmalar sıralanır sağlar. Tek tek sınıflandırıcı sınıflandırmaları, herhangi bir kümesi herhangi bir sırada döndürmek ücretsiz ve herhangi bir şekilde çakışan.  
  
#### <a name="classification-formatting-and-text-coloring"></a>Sınıflandırma biçimlendirme ve metin renklendirme  
 Metni Biçimlendirme metin sınıflandırmasına yerleşik bir özelliği bir örnektir. Metin görünümü katman tarafından bir uygulama içindeki metnin görüntülenmesi belirlemek için kullanılır. Metin biçimlendirme alanı WPF bağlıdır, ancak sınıflandırmaları mantıksal tanımı değil.  
  
 Belirli sınıflandırma türü için properties biçimlendirme kümesi bir sınıflandırma biçimidir. Bu biçimler sınıflandırma türünde üst biçiminden devralır.  
  
 Bir <xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMap> sınıflandırma türünden eşlemesi özellikleri biçimlendirme metin bir dizi. Biçim eşlemesi Düzenleyicisi'nde uygulama sınıflandırma biçimlerinin tüm dışarı işler.  
  
###  <a name="adornments"></a> Adornments  
 Adornments doğrudan karakterler metin görünümü, renk ve yazı tipi ilişkili grafik efektleri ' dir. Örneğin, bir katıştırılmış adornment derleme olmayan kod pek çok programlama dillerinde işaretlemek için kullanılan kırmızı dalgalı alt çizgi olan ve açılır adornments araç ipuçları şunlardır. Adornments türetilir <xref:System.Windows.UIElement> ve uygulamanıza <xref:Microsoft.VisualStudio.Text.Tagging.ITag>. İki özel türleridir adornment etiketinin <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>, metin bir görünüm olarak aynı alan kaplar adornments için ve <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>, dalgalı alt çizgi için.  
  
 Katıştırılmış adornments biçimlendirilmiş metin görünümü parçasını grafikler durumdadır. Bunlar farklı Z düzeni katmanlarında düzenlenir. Üç yerleşik katmanı vardır: metin, düzeltme işareti ve seçim. Ancak, geliştiricilerin daha fazla katman tanımlayın ve bunları sırayla birbirine göre yerleştirin. Üç katıştırılmış adornments (metin silindiğinde, silinen metni taşındığında taşıma ve misiniz) metin göreli adornments, (hangi görünümü metin dışı bölümleriyle yapmak zorunda) görünüm göreli adornments ve sahibi tarafından denetlenen adornments (türleridir Geliştirici yatırımlarından yönetmeniz gerekir).  
  
 Açılır adornments metin görünümü, örneğin, araç ipuçları yukarıda küçük bir pencere görünür grafikler durumdadır.  
  
###  <a name="projection"></a> Yansıtma  
 Projeksiyon, farklı türde bir metin gerçekten depolamaz, ancak bunun yerine diğer metin arabelleği metinden birleştirir metin arabelleğini oluşturmak için kullanılan bir tekniktir. Örneğin, bir yansıtma arabellek iki arabelleğini metinden birleştirmek ve onu yalnızca bir arabellek ise sonucu sunmak için ya da bir arabellek metinde parçalarını gizlemek için kullanılabilir. Projeksiyon arabellek kaynak arabelleği başka bir yansıtma arabellek olarak çalışabilir. Projeksiyon tarafından ilgili arabellekleri kümesi metin birçok farklı yolla yeniden düzenlemek için oluşturulabilir. (Böyle bir küme olarak da bilinen olan bir *arabellek grafik*.) Visual Studio metin anahat özelliği daraltılmış metin gizlemek için bir yansıtma arabellek kullanılarak uygulanır ve Visual Basic ve C# gibi katıştırılmış dilleri desteklemek için yansıtma ASP.NET sayfaları için Visual Studio Düzenleyicisi'ni kullanır.  
  
 Bir <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBuffer> kullanılarak oluşturulan <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBufferFactoryService>. Projeksiyon arabellek sıralı bir dizi tarafından temsil edilen <xref:Microsoft.VisualStudio.Text.ITrackingSpan> olarak bilinen nesneleri *kaynak yayılma*. Bu yayılma içeriğini bir karakter dizisi sunulur. İçinden kaynak yayılma çizilir metin arabelleği adlı *kaynak arabelleklerini*. Projeksiyon arabellek istemcileri bir normal metin arabelleğinden farklı haberdar olmanız gerekmez.  
  
 Projeksiyon arabellek kaynak arabelleklerini metin değişikliği olaylarını dinler. Bir kaynak metinde span değiştiğinde, projeksiyon arabellek değiştirilen metin koordinatları kendi koordinat eşler ve uygun metin değişikliği olayları başlatır. Örneğin, bu içeriğe sahip olan kaynak arabelleklerini A ve B göz önünde bulundurun:  
  
```  
A: ABCDE  
B: vwxyz  
```  
  
 İki metin yayılma bir arabellek bir ve tümü olduğu diğer tüm arabellek B sahip projeksiyon arabellek P biçimlendirildiğinden, P aşağıdaki içeriğe sahip:  
  
```  
P: ABCDEvwxyz  
```  
  
 Varsa alt dizeyi `xy` arabellek P 7 ve 8 konumlarda karakterleri silindi belirten bir olay başlatır sonra B arabelleğinden silinir.  
  
 Projeksiyon arabellek de doğrudan düzenlenebilir. Uygun kaynak arabelleklerini düzenlemeler yayar. Örneğin, bir dize arabellek P 6 (özgün konum karakter "v") konumunda eklenir, arabellek B 1 konumunda ekleme yayılır.  
  
 Bir yansıtma arabellek katkıda kaynak yayılma kısıtlamalar vardır. Kaynak yayılma çakışmaması; projeksiyon arabellek bir konumda herhangi kaynak arabelleği birden fazla konumda eşlenemez ve kaynak arabelleği bir konumda bir yansıtma arabellek birden fazla konumda eşlenemez. Hiçbir circularities kaynak arabelleği ilişkisinde izin verilir.  
  
 Kaynak kümesi projeksiyon arabellek değişiklikleri ve kaynak kümesi değişiklikleri yayıldığında arabelleği, olaylar oluşturulur.  
  
 Bir elision arabellek projeksiyon arabellek özel türüdür. Öncelikle, anahat oluşturma ve genişletme ve daraltma metin bloklarını işlemleri için kullanılır. Bir elision arabellek yalnızca bir kaynak arabelleği temel alır ve kaynak arabellekte sıralanmış olarak elision arabelleği yayılma aynı sıralanmış olmaları gerekmektedir.  
  
##### <a name="the-buffer-graph"></a>Arabellek grafiği  
 <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraph> Arabirimi bir yansıtma arabellekleri grafik arasında eşleme sağlar. Tüm metin arabelleği ve projeksiyon arabellek çok dil derleyici tarafından üretilen soyut söz dizimi ağaç gibi yönlendirilmiş Çevrimsiz grafik toplanır. Grafik tüm metin arabelleğini olabilecek üst arabellek tarafından tanımlanır. Arabellek grafik kaynak arabelleği bir noktasına üst arabelleği bir noktasından veya üst arabelleği kaynak arabelleği yayılma kümesi için bir aralık eşleyebilirsiniz. Benzer şekilde, eşleme bir noktası veya kaynak arabelleğinden bir noktayı üst arabelleği span yükleyebilir. Arabellek grafikleri kullanarak oluşturulur <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraphFactoryService>.  
  
##### <a name="events-and-projection-buffers"></a>Olaylar ve projeksiyon arabellekler  
 Projeksiyon arabellek değiştirildiğinde, değişikliklerin bağımlı arabellekleri projeksiyon arabelleğinden gönderilir. Tüm arabellekler değiştiren sonra derin arabellekten başlayarak arabellek değişiklik olaylar oluşturulur.  
  
###  <a name="outlining"></a> Anahat oluşturma  
 Anahat oluşturma genişletmek veya daraltmak için farklı bir metin görünümünde metin bloklarını yeteneğidir. Anahat oluşturma türü tanımlanmış, <xref:Microsoft.VisualStudio.Text.Tagging.ITag>, aynı şekilde adornments belirtildiği şekilde. A <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> genişletilmiş veya daraltılmış metin bölge tanımlayan bir etiket. Anahat oluşturma kullanmak için içeri aktarmanız gerekir <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManagerService> almak için bir <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManager>. Anahat Yöneticisi sıralar, daraltır ve olarak temsil edilir farklı bloklar genişletir <xref:Microsoft.VisualStudio.Text.Outlining.ICollapsible> nesneleri ve olayları buna uygun olarak başlatır.  
  
###  <a name="mousebindings"></a> Fare bağlamaları  
 Fare bağlamaları fare hareketleri farklı komutları bağlayın. Fare bağlamalar kullanılarak tanımlanmış bir <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessorProvider>, ve anahtar bağlamalar kullanılarak tanımlanmış bir <xref:Microsoft.VisualStudio.Text.Editor.IKeyProcessorProvider>. <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> Otomatik olarak tüm bağlamaları oluşturur ve fare olayları görünümünde bağlanır.  
  
 <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessor> Arabirimi farklı fare olayları için önceden işlem ve işlem sonrası olay işleyicileri içerir. Bazı yöntemleri geçersiz olaylardan biri için tanıtıcı <xref:Microsoft.VisualStudio.Text.Editor.MouseProcessorBase>.  
  
###  <a name="editoroperations"></a> Düzenleyici işlemleri  
 Düzenleyici işlemleri otomatikleştirmek için komut dosyası Düzenleyicisi veya başka amaçlarla etkileşim için kullanılabilir. İçeri aktarabilirsiniz <xref:Microsoft.VisualStudio.Text.Operations.IEditorOperationsFactoryService> erişim işlemleri için bir verilen <xref:Microsoft.VisualStudio.Text.Editor.ITextView>. Sonra bu nesneleri seçimi değiştirmek, görünümü kaydırma veya şapka görünümü farklı bölümlerine taşımak için de kullanabilirsiniz.  
  
###  <a name="intellisense"></a> IntelliSense  
 Deyim tamamlama, imza Yardım (parametre bilgisi olarak da bilinir), hızlı bilgi ve ampuller IntelliSense destekler.  
  
 Deyim tamamlama yöntemi adları, XML öğeleri ve diğer kodlama veya işaretleme öğeler için olası tamamlamalar açılır listesini sağlar. Genel olarak, bir kullanıcı hareketi tamamlama oturum çağırır. Oturum olası tamamlamalar listesini görüntüler ve kullanıcının birini seçin veya liste yok sayın. <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker> Oluşturma ve tetikleme sorumlu <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSession>. <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource> Hesaplar <xref:Microsoft.VisualStudio.Language.Intellisense.CompletionSet> oturumu için tamamlama öğelerinin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil hizmeti ve düzenleyici uzantı noktaları](../extensibility/language-service-and-editor-extension-points.md)   
 [Düzenleyici İçeri Aktarımları](../extensibility/editor-imports.md)