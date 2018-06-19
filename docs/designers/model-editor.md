---
title: Model Düzenleyicisi
ms.date: 04/12/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- vs.graphics.designer.3dscene
- vs.graphics.modelviewer
ms.assetid: 5edf1a30-9307-43c3-9b8b-831217be0104
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5353be6e3c02895ce74ff4cf27493f803bb25b4e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31927039"
---
# <a name="model-editor"></a>Model Düzenleyicisi

Bu belge, görüntülemek, oluşturmak ve 3B modeller değiştirmek için Visual Studio Model Düzenleyicisi ile çalışmak açıklar.

Temel 3B modelleri sıfırdan oluşturabilir veya görüntülemek ve tam özellikli 3B modelleme araçları kullanılarak oluşturulmuş olan daha karmaşık 3B modelleri değiştirmek için Model Düzenleyicisi'ni kullanabilirsiniz. Model Düzenleyicisinde kullanılan birkaç 3D modeli DirectX uygulaması geliştirme destekler.

## <a name="supported-formats"></a>Desteklenen biçimler

Model Düzenleyicisinde bu modeli biçimlerini destekler:

|Biçim Adı|Dosya Uzantısı|Desteklenen İşlemler (Görüntüleme, Düzenleme, Oluşturma)|
|-----------------|--------------------|-------------------------------------------------|
|AutoDesk FBX Değişim Dosyası|.fbx|Görüntüleme, Düzenleme, Oluşturma|
|Collada DAE Dosyası|.dae|Görüntüleme, Düzenleme (Collada DAE dosyalarında yapılan değişiklikler FBX biçimi kullanılarak kaydedilir.)|
|OBJ|.obj|Görüntüleme, Düzenleme (OBJ dosyalarında yapılan değişiklikler FBX biçimi kullanılarak kaydedilir.)|

## <a name="get-started"></a>Kullanmaya başlayın

Bu bölümde, Visual Studio projenizi 3D model eklemeyi açıklar ve başlamak için gereken temel bilgileri sağlar.

### <a name="to-add-a-3d-model-to-your-project"></a>Bir 3B modeli projenize eklemek için

1. İçinde **Çözüm Gezgini**, görüntüsüne ekleyin ve ardından istediğiniz proje için kısayol menüsünü açın **Ekle** > **yeni öğe**.

2. İçinde **Yeni Öğe Ekle** iletişim kutusunda **grafik** kategorisi, select **3B Sahne (.fbx)**.

   ![Yeni öğe iletişim seçili 3B Sahne ile ekleme](media/add-new-3d-scene.png)

3. Girin **adı** modeli dosyası ve ardından **Ekle**.

> [!NOTE]
> Görmüyorsanız, **grafik** kategorisinde **Yeni Öğe Ekle** iletişim kutusunda, yüklemeniz gerekebilir **görüntü ve 3B model düzenleyicileri** bileşeni. İletişim kutusunu kapatın ve ardından **Araçları** > **alma araçları ve özelliklerinin** açmak için menü çubuğundan **Visual Studio yükleyicisi**. Seçin **bileşenleri tek tek** sekmesini tıklatın ve ardından **görüntü ve 3B model düzenleyicileri** altında bileşen **oyunları ve grafik** kategorisi. Seçin **değiştirmek**.
>
> ![Görüntü ve 3B modeli düzenleyicileri bileşeni](media/image-3d-model-editors-component.png)
>
> Varsa **görüntü ve 3B model düzenleyicileri** bileşeni yüklü ve hala görmüyorum **grafik** şablon kategorisi, bu kategori, yalnızca belirli proje türleri için görünür Not örneğin konsol uygulamalar.

### <a name="axis-orientation"></a>Eksen yönlendirme

Visual Studio 3B Eksen her yönünü destekler ve destekleyen model dosya biçimlerinden eksen yönlendirme bilgilerini yükler. Eksen yönlendirmesini belirtilmediği takdirde, Visual Studio sağ koordinat sistemi varsayılan olarak kullanır. **Eksen göstergesi** tasarım yüzeyine sağ alt köşesinde geçerli ekseni yönlendirmesini gösterir. Üzerinde **eksen göstergesi**kırmızı x ekseni temsil eder, yeşil y ekseni temsil eder ve mavi z ekseni temsil eder.

### <a name="begin-your-3d-model"></a>3B modelinizi başlayın

Model Düzenleyicisi'nde, her yeni nesne her zaman temel 3B şekiller biri olarak başlar — veya *Temelleri*— Model düzenleyicisine yerleşiktir. Yeni ve benzersiz nesneler oluşturmak için, görünüme bir temel öğe ekler ve sonra da köşeleriyle oynayarak şeklini değiştirirsiniz. Karmaşık şekiller için, kalıp veya alt bölüm kullanarak ek köşeler ekler ve sonra bunlarda değişiklik yaparsınız. Temel bir nesne, Sahne ekleme hakkında daha fazla bilgi için bkz: [oluşturma ve 3B nesneleri içeri aktarma](#Adding3DObjects). Daha fazla köşeleri nesneye ekleme hakkında daha fazla bilgi için bkz: [nesneleri değiştirmeniz](#ModifyingObjects).

## <a name="work-with-the-model-editor"></a>Model Düzenleyicisi ile çalışma

Aşağıdaki bölümlerde Model Düzenleyicisinde 3B modeller ile çalışmak için nasıl kullanılacağı açıklanmaktadır.

### <a name="model-editor-toolbars"></a>Model Düzenleyicisi araç çubukları

Araç çubukları içeren Model Düzenleyicisinde 3D modellerle çalışma yardımcı komutları.

Model Düzenleyicisi'nin durumunu etkileyen komutları bulunur **Model Düzenleyicisinde modu** ana Visual Studio penceresinde araç. Modelleme Araçları ve komut dosyalı komutları bulunur **Model Düzenleyicisinde** Model Düzenleyicisinde tasarım yüzeyine araç.

Burada **Model Düzenleyicisinde modu** araç çubuğu:

![Model Görüntüleyicisi kalıcı araç.](../designers/media/digit-mre-modal-toolbar.png)

Bu tablo üzerinde öğeleri açıklar **Model Düzenleyicisinde modu** araç çubuğu göründükleri soldan sağa doğru sırayla listelenir.

|Araç Çubuğu Öğesi|Açıklama|
|------------------|-----------------|
|**seçin**|Etkin seçim moduna bağlı olarak görünümdeki noktaların, kenarların, yüzeylerin ya da nesnelerin seçimini etkinleştirir.|
|**Pan**|Bir 3B Sahne pencere çerçevesi göre hareketini sağlar. Kaydırmak için görünümde bir nokta seçip dolaştırın.<br /><br /> İçinde **seçin** modu tuşuna basın ve etkinleştirmek için Ctrl basılı **Pan** geçici olarak modu.|
|**Yakınlaştır**|Pencere çerçevesine göre daha az ya da daha fazla görünüm ayrıntısının görüntülenmesini sağlar. İçinde **yakınlaştırma** modu, Görünüm bir nokta seçin ve ardından sağa taşıyın veya yakınlaştırmak için aşağı veya sol veya en fazla yakınlaştırma yetersiz.<br /><br /> İçinde **seçin** modu, yakınlaştırma veya uzaklaştırma, Ctrl tuşuna basılı tutun durumdayken fare tekerleği kullanarak.|
|**Yörünge**|Görünümü seçili nesnenin çevresinde dairesel bir yola yerleştirir. Hiçbir nesne seçili değilse, yol görünüm başlangıcında ortalanır. **Not:** Bu mod sahip olmayan zaman efekt **Dikçizgisel** projeksiyon etkindir.|
|**Uluslararası yerel**|Bu öğe etkin olduğunda, seçili nesne üzerindeki dönüştürmeler dünya uzayında oluşur. Aksi takdirde, seçilen nesne üzerinde dönüştürmeler yerel uzayda oluşur.|
|**Pivot modu**|Bu öğe etkinleştirildiğinde, konumunu ve yönünü dönüşümleri etkileyen *pivot noktası* seçili nesnenin (pivot noktası çevirisi, ölçeklendirme ve döndürme işlemlerinin merkezi tanımlar.) Aksi takdirde dönüştürmeler, pivot noktasına göreli olarak, nesne geometrisinin konumunu ve yönlendirmesini etkiler.|
|**Kilit X ekseni**|Nesne düzenlemesini x ekseni ile sınırlar. Yalnızca işleyici pencere öğesinin orta bölümünü kullandığınızda uygulanır.|
|**Kilit Y ekseni**|Nesne düzenlemesini y ekseni ile sınırlar. Yalnızca işleyici pencere öğesinin orta bölümünü kullandığınızda uygulanır.|
|**Kilit Z ekseni**|Nesne düzenlemesini z ekseni ile sınırlar. Yalnızca işleyici pencere öğesinin orta bölümünü kullandığınızda uygulanır.|
|**Çerçeve nesnesi**|Seçili nesneyi, görünümün ortasında yer alacak şekilde çerçeveler.|
|**Görünümü**|Görünüm yönlendirmesini ayarlar. Kullanılabilir yönlendirmeler şunlardır:<br /><br /> **Ön**<br /> Görünümü sahnenin önüne yerleştirir.<br /><br /> **Geri**<br /> Görünümü sahnenin arkasına yerleştirir.<br /><br /> **Sol**<br /> Görünümü sahnenin soluna yerleştirir.<br /><br /> **Sağ**<br /> Görünümü sahnenin sağına yerleştirir.<br /><br /> **Sayfanın Üstü**<br /> Görünümü sahnenin yukarısına yerleştirir.<br /><br /> **Alt**<br /> Görünümü sahnenin aşağısına yerleştirir. **Not:** görünüm yönünü değiştirmek için tek yolu budur zaman **Dikçizgisel** projeksiyon etkindir.|
|**Projeksiyon**|Sahneyi çizmek için kullanılan projeksiyonun türünü ayarlar. Kullanılabilir projeksiyonlar şunlardır:<br /><br /> **Perspektifi**<br /> Perspektif projeksiyonunda, bakış açısından uzakta olan nesneler boyut olarak daha küçük görünür ve en sonunda uzaktaki bir noktaya doğru birleşir.<br /><br /> **Ortografik**<br /> Ortografik projeksiyonda, bakış açısına olan uzaklıklarına bakılmaksızın nesneler aynı boyutta görünür. Bir yakınlaşma görüntüsü olmaz. Zaman **Dikçizgisel** etkin projeksiyon kullanamaz **Yörünge** görünümü konumlandırmak için modu.|
|**Çizim Stili**|Sahnedeki nesnelerin işlenme yöntemini ayarlar. Kullanılabilir stiller şunlardır:<br /><br /> **Tel Çerçeve**<br /> Etkin olduğunda, nesneler tel çerçeve şeklinde işlenir.<br /><br /> **Overdraw**<br /> Etkin olduğunda, nesneler ek karıştırma kullanılarak işlenir. Görünümde, fazla çekme işleminin ne kadar yapıldığını görselleştirmek için bunu kullanabilirsiniz.<br /><br /> **Düz gölgeli**<br /> Etkin olduğunda, nesneler temel ve düz gölgeli bir aydınlatma modeli kullanılarak işlenir. Bir nesnenin yüzeylerini daha kolay görmek için bunu kullanabilirsiniz.<br /><br /> Bu seçeneklerden hiçbiri etkin değilse, her nesne kendisine uygulanan malzeme kullanılarak işlenir.|
|**Gerçek zamanlı işleme modu**|Gerçek zamanlı işleme etkinleştirildiğinde, Visual Studio tasarım yüzeyi bile herhangi bir kullanıcı eylemi gerçekleştirildiğinde yeniden çizer. Bu mod, zamanla değişen gölgelendiriciler ile çalıştığınızda kullanışlıdır.|
|**Geçiş Kılavuzu**|Bu öğe etkinleştirildiğinde bir kılavuz görüntülenir. Aksi takdirde kılavuz görüntülenmez.|
|**Araç Kutusu**|Alternatif olarak gösterir veya gizler **araç**.|
|**Belge Anahattı**|Alternatif olarak gösterir veya gizler **belge anahattı** penceresi.|
|**Özellikler**|Alternatif olarak gösterir veya gizler **özellikleri** penceresi.|
|**Gelişmiş**|Gelişmiş komutları ve seçenekleri içerir.<br /><br /> **Grafik motorları**<br /><br /> **D3D11 ile işleme**<br /> Model Düzenleyicisi tasarım yüzeyini işlemek için Direct3D 11 kullanır.<br /><br /> **D3D11WARP ile işleme**<br /> Model Düzenleyicisi tasarım yüzeyini işlemek için Direct3D 11 Windows Gelişmiş Pikselleştirme Platformu'nu (WARP) kullanır.<br /><br /> **Sahne Yönetimi**<br /><br /> **İçeri Aktar**<br /> Nesneler için geçerli Sahne başka bir 3B modeli dosyasından içeri aktarır.<br /><br /> **Üst öğeye bağlayın**<br /> Çoklu seçilen nesnelerin ilkini, kalan seçili nesnelerin üst öğesi olarak ayarlar.<br /><br /> **Üst öğeden ayırma**<br /> Seçili nesneyi üst öğesinden ayırır. Seçilen nesne olur bir *kök nesnesi* Sahne içindeki. Kök nesnenin bir üst nesnesi olmaz.<br /><br /> **Grup oluşturma**<br /> Seçili nesneleri eşdüzey nesneler olarak gruplandırır.<br /><br /> **Nesneleri birleştirme**<br /> Seçili nesneleri tek bir nesne halinde birleştirir.<br /><br /> **Çokgen seçimden yeni nesne oluşturma**<br /> Seçilen yüzeyleri geçerli nesneden kaldırır ve bu yüzeyleri içeren yeni bir nesneyi sahneye ekler.<br /><br /> **Araçlar**<br /><br /> **Çokgen sargı ters çevirin**<br /> Seçili çokgenleri çevirir ve böylece sargı sırasını ve yüzey normalini tersine çevirir.<br /><br /> **Tüm animasyon kaldırma**<br /> Nesnelerden animasyon verilerini kaldırır.<br /><br /> **Triangulate**<br /> Seçili nesneyi üçgenlere dönüştürür.<br /><br /> **Görünümü**<br /><br /> Arkayüz Ayrılması<br /> Arka yüz ayırmayı etkinleştirir veya devre dışı bırakır.<br /><br /> **Kare hızı**<br /> Tasarım yüzeyinin sağ üst köşesinde kare hızını görüntüler. Kare hızı, saniye başına çizilen çerçeve sayısıdır.<br /><br /> Bu seçenek, etkinleştirdiğinizde yararlıdır **gerçek zamanlı işleme modunu** seçeneği.<br /><br /> **Tümünü Göster**<br /> Sahnedeki tüm nesneleri gösterir. Bu sıfırlar **gizli** her nesnenin özelliğinin **False**.<br /><br /> **Yüz normalleri Göster**<br /> Her bir yüzeyin normalini gösterir.<br /><br /> **Eksik malzeme Göster**<br /> Atanmış malzemeleri olmayan nesneler üzerinde özel bir doku gösterir.<br /><br /> **Özet Göster**<br /> Etkinleştirir veya görüntülenmesini 3B Eksen işaret etkin seçimi Özet noktada devre dışı bırakır.<br /><br /> **Yer tutucu düğümleri Göster**<br /> Yer tutucu düğümlerini gösterir. Nesneleri gruplandırdığınızda bir yer tutucu düğümü oluşturulur.<br /><br /> **Köşe normalleri Göster**<br /> Her köşenin normalini gösterir. **İpucu:** seçebileceğiniz **betikleri** düğmesi son komut dosyası yeniden çalıştırın.|

Burada **Model Düzenleyicisinde** araç çubuğu:

![Model Görüntüleyici araç çubuğu](../designers/media/digit-mre-toolbar.png)

Öğeleri açıklar ve bir sonraki tabloyu **Model Düzenleyicisinde** göründükleri üstten alta gözüktükleri sırada listelenen araç.

|Araç Çubuğu Öğesi|Açıklama|
|------------------|-----------------|
|**Çevir**|Seçimi taşır.|
|**Ölçek**|Seçimin boyutunu değiştirir.|
|**döndürme**|Seçimi döndürür.|
|**Select noktası**|Ayarlar **seçim modunu** bir nesne üzerinde tek tek noktalarını seçmek için.|
|**Edge seçin**|Ayarlar **seçim modunu** bir nesne üzerinde bir kenarı (iki köşeleri arasında bir çizgi) seçin.|
|**Yüz Seç**|Ayarlar **seçim modunu** bir nesne üzerinde bir yazıtipi seçin.|
|**Nesne seçin**|Ayarlar **seçim modunu** nesnenin tamamı seçin.|
|**Yükselt**|Ek bir yüzey oluşturur ve bunu seçili yüze bağlar.|
|**Ayırabilir**|Seçilen her yüzeyi birden fazla yüzeye böler. Yeni yüzler oluşturmak için, biri özgün yüzün ortasına ve biri de her bir kenarın ortasına olmak üzere yeni köşeler eklenir ve sonra bunlar orijinal köşelerle birleştirilir. Eklenen yüzlerin sayısı, orijinal yüzdeki köşelerin sayısına eşittir.|

### <a name="control-the-view"></a>Denetim Görünüm

3B Sahne, bir konum ve yön sahip sanal bir kamera olarak düşünülebilir görünümü göre işlenir. Yönlendirme ve konumu değiştirmek için görünümü denetimleri kullanın **Model Düzenleyicisinde modu** araç.

Aşağıdaki tabloda birincil görünüm denetimleri açıklanmaktadır.

|Görünüm Denetimi|Açıklama|
|------------------|-----------------|
|**Pan**|Bir 3B Sahne pencere çerçevesi göre hareketini sağlar. Kaydırmak için görünümde bir nokta seçip dolaştırın.<br /><br /> İçinde **seçin** modu tuşuna basın ve etkinleştirmek için Ctrl basılı **Pan** geçici olarak modu.|
|**Yakınlaştır**|Pencere çerçevesine göre daha az ya da daha fazla görünüm ayrıntısının görüntülenmesini sağlar. İçinde **yakınlaştırma** modu, Görünüm bir nokta seçin ve ardından sağa taşıyın veya yakınlaştırmak için aşağı veya sol veya en fazla yakınlaştırma yetersiz.<br /><br /> İçinde **seçin** modu, yakınlaştırma veya uzaklaştırma, Ctrl tuşuna basılı tutun durumdayken fare tekerleği kullanarak.|
|**Yörünge**|Görünümü seçili nesnenin çevresinde dairesel bir yola yerleştirir. Hiçbir nesne seçili değilse, yol görünüm başlangıcında ortalanır. **Not:** Bu mod sahip olmayan zaman efekt **Dikçizgisel** projeksiyon etkindir.|
|**Çerçeve nesnesi**|Seçili nesneyi, görünümün ortasında yer alacak şekilde çerçeveler.|

Görünüm sanal kamera ile belirlenir, ancak aynı zamanda bir projeksiyon ile de tanımlanır. Projeksiyon, görünümdeki şekillerin ve nesnelerin tasarım yüzeyinde piksellere nasıl dönüştürüldüğünü tanımlar. Üzerinde **Model Düzenleyicisinde** araç seçebilirsiniz ya da **perspektif** veya **Dikçizgisel** projeksiyon.

|Projeksiyon|Açıklama|
|----------------|-----------------|
|**Perspektifi**|Perspektif projeksiyonunda, bakış açısından uzakta olan nesneler boyut olarak daha küçük görünür ve en sonunda uzaktaki bir noktaya doğru birleşir.|
|**Ortografik**|Ortografik projeksiyonda, bakış açısına olan uzaklıklarına bakılmaksızın nesneler aynı boyutta görünür. Bir yakınlaşma görüntüsü olmaz. Zaman **Dikçizgisel** etkin projeksiyon kullanamaz **Yörünge** görünümü rasgele konumlandırmak için modu.|

İki benzer Sahne karşılaştırmak istediğiniz zaman bir bilinen konumu ve açı, örneğin, 3B Sahne görüntülemek daha yararlı olabilir. Bu senaryo için, Model Düzenleyicisi önceden tanımlı çeşitli görünümler sağlar. Üzerinde önceden tanımlanmış bir görünümü kullanmak için **Model Düzenleyicisinde modu** araç seçin **Görünüm**ve ardından istediğiniz önceden tanımlanmış görünümü — ön, geri, sol, sağ, üst veya alt. Bu görünümlerde, sanal kamera doğrudan sahnenin başlangıç noktasına doğru bakar. Örneğin, seçtiğiniz **görünüm üst**, Sahne doğrudan yukarıda kökeni sanal kamera bakar.

### <a name="view-additional-geometry-details"></a>Ek geometri ayrıntıları görüntüle

Bir 3B nesne veya Sahne daha iyi anlamak için köşe başına normalleri, yüz başına normalleri, etkin seçimi Özet noktaları gibi ek geometri ayrıntıları ve diğer ayrıntıları görüntüleyebilirsiniz. Etkinleştirmek veya bunları devre dışı bırakmak **Model Düzenleyicisinde** araç seçin **betikleri**, **Görünüm**ve ardından istediğinizi seçin.

### <a name="create-and-import-3d-objects"></a>Oluşturma ve 3B nesneleri içeri aktarma

Sahne için tanımlanmış bir 3B şekle eklemek için **araç**, istediğiniz ve ardından tasarım yüzeyine taşıma birini seçin. Yeni şekiller sahnenin başlangıcına yerleştirilir. Model düzenleyicisinde yedi şekiller sağlar: **koni**, **küp**, **silindir**, **disk**, **düzlem**,  **Küre**, ve **Teapot**.

Bir dosyadan 3B bir nesneyi almak için **Model Düzenleyicisinde** araç seçin **Gelişmiş**, **Sahne Yönetim**, **alma**ve ardından belirtin içeri aktarmak istediğiniz dosyanın.

### <a name="transform-objects"></a>Dönüşüm nesneleri

Yapabilecekleriniz *dönüştürme* değiştirerek bir nesne, **döndürme**, **ölçek**, ve **çeviri** özellikleri. *Döndürme* x ekseni, y ekseni ve onun pivot noktası tarafından tanımlanan z ekseni etrafında art arda döndürmeleri uygulayarak bir nesne yönlendirir. Her döndürme belirtiminin sırasıyla x, y ve z olmak üzere üç bileşeni vardır ve bu bileşenler derece olarak belirtilir. **Ölçeklendirme** bir nesne üzerinde kendi pivot noktası ortalanmış bir veya daha fazla eksen boyunca belirtilen bir faktörüyle yayarak göre yeniden boyutlandırır. *Çeviri* 3 boyutlu alana göre kendi pivot noktası yerine, üst nesnenin bulur.

Modelleme araçlarını kullanarak veya özellikleri ayarlayarak bir nesneyi dönüştürebilirsiniz.

#### <a name="to-transform-an-object-by-using-modeling-tools"></a>Modelleme araçlarını kullanarak bir nesneyi dönüştürmek için

1. İçinde **seçin** modu, dönüştürmek istediğiniz nesne seçin. Tel çerçeve yer paylaşımı nesnenin seçili olduğunu gösterir.

2. Üzerinde **Model Düzenleyicisinde** araç seçin **çevir**, **ölçek**, veya **Döndür** aracı. Seçili nesne için bir çeviri, ölçeklendirme veya döndürme işleyicisi görüntülenir.

3. Dönüştürmeyi gerçekleştirmek için işleyiciyi kullanın. Çeviri ve ölçeklendirme dönüşümlerinde işleyici bir eksen göstergesidir. Bir kerede bir eksen değiştirebilir veya göstergenin ortasındaki beyaz küpü kullanarak aynı anda tüm eksenleri değiştirebilirsiniz. Döndürme için işleyici x eksenine (kırmızı), y eksenine (yeşil) ve z eksenine (mavi) karşılık gelen renk kodlu dairelerden oluşan bir küredir. İstediğiniz döndürmeyi oluşturmak için her ekseni tek tek değiştirmeniz gerekir.

#### <a name="to-transform-an-object-by-setting-its-properties"></a>Özelliklerini ayarlayarak bir nesneyi dönüştürmek için

1. İçinde **seçin** modu, dönüştürmek istediğiniz nesne seçin. Tel çerçeve yer paylaşımı nesnenin seçili olduğunu gösterir.

2. İçinde **özellikleri** penceresinde değerlerini belirtin **döndürme**, **ölçek**, ve **çeviri** özellikleri.

    > [!IMPORTANT]
    > İçin **döndürme** özelliği, her üç eksen etrafında döndürme derecesini belirtin. Döndürmeler sırayla uygulandığından önce x ekseni, sonra y ekseni ve sonra da z ekseni açısından bir döndürme planladığınızdan emin olun.

Modelleme araçlarını kullanarak, dönüştürmeleri hızlı ancak kesin olmayan bir şekilde oluşturabilirsiniz. Nesne özelliklerini ayarlayarak, dönüştürmeleri kesin ancak hızlı olmayan bir şekilde belirtebilirsiniz. İstediğiniz dönüştürmelere "yeteri kadar" yaklaşmak için modelleme araçlarını kullanmanızı ve ardından özellik değerlerinde ince ayar yapmanızı öneririz.

İşleyicileri kullanmayı istemiyorsanız, serbest biçim modunu etkinleştirebilirsiniz. Üzerinde **Model Düzenleyicisinde** araç seçin **betikleri**, **Araçları**, **serbest biçimli işleme** serbest biçimli modunu etkinleştir (veya devre dışı bırakmak için). Serbest biçim modunda, işleyici üzerindeki bir nokta yerine herhangi bir tasarım yüzeyi noktasında düzenleme yapmaya başlayabilirsiniz. Serbest biçim modunda, değiştirmek istemediklerinizi kilitleyerek bazı eksenlerde yapılacak değişiklikleri kısıtlayabilirsiniz. Üzerinde **Model Düzenleyicisinde modu** araç, herhangi bir birleşimini seçin **kilit X**, **kilit Y**, ve **kilit Z** düğmeler.

Kılavuza uydur işlevini kullanarak nesnelerle çalışmayı daha kullanışlı bulabilirsiniz. Üzerinde **Model Düzenleyicisinde modu** araç seçin **Daya** ek kılavuz etkinleştirin (veya devre dışı bırakmak için). Kılavuza uydur etkinleştirildiğinde, çeviri, döndürme ve ölçeklendirme dönüştürmeleri önceden tanımlı aralıklarla sınırlandırılır.

### <a name="work-with-the-pivot-point"></a>Pivot noktası ile çalışma

Pivot noktası nesnenin döndürme ve ölçeklendirme merkezini tanımlar. Döndürme ve ölçeklendirme dönüşümlerinden nasıl etkilendiğini değiştirmek için bir nesnenin özet noktasını değiştirebilirsiniz. Üzerinde **Model Düzenleyicisinde modu** araç seçin **Özet modu** etkinleştir (veya devre dışı) Özet moduna. Pivot modu etkin olduğunda, seçili nesnenin pivot noktasında küçük bir eksen göstergesi görünür. Daha sonra **çeviri** ve **döndürme** pivot noktası yönetmek için Araçlar.

Pivot noktası kullanmak üzere nasıl oluşturulduğunu gösteren bir örnek için bkz: [nasıl yapılır: bir 3B modelin Pivot noktası değiştirmek](../designers/how-to-modify-the-pivot-point-of-a-3-d-model.md).

### <a name="world-and-local-modes"></a>Dünya ve yerel modları

Çevirme ve döndürme oluşabilir ya da yerel koordinat sistemini (veya *yerel çerçeve-in-başvuru*) nesnesinin veya dünya koordinat sistemi (veya *world çerçeve-in-başvuru*). Dünya başvuru çerçevesi nesnenin dönüşünden bağımsızdır. Yerel mod varsayılandır. Etkinleştir (veya devre dışı bırak) için world modu **Model Düzenleyicisinde modu** araç seçin **WorldLocal** düğmesi.

### <a name="modify-objects"></a>Nesneleri değiştirme

Bir 3B nesnesinin şeklini taşıma veya köşeleri, kenarları ve yüzeyleri silme değiştirebilirsiniz. Varsayılan olarak, Model Düzenleyicisinde bulunduğu *nesne modu*, böylece seçin ve tüm nesneleri dönüştürme. Noktaları, kenarları veya yüzeyleri seçmek için uygun seçim modunu seçin. Üzerinde **Model Düzenleyicisinde modu** araç seçin **seçim modları**ve ardından istediğiniz modu seçin.

 Çıkarmayla veya alt bölümlere ayırmayla ek köşeler oluşturabilirsiniz. Çıkarma bir yüzün köşelerini (aynı düzlemli bir yüzler kümesi) çoğaltır ve yüz çoğaltılmış köşelerle bağlı kalır. Alt bölümlere ayırma, önceden bir tane olan yüzeyden birçok yüzey oluşturmak için köşeler ekler. Yeni yüzler oluşturmak için, biri özgün yüzün ortasına ve biri de her bir kenarın ortasına olmak üzere yeni köşeler eklenir ve sonra bunlar orijinal köşelerle birleştirilir. Eklenen yüzlerin sayısı, orijinal yüzdeki köşelerin sayısına eşittir. Her iki durumda da, nesnenin geometrisini değiştirmek için yeni köşeleri çevirebilir, döndürebilir ve ölçeklendirebilirsiniz.

#### <a name="to-extrude-a-face-from-an-object"></a>Bir nesneden bir yüzü çıkarmak için

1. Yüz seçimi modunda, çıkarmak istediğiniz yüzü seçin.

2. Üzerinde **Model Düzenleyicisinde** araç seçin **betikleri**, **Araçları**, **Yükselt**.

#### <a name="to-subdivide-faces"></a>Yüzleri alt bölümlere ayırmak için

1. Yüz seçimi modunda, alt bölümlere ayırmak istediğiniz yüzleri seçin. Alt bölüm yeni kenar verileri oluşturduğundan, tüm yüzeyleri aynı anda alt bölümlere ayırmak yüzler bitişik olduğunda daha tutarlı sonuçlar verir.

2. Üzerinde **Model Düzenleyicisinde** araç seçin **betikleri**, **Araçları**, **Subdivide**.

 Ayrıca yüzeyleri üçgenlere bölebilir, nesneleri birleştirebilir ve çokgen seçimlerini yeni nesnelere dönüştürebilirsiniz. Üçgenlere bölme, üçgen olmayan bir yüz, en uygun sayıda üçgene dönüştürülecek şekilde ek kenarlar oluşturur; ancak ek geometrik ayrıntı sağlamaz. Birleştirme işlemi, seçili nesneleri tek bir nesne halinde birleştirir. Yeni nesneler bir çokgen seçiminden oluşturulabilir.

#### <a name="to-triangulate-a-face"></a>Bir yüzü üçgenlere bölmek için

1. Yüz seçimi modunda, üçgenlere bölmek istediğiniz yüzü seçin.

2. Üzerinde **Model Düzenleyicisinde** araç seçin **betikleri**, **Araçları**, **Triangulate**.

#### <a name="to-merge-objects"></a>Nesneleri birleştirmek için

1. Nesne seçimi modunda, birleştirmek istediğiniz nesneleri seçin.

2. Üzerinde **Model Düzenleyicisinde** araç seçin **betikleri**, **Araçları**, **birleştirme nesneleri**.

#### <a name="to-create-an-object-from-a-polygon-selection"></a>Çokgen seçiminden bir nesne oluşturmak için

1. Yüz seçimi modunda yeni bir nesne oluşturmak istediğiniz yüzleri seçin.

2. Üzerinde **Model Düzenleyicisinde** araç seçin **betikleri**, **Araçları**, **Çokgen seçimden yeni nesne oluşturma**.

### <a name="work-with-materials-and-shaders"></a>Malzemeleri ve gölgelendiriciler ile çalışma

Bir nesnenin görünümü, sahnedeki aydınlatma etkileşimi ve nesnenin malzemesi ile belirlenir. Malzemeler, yüzeyin farklı ışık türlerine nasıl tepki verdiğini açıklayan özelliklerle ve nesne yüzeyindeki her pikselin son rengini ışıklandırma bilgisine, doku eşlemelerine, normal eşlemelere ve diğer verilere göre hesaplayan bir gölgelendirici programla tanımlanır.

Model Düzenleyicisi şu varsayılan malzemeleri sağlar:

|Malzeme|Açıklama|
|--------------|-----------------|
|Işıklandırılmamış|Benzetimli aydınlatma olmadan bir yüzeyi işler.|
|Lambert|Benzetimli ortam aydınlatması ve yayınık aydınlatma ile bir yüzey işler.|
|Phong|Benzetimli ortam aydınlatması, yayınık aydınlatma ve yansımalı vurgular ile bir yüzeyi işler.|

Bu malzemelerin her biri nesnenin yüzeyine tek bir doku uygular. Malzemeyi kullanan her nesne için farklı bir doku ayarlayabilirsiniz.

Belirli bir nesnenin sahnedeki farklı ışık kaynaklarına verdiği tepkiyi değiştirmek için, malzemeyi kullanan diğer nesnelerden bağımsız olarak malzemenin aydınlatma özelliklerini değiştirebilirsiniz. Bu tabloda genel aydınlatma özellikleri açıklanmaktadır:

|Aydınlatma Özelliği|Açıklama|
|-----------------------|-----------------|
|Ortam|Yüzeyin ortam aydınlatmasından nasıl etkilendiğini açıklar.|
|Yayınık|Yüzeyin yönlü ve nokta ışıklardan nasıl etkilendiğini açıklar.|
|Yayımlatıcı|Yüzeyin, diğer aydınlatmalardan bağımsız olarak ışığı nasıl yaydığını açıklar.|
|Yansımalı|Yüzeyin yönlü ve nokta ışıkları nasıl yansıttığını açıklar.|
|Yansımalı Güç|Yansımalı vurguların genişliğini ve yoğunluğunu açıklar.|

Bir malzemenin neyi desteklediğine bağlı olarak aydınlatma özelliklerini, dokuları ve diğer verileri değiştirebilirsiniz. İçinde **seçin** modu, malzeme değiştirmek istediğiniz nesne seçin ve ardından **özellikleri** penceresinde, değişiklik **MaterialAmbient**,  **MaterialDiffuse**, **MaterialEmissive**, **MaterialSpecular**, **MaterialSpecularPower**, ya da diğer kullanılabilir özellik. Bir malzeme özellikleri adlı sırayla gelen en fazla sekiz dokuları getirebilir **Texture1** için **Texture8**.

Üzerinde bir nesneden tüm malzemeleri kaldırma hakkını **Model Düzenleyicisinde** araç seçin **betikleri**, **malzemeleri**, **malzemeleri kaldırma**.

Kullanabileceğiniz **gölgelendirici Tasarımcısı** , 3B Sahne nesnelere uygulanan özel gölgelendirici malzemeleri oluşturmak için. Özel gölgelendirici malzemeleri oluşturma hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md). Bir nesneye malzeme özel gölgelendirici uygulama hakkında daha fazla bilgi için bkz [nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md).

### <a name="scene-management"></a>Sahne yönetimi

Sahneleri nesnelerin bir hiyerarşisi olarak yönetebilirsiniz. Birden fazla nesne hiyerarşik bir şekilde düzenlendiğinde, üst öğe düğümünün herhangi bir çeviri, ölçek veya döndürme işlemi alt öğelerini de etkiler. Bu, temel nesnelerden karmaşık nesneler veya sahneler oluşturmak istediğinizde kullanışlıdır.

Kullanabileceğiniz **belge anahattı** penceresi Sahne hiyerarşi görüntüleyip Sahne düğümleri seçin. Anahat içinde bir düğümünü seçtiğinizde kullanabilirsiniz **özellikleri** pencere özelliklerini değiştirin.

Gerek birini diğerlerinin üst öğesi yaparak, gerekse üst öğe gibi davranan bir yer tutucu düğümünün altında eşdüzeyler olarak birlikte gruplandırarak nesnelerin bir hiyerarşisini oluşturabilirsiniz.

#### <a name="to-create-a-hierarchy-that-has-a-parent-object"></a>Üst nesnesi olan bir hiyerarşi oluşturmak için

1. İçinde **seçin** modu, iki veya daha fazla nesneleri seçebilir. İlk seçtiğiniz öğe üst nesne olur.

2. Üzerinde **Model Düzenleyicisinde** araç seçin **betikleri**, **Sahne Yönetim**, **eklemek için üst**.

#### <a name="to-create-a-hierarchy-of-sibling-objects"></a>Eşdüzeyli nesnelerin hiyerarşisini oluşturmak için

1. İçinde **seçin** modu, iki veya daha fazla nesneleri seçebilir. Bir yer tutucu nesne oluşturulur ve onların üst nesnesi haline gelir.

2. Üzerinde **Model Düzenleyicisinde** araç seçin **betikleri**, **Sahne Yönetim**, **Grup Oluştur**.

Model Düzenleyicisi, ilk seçilen nesneyi (üst öğe haline gelen) tanımlamak için beyaz tel çerçeve kullanır. Seçimdeki diğer nesneler mavi bir tel çerçeveye sahiptir. Varsayılan olarak, yer tutucu düğümleri görüntülenmez. Yer tutucu düğümleri görüntülemek için **Model Düzenleyicisinde** araç seçin **betikleri**, **Sahne Yönetim**, **Göster yer tutucu düğümleri**. Yer tutucu düğümleriyle, yer tutucu olmayan nesnelerle çalıştığınız gibi çalışabilirsiniz.

İki nesne arasındaki üst-alt ilişkisi kaldırmak için alt nesne seçin ve ardından **Model Düzenleyicisinde** araç seçin **betikleri**, **Sahne Yönetim**, **Üst öğeden detach**. Üst nesne ile alt nesneyi ayırdığınızda, alt nesne sahnede bir kök nesne olur.

## <a name="keyboard-shortcuts"></a>Klavye kısayolları

|Komut|Klavye kısayolları|
|-------------|------------------------|
|Geçiş **seçin** modu|Ctrl+G, Gtrl+Q<br /><br /> S|
|Geçiş **yakınlaştırma** modu|Ctrl+G, Ctrl+Z<br /><br /> Z|
|Geçiş **Pan** modu|Ctrl+G, Ctrl+P<br /><br /> K|
|Tümünü seç|Ctrl+A|
|Geçerli seçimi sil|Sil|
|Geçerli seçimi iptal et|Esc|
|Yakınlaştır|Fare tekerleği ileriye doğru<br /><br /> Ctrl+Fare tekerleği ileriye doğru<br /><br /> Shift+Fare tekerleği ileriye doğru<br /><br /> Ctrl+PageUp<br /><br /> Artı İşareti (+)|
|Uzaklaştır|Fare tekerleği geriye doğru<br /><br /> Ctrl+Fare tekerleği geriye doğru<br /><br /> Shift+Fare tekerleği geriye doğru<br /><br /> Ctrl+PageDown<br /><br /> Eksi İşareti (-)|
|Kamerayı yukarı kaydır|PageDown|
|Kamerayı aşağı kaydır|PageUp|
|Kamerayı sola kaydır|Fare tekerleği sol<br /><br /> Ctrl+PageDown|
|Kamerayı sağa kaydır|Fare tekerleği sağ<br /><br /> Ctrl+PageDown|
|Modelin üst kısmını görüntüle|Ctrl+L, Ctrl+T<br /><br /> T|
|Modelin alt kısmını görüntüle|Ctrl+L, Ctrl+U|
|Modelin sol tarafını görüntüle|Ctrl+L, Ctrl+L|
|Modelin sağ tarafını görüntüle|Ctrl+L, Ctrl+R|
|Modelin önünü görüntüle|Ctrl+L, Ctrl+F|
|Modelin arkasını görüntüle|Ctrl+L, Ctrl+B|
|Nesneyi pencere içinde çerçevele|F|
|Tel çerçeve modunu aç/kapat|Ctrl+L, Ctrl+W|
|Kılavuza uydurmayı aç/kapat|Ctrl+G, Ctrl+N|
|Pivot modunu aç/kapat|Ctrl+G, Ctrl+V|
|X ekseni kısıtlamasını aç/kapat|Ctrl+L, Ctrl+X|
|Y ekseni kısıtlamasını aç/kapat|Ctrl+L, Ctrl+Y|
|Z ekseni kısıtlamasını aç/kapat|Ctrl+L, Ctrl+Z|
|Çeviri moduna geçiş yap|Ctrl+G, Ctrl+W<br /><br /> W|
|Ölçek moduna geçiş yap|Ctrl+G, Ctrl+E<br /><br /> E|
|Döndürme moduna geçiş yap|Ctrl+G, Ctrl+R<br /><br /> R|
|Nokta seçme moduna geçiş yap|Ctrl+L, Ctrl+1|
|Kenar seçme moduna geçiş yap|Ctrl+L, Ctrl+2|
|Yüz seçme moduna geçiş yap|Ctrl+L, Ctrl+3|
|Nesne seçme moduna geçiş yap|Ctrl+L, Ctrl+4|
|Yörünge (kamera) moduna geçiş yap|Ctrl+G, Ctrl+O|
|Sahnede sonraki nesneyi seç|Tab|
|Sahnede önceki nesneyi seç|Shift+Sekme Tuşu|
|Geçerli araca bağlı olarak seçili nesneyi düzenle.|Ok tuşları|
|Geçerli işleyiciyi devre dışı bırak|Q|
|Kamerayı döndür|Alt + Farenin sol düğmesiyle sürükleme|

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[3B varlıklarıyla oyunları ve uygulamaları için çalışma](../designers/working-with-3-d-assets-for-games-and-apps.md)|Grafik varlıklar dokuları, görüntüler, 3B modeller ve gölgelendirici etkileri gibi çalışmak için kullanabileceğiniz Visual Studio Araçları Genel bir bakış sağlar.|
|[Görüntü Düzenleyicisi](../designers/image-editor.md)|Visual Studio görüntü Düzenleyicisi dokuları ve görüntüleri ile çalışmak için nasıl kullanılacağını açıklar.|
|[Gölgelendirici Tasarımcısı](../designers/shader-designer.md)|Visual Studio gölgelendirici Tasarımcısı gölgelendiriciler ile çalışmak için nasıl kullanılacağını açıklar.|