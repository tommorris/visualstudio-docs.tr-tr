---
title: Görüntü Düzenleyici
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- vs.graphics.designer.imageeditor
- vs.graphics.imageeditor
ms.assetid: fc71d502-c548-4863-8afc-12a1d3ec90d4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 92d82cfaf2f06018ce93e6c1fce1abd0b63809f6
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747316"
---
# <a name="image-editor"></a>Görüntü Düzenleyici

Bu belge, doku ve görüntü kaynakları görüntülemek ve değiştirmek için Visual Studio görüntü Düzenleyicisi ile çalışmak açıklar.

 Görüntü Düzenleyicisi DirectX uygulaması geliştirme kullanılan zengin doku ve resim biçimleri türlerini çalışmak için kullanabileceğiniz — Bu popüler görüntü dosyası biçimlerini ve renk Kodlamalar, alfa kanallar ve MIP eşleştirme gibi özellikler için destek ve birçok içerir yüksek oranda sıkıştırılmış, donanım hızlandırılmış doku DirectX destekleyen biçimlendirir.

## <a name="supported-formats"></a>Desteklenen biçimler

Görüntü Düzenleyicisi bu görüntü biçimlerini destekler:

|Biçim adı|Dosya Adı Uzantısı|
|-----------------|-------------------------|
|Taşınabilir Ağ Grafikleri|.PNG|
|JPEG|.jpg, .jpeg, .jpe, .jfif|
|Doğrudan çizim yüzeyini|.DDS|
|Grafik Değişim Biçimi|.gif|
|Bit eşlem|.bmp, .dib|
|Etiketli Görüntü dosyası biçimi|.tif, .tiff|
|TGA (Targa)|.TGA|

## <a name="get-started"></a>Kullanmaya başlayın

Bu bölümde, Visual Studio projenize bir görüntü ekleyin ve gereksinimleriniz için yapılandırma açıklar.

### <a name="to-add-an-image-to-your-project"></a>Bir görüntü projenize eklemek için

1.  İçinde **Çözüm Gezgini**, görüntüsüne ekleyin ve ardından istediğiniz proje için kısayol menüsünü açın **Ekle**, **yeni öğe**.

2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **yüklü**seçin **grafik**ve ardından bir görüntü için uygun dosya biçimi seçin. Gereksinimlerinize göre bir dosya biçimi seçme hakkında daha fazla bilgi için aşağıdaki bölümüne bakın.

3.  Belirtin **adı** görüntü dosyasının ve **konumu** istediğiniz oluşturulacak.

4.  Seçin **Ekle** düğmesi.

### <a name="choose-the-image-format"></a>Görüntü biçimi seçin

Nasıl görüntü kullanmayı planladığınız bağlı olarak, belirli dosya biçimlerine diğerlerinden daha uygun olabilir. Örneğin, bazı biçimleri gereksinim duyduğunuz bir özelliği desteklemiyor olabilir — saydamlık veya belirli bir renk biçimi gibi — veya planlanmış görüntü içerik türü için uygun sıkıştırma sağlamayabilir.

 Aşağıdaki bilgiler ihtiyaçlarınıza uygun bir görüntü biçimi seçmenize yardımcı olabilir.

 **Bit eşlem resim (.bmp)** bit eşlem resim biçimi. 24 bit renk destekleyen sıkıştırılmamış görüntü biçimi. Bit eşlem saydamlık desteklemiyor.

 **GIF resim (.gif)** Grafik Değişim Biçimi (GIF) görüntü biçimi. 256 renk destekleyen bir LZW sıkıştırılmış, kayıpsız görüntü biçimi. Fotoğraf ve renk ayrıntı önemli miktarda ancak iyi sıkıştırma oranları yüksek dereceli bir renk tutarlılık sahip düşük renk görüntülerde sağlar görüntüleri için uygun değil.

 **JPG resim (.jpg)** Birleşik Fotoğraf Uzmanları Grubu (JPEG) görüntü biçimi. 24 bit renk destekler ve renk tutarlılık yüksek derecede sahip görüntüleri genel amaçlı sıkıştırma için uygun bir yüksek oranda sıkıştırılmış, kayıplı görüntü biçimi.

 **PNG resim (.png)** Taşınabilir Ağ Grafikleri (PNG) görüntü biçimi. 24 bit renk ve alfa saydamlığı destekler oldukça sıkıştırılmış, kayıpsız görüntü biçimi. Doğal ve yapay görüntüler için uygundur ancak sıkıştırma oranları JPG veya GIF gibi kadar iyi kayıplı biçimleri sağlamaz.

 **TIFF resim (.tif)** etiketli görüntü dosyası biçimi (TIFF veya TIF) görüntü biçimi. Birkaç sıkıştırma şemasını destekler esnek görüntü biçimi.

 **DDS doku (.dds)** DirectDraw yüzeyini (DDS) doku biçimi. 24 bit renk ve alfa saydamlığı destekleyen bir yüksek oranda sıkıştırılmış, kayıplı doku biçimi. Sıkıştırma oranları 8:1 olarak yüksek olabilir. Grafik donanımda sıkıştırması S3 doku sıkıştırma dayanır.

 **TGA görüntü (.tga)** Truevision grafik bağdaştırıcı (TGA) görüntü biçimi (Targa olarak da bilinir). RLE sıkıştırılmış, kayıpsız görüntüyü biçimlendirme renk eşlenen her ikisini de destekler (renk paletini) veya doğrudan Renk görüntülerini 24 bit renk ve Alfa Saydamlığı kadar. Fotoğraf ve renk ayrıntı önemli miktarda sahip, ancak aynı renkleri uzun yayılma sahip görüntüler için iyi sıkıştırma oranları sağlayan görüntüler için uygun değil.

### <a name="configure-the-image"></a>Yapılandırma resmi

Yeni oluşturduğunuz görüntü ile çalışmaya başlamadan önce varsayılan yapılandırmasını değiştirebilirsiniz. Örneğin, Boyutlar veya kullandığı renk biçimi değiştirebilirsiniz. Bunlar ve diğer özellikleri görüntüsünün nasıl yapılandırılacağı hakkında daha fazla bilgi için bkz: [görüntü özelliklerini](#ImageProperties).

> [!NOTE]
>  Çalışmanızı kaydetmeden önce ayarladığınızdan emin olun **renk biçimi** belirli bir renk biçimi kullanmak istiyorsanız, özellik. Dosya biçimi sıkıştırma destekliyorsa, dosyayı ilk kez veya seçtiğinizde kaydettiğinizde sıkıştırma ayarları ayarlayabilirsiniz **Kaydet**.

## <a name="work-with-the-image-editor"></a>Görüntü Düzenleyicisi ile çalışma

Bu bölümde, doku ve görüntüleri değiştirmek için görüntü Düzenleyicisi kullanmayı açıklar.

### <a name="image-editor-toolbars"></a>Görüntü Düzenleyicisi araç çubukları

Görüntü Düzenleyicisi araç çubukları içeren görüntülerle çalışma yardımcı komutları.

 Görüntü Düzenleyicisi'nin durumunu etkileyen komutları bulunur **görüntü Düzenleyicisi modu** Gelişmiş komutları birlikte araç. Görüntü Düzenleyicisi tasarım yüzeyi en üstteki kenarına araç bulunur. Çizim araçları bulunur **görüntü Düzenleyicisi** görüntü Düzenleyicisi tasarım yüzeyi sol kenarı boyunca araç.

 Burada **görüntü Düzenleyicisi modu** araç çubuğu:

 ![Görüntü Düzenleyicisi kalıcı araç.](../designers/media/digit-tre-modal-toolbar.png)

 Bu tablo üzerinde öğeleri açıklar **görüntü Düzenleyicisi modu** araç çubuğu göründükleri soldan sağa doğru sırayla listelenir.

|Araç Çubuğu Öğesi|Açıklama|
|------------------|-----------------|
|**seçin**|Dikdörtgen bir bölgesi görüntü seçimi sağlar. Bir bölge seçtikten sonra kesme, kopyalayabilir, taşımak, ölçeklendirme, döndürme, Çevir veya silin. Çizim Araçları, yalnızca etkin bir seçim olduğunda, seçili bölgeye etkiler.|
|**Düzensiz seçimi**|Düzensiz bir bölgenin görüntü seçimi sağlar. Bir bölge seçtikten sonra kesme, kopyalayabilir, taşımak, ölçeklendirme, döndürme, Çevir veya silin. Çizim Araçları, yalnızca etkin bir seçim olduğunda, seçili bölgeye etkiler.|
|**Değnek seçimi**|Benzer şekilde renkli bölgesinin görüntü seçimi sağlar. *Dayanıklılık*— diğer bir deyişle, maksimum fark içinde bunlar değerlendirilir benzer bitişik renkler arasındaki — benzer renkleri daha küçük veya daha geniş bir dizi içerecek şekilde yapılandırılabilir. Bir bölge seçtikten sonra kesme, kopyalayabilir, taşımak, ölçeklendirme, döndürme, Çevir veya silin. Çizim Araçları, yalnızca etkin bir seçim olduğunda, seçili bölgeye etkiler.|
|**Pan**|Görüntünün pencere çerçevesi göre hareketini sağlar. İçinde **Pan** modu, görüntünün bir nokta seçin ve ardından taşıyabilirsiniz.<br /><br /> Geçici olarak etkinleştirebilirsiniz **Pan** tuşuna basarak ve Ctrl tuşunu basılı tutarak modu.|
|**Yakınlaştır**|Pencere çerçevesi göre daha az veya görüntü ayrıntı görünümünü sağlar. İçinde **yakınlaştırma** modu, görüntünün bir nokta seçin ve ardından sağa taşıyın veya yakınlaştırmak için aşağı veya sol veya en fazla yakınlaştırma yetersiz.<br /><br /> Tuşuna basarak ve fare tekerleğinin kullanabilir veya artı (+) basın Ctrl tutarken veya eksi işareti (-) yakınlaştırma veya uzaklaştırma.|
|**Gerçek boyutuna Büyüt**|Görüntüyü, görüntünün ve ekrandaki pikseller arasında 1:1 ilişki kullanarak görüntüler.|
|**Sığdırmak için Yakınlaştır**|Tam görüntüyü penceresi çerçevede görüntüler.|
|**Genişliğine yakınlaştırır**|Tam genişlikli görüntünün penceresi çerçevede görüntüler.|
|**Kılavuz**|Etkinleştirir veya piksel sınırlarını gösterir kılavuz devre dışı bırakır. Görüntüsüne yakınlaştırmak kadar kılavuz görünmeyebilir.|
|**Görünüm sonraki MIP düzeyi**|Daha büyük MIP düzeydeki MIP harita zincirindeki etkinleştirir. Etkin MIP düzeyi tasarım yüzeyine görüntülenir. Bu öğe yalnızca MIP düzeylerine sahip dokular için kullanılabilir.|
|**Görünüm önceki MIP düzeyi**|Daha küçük MIP düzeydeki MIP harita zincirindeki etkinleştirir. Etkin MIP düzeyi tasarım yüzeyine görüntülenir. Bu öğe yalnızca MIP düzeylerine sahip dokular için kullanılabilir.|
|**Kırmızı kanalı**<br /><br /> **Yeşil kanal**<br /><br /> **Mavi kanal**<br /><br /> **Alfa kanal**|Etkinleştirir veya belirli bir renk kanal devre dışı bırakır. **Not:** sistematik olarak etkinleştirme veya renk kanalları devre dışı bırakarak, bir veya daha fazlası ile ilgili sorunları ayırabilirsiniz. Örneğin, hatalı Alfa Saydamlığı tanımlayabilirsiniz.|
|**Arka plan**|Etkinleştirir veya arka plan resminin saydam bölümleri aracılığıyla görüntülenmesini devre dışı bırakır. Aşağıdaki seçeneklerden birini seçerek arka nasıl görüntüleneceğini yapılandırabilirsiniz:<br /><br /> **Damalı**<br /> Arka plan Damalı bir desen göstermek için yeşil bir renk belirtilen arka plan rengini birlikte kullanır. Resmin saydam bölümlerini daha belirgin olmasına yardımcı olmak için bu seçeneği kullanın.<br /><br /> Beyaz arka plan<br /> Rengi beyaz arka plan görüntülemek için kullanır.<br /><br /> Siyah arka plan<br /> Siyah renk, arka plan görüntülemek için kullanır.<br /><br /> Arka plan animasyon ekleme<br /> Dama deseni yavaş yatay kaydırır. Resmin saydam bölümlerini daha belirgin olmasına yardımcı olmak için bu seçeneği kullanın.|
|**Özellikler**|Alternatif olarak açar veya kapatır **özellikleri** penceresi.|
|**Gelişmiş**|Ek komutlar ve seçenekler içerir.<br /><br /> **Filtreler**<br /><br /> Birçok ortak resmi filtreleri sağlar: **siyah beyaz**, **Ölçeklendirilmelidir**, **Brighten**, **Koyulaştır**, **kenar algılama**, **Kabartma**, **renkleri ters çevir**, **Ripple**, **sepya**, ve **keskinleştirme**.<br /><br /> **Grafik motorları**<br /><br /> **D3D11 ile işleme**<br /> Görüntü Düzenleyicisi tasarım yüzeyi işlemek için Direct3D 11 kullanır.<br /><br /> **D3D11WARP ile işleme**<br /> Görüntü Düzenleyicisi tasarım yüzeyi işlemek için Direct3D 11 Windows Gelişmiş Tarama Platform (TÜNELİ) kullanır.<br /><br /> **Araçlar**<br /><br /> **Yatay Ters Çevir**<br /> Görüntünün yatay ya da x ekseni etrafında'ye dönüştürür.<br /><br /> **Dikey Ters Çevir**<br /> Görüntünün dikey veya y ekseni etrafında'ye dönüştürür.<br /><br /> **MIPS oluştur**<br /> Görüntü için MIP düzeylerini oluşturur. MIP düzeyleri zaten varsa, bunlar büyük MIP düzeyden yeniden oluşturulur. Daha küçük MIP düzeylere yapılan değişiklikler kaybolur. Oluşturulan MIP düzeyleri kaydetmek için görüntüsünü kaydetmek için .dds biçimi kullanmanız gerekir.<br /><br /> **Görünümü**<br /><br /> **Kare hızı**<br /> Etkinleştirildiğinde, kare hızı tasarım yüzeyine sağ üst köşesinde görüntülenir. Kare hızı, saniye başına çizilen çerçeve sayısıdır. **İpucu:** seçebileceğiniz **Gelişmiş** düğmesi son komutu yeniden çalıştırın.|

 Burada **görüntü Düzenleyicisi** araç.

 ![Görüntü Düzenleyicisi araç çubuğu](../designers/media/digit-tre-toolbar.png)

 Aşağıdaki tabloda öğeleri açıklar **görüntü Düzenleyicisi** araç çubuğu göründükleri üstten alta gözüktükleri sırada listelenir.

|Araç Çubuğu Öğesi|Açıklama|
|------------------|-----------------|
|**Kalem**|Etkin renk seçim bir SELECT vuruş çizmek için kullanır. Renk ve vuruş kalınlığı ayarlayabilirsiniz **özellikleri** penceresi.|
|**Fırça**|Kenar yumuşatma vuruş çizmek için etkin renk seçimi kullanır. Renk ve vuruş kalınlığı ayarlayabilirsiniz **özellikleri** penceresi.|
|**Havalı fırça**|Görüntünün birlikte karıştırır ve süresinin bir işlevi olarak daha doymuş duruma bir kenar yumuşatma vuruşu çizmek için etkin renk seçimi kullanır. Renk ve vuruş kalınlığı ayarlayabilirsiniz **özellikleri** penceresi.|
|**Damlalık**|Etkin renk seçimi seçili piksel rengini belirler.|
|**doldurma**|Görüntü bölgesi doldurmak için etkin renk seçimi kullanır. Etkilenen bölge burada dolgu, her piksel, aynı renkteki piksel bağlı olduğu ve aynı renk birlikte uygulanır piksel olarak tanımlanır. Dolgu etkin bir seçim uyguladıysanız, etkilenen bölge seçerek sınırlı değildir.<br /><br /> Varsayılan olarak, görüntünün alfa bileşen göre etkilenen bölge ile birlikte etkin renk seçimi karıştırılan. Etkilenen bölge üzerine yazmak için etkin renk seçimi kullanmak üzere dolgu Aracı'nı kullandığınızda Shift tuşunu basılı tutun.|
|**Silme**|Görüntünün bir alfa kanal destekliyorsa piksel için tamamen saydam rengini belirler. Aksi takdirde, piksel için etkin arka plan rengini belirler.|
|**Satır**, **dikdörtgen**, **yuvarlak dikdörtgen**, **elips**|Bir şekli görüntü üzerinde çizer. Renk ve hattaki kalınlığı ayarlayabilirsiniz **özellikleri** penceresi.<br /><br /> Eşit genişlik ve yükseklik sahip ilkel çizmek için tuşuna basın ve çizerken Shift basılı tutun.|
|**Metin**|Ön plan rengini seçimin metin çizme için kullanır. Arka plan rengi, arka plan rengi seçime göre belirlenir. Saydam arka plan, arka plan rengi seçim alfa değeri 0 olmalıdır. Metin bölge etkinken metin kenar yumuşatma vuruşu ile çizilir ve metin ayarlayabilirsiniz olup olmadığını ayarlayabilir **değeri**, **yazı tipi**, **boyutu**ve stil —**Kalın**, **italik**, veya **altı çizili**— içinde **özellikleri** penceresi. İçerik ve metin görünümünü kesin metin bölge artık etkin olduğunda.|
|**döndürme**|Görüntüyü 90 derece saat yönünde döndürür.|
|**Kırpma**|Etkin seçimi görüntüye kırpar.|

### <a name="work-with-mip-levels"></a>MIP düzeyleri ile çalışma

Bazı görüntü biçimleri — Örneğin, DirectDraw yüzeyini (.dds) — MIP düzeyi doku alanı düzeyi-in-ayrıntısını (LOD) destekler. Oluştur ve MIP düzeyleri ile çalışma hakkında daha fazla bilgi için bkz: [nasıl yapılır: oluşturmak ve MIP düzeylerini değiştirme](../designers/how-to-create-and-modify-mip-levels.md)

### <a name="work-with-transparency"></a>Saydamlık ile çalışma

Bazı görüntü biçimleri — Örneğin, DirectDraw yüzeyini (.dds) — saydamlığı destekler. Saydamlık, kullanmakta olduğunuz araç bağlı olarak kullanılabileceğini birkaç yolu vardır. Bir renk seçilmek saydamlık düzeyi belirtmek üzere **özellikleri** penceresindeki ayarlayın **A** renk seçimi (alfa) bileşeni. Araçlar Denetim saydamlık nasıl uygulandığını nasıl farklı türde şöyledir:

|Aracı|Açıklama|
|----------|-----------------|
|**Kalem**, **fırça**, **havalı fırça**, **satır**, **dikdörtgen**, **yuvarlak dikdörtgen** , **Elips**, **metin**|Görüntü ile birlikte etkin renk seçimi de karıştırmak için **özellikleri** penceresinde genişletin **kanalları** özellik grubu ve kümesi **çizmek** onaykutusu **Alpha** kanal ve normal şekilde çizin.<br /><br /> Etkin renk seçim ile çizme ve görüntünün alfa değeri bırakın için temizleyin **çizin** , onay kutusu **alfa** kanal ve normal şekilde çizin.|
|**doldurma**|Görüntü ile birlikte etkin renk seçimi karıştırmak için yalnızca doldurmak için alanı seçin.<br /><br /> Etkin renk seçimi kullanmak üzere — alfa kanal değeri de dahil olmak üzere — görüntünün üzerine yazmak için tuşuna basın ve Shift basılı tutun ve doldurmak için alanı seçin.|

### <a name="image-properties"></a>Görüntü Özellikleri

Kullanabileceğiniz **özellikleri** görüntünün çeşitli özelliklerini belirtmek için penceresi. Örneğin, görüntüyü yeniden boyutlandırmak için genişlik ve yükseklik özellikleri ayarlayabilirsiniz.

Aşağıdaki tabloda görüntü özelliklerini açıklar.

|Özellik|Açıklama|
|--------------|-----------------|
|Genişlik|Resmin genişliğini.|
|Yükseklik|Resmin yüksekliğini.|
|Bit / piksel|Her piksel temsil eden bit sayısı. Bu özelliğin değeri bağlıdır **renk biçimi** görüntünün.|
|Saydam seçimi|**Doğru** karıştırmak için ana birlikte seçimi katman görüntü, seçim katmanın alfa değeri temel alınarak, aksi takdirde **False**. Bu öğe yalnızca alfa destekleyen görüntüler için kullanılabilir.|
|Biçimi|Görüntü renk biçimi. Görüntü biçimi bağlı olarak, çeşitli renk biçimlerde belirtilebilir. Renk biçimi sayı ve yansıma ve boyutu dahil ve çeşitli kanalı kodlama renk kanalları türünü tanımlar.|
|MIP düzeyi|Etkin MIP düzeyi. Bu öğe yalnızca MIP düzeylerine sahip dokular için kullanılabilir.|
|MIP düzey sayısı|Görüntüde MIP düzeyleri toplam sayısı. Bu öğe yalnızca MIP düzeylerine sahip dokular için kullanılabilir.|
|Çerçeve sayısı|Görüntü çerçevelere toplam sayısı. Bu öğe yalnızca doku dizileri desteklemek görüntüler için kullanılabilir.|
|Çerçeve|Geçerli çerçevesi. Yalnızca ilk çerçeve görüntülenebilir; diğer tüm çerçeveler görüntü kaydedildiğinde kaybolur.|
|Derinlik dilim sayısı|Görüntü derinliği dilimleri toplam sayısı. Bu öğe yalnızca birim dokuları destekleyen görüntüler için kullanılabilir.|
|Derinlik dilim|Geçerli derinlik dilim. Yalnızca ilk dilim görüntülenebilir; diğer tüm dilimleri görüntü kaydedildiğinde kaybolur.|

> [!NOTE]
>  Çünkü **tarafından Döndür** özelliği uygulanır tüm araçlar ve seçili bölgeler için her zaman en altında görüntülenen **özellikleri** diğer aracı özellikleri ile birlikte penceresi. **Tarafından döndürme** başka bir seçim veya etkin araca olduğunda görüntünün tamamını örtük olarak seçilmediğinden her zaman görüntülenir. Hakkında daha fazla bilgi için **tarafından döndürme** özelliği, bkz: [aracı özelliklerini](#ToolProperties).

#### <a name="resize-images"></a>Görüntüleri yeniden boyutlandırma

Burada, görüntüyü yeniden boyutlandırmak için iki yolu bulunmaktadır. Görüntü Düzenleyicisi, her iki durumda da, görüntüyü yeniden örneklemek için BI doğrusal ilişkilendirme kullanır.

-   İçinde **özellikleri** penceresinde, yeni değerlerini belirtin **genişliği** ve **yükseklik** özellikleri.

-   Görüntünün tümünü seçin ve görüntüyü yeniden boyutlandırmak için kenarlık işaretlerini kullanın.

### <a name="work-with-tools"></a>Araçları ile çalışma

#### <a name="selected-regions"></a>Seçili bölgeler

Seçimleri görüntü Düzenleyicisi'nde tanımlamak etkin olan görüntü bölgeleri — araçları ve dönüştürmeler tarafından bölge diğer bir deyişle, etkilenecek. Etkin bir seçim olduğunda, seçili bölge dışında alanları çoğu araçları ve dönüşümleri tarafından etkilenmez. Etkin bir seçim değilse, görüntünün tamamını etkindir.

Çoğu araç —**kalem**, **fırça**, **havalı fırça**, **doldurun**, **silme**ve 2B temelleri — ve Dönüşümleri —**Döndür**, **kırpma**, **renkleri ters çevir**, **Yatay Çevir**, ve **Dikey Ters Çevir** — kısıtlı veya etkin seçime göre tanımlanabilir. Ancak, bazı araçları —**Damlalık** ve **metin**— ve dönüştürmeler —**oluşturmak MIPS**— tüm etkin seçerek; etkilenmez bu araçların her zaman davranır gibi tüm Görüntü etkin bir seçimdir.

Bir bölge seçmeyi olsa da, tuşuna basın ve orantılı (kare) seçim yapmak için Shift tutun; Aksi takdirde, seçimi sınırlı değildir.

##### <a name="resize-selections"></a>Seçimleri yeniden boyutlandırma

Bir bölge seçtikten sonra seçim işaretin boyutunu değiştirerek veya görüntü içeriğinin boyutunu değiştirebilirsiniz. Seçili bölgeye yeniden boyutlandırma, ancak bunu (basılı tutarak yeniden boyutlandırmak anahtar, olarak) yeniden boyutlandırma olarak seçili bölge davranışını değiştirmek için aşağıdaki değiştirici tuşları kullanabilirsiniz.

CTRL&mdash;onu yeniden boyutlandırılır önce seçili bölgeye içeriğini kopyalar. Kopyalama yeniden boyutlandırılabilir sırada bu özgün görüntüsüne dokunmaz.

Shift&mdash;özgün boyutuyla orantılı olarak seçili bölgeye göre yeniden boyutlandırır.

Alt&mdash;seçim bölgesini boyutunu değiştirir. Bu, görüntünün değiştirilmemiş şekilde bırakır.

Geçerli değiştirici tuş bileşimlerini şunlardır:

|CTRL|Kaydırma|Alt|Açıklama|
|----------|-----------|---------|-----------------|
||||Seçili bölgeye içeriğini yeniden boyutlandırır.|
||Kaydırma||Orantılı olarak seçili bölge içeriğini yeniden boyutlandırır.|
|||Alt|Seçili bölgeye göre yeniden boyutlandırır. Bu, yeni bir seçim bölge tanımlar.|
||Kaydırma|Alt|Orantılı olarak seçili bölgeye göre yeniden boyutlandırır. Bu, yeni bir seçim bölge tanımlar.|
|CTRL|||Kopyalar ve seçili bölgeye içeriğini yeniden boyutlandırır.|
|CTRL|Kaydırma||Kopyalar ve ardından orantılı olarak seçili bölge içeriğini yeniden boyutlandırır.|

#### <a name="tool-properties"></a>Aracı özellikleri

Bir aracı seçiliyken kullanabileceğiniz **özellikleri** penceresi görüntünün nasıl etkilediği hakkında ayrıntıları belirtin. Örneğin, kalınlığı ayarlayabilirsiniz **kalem** aracını veya rengini **fırça** aracı.

Ön plan rengini ve arka plan rengi ayarlayabilirsiniz. Hem kullanıcı tanımlı opaklık sağlamak için bir alfa kanal destekler. Ayarlar tüm araçlar için geçerlidir. Fare kullanıyorsanız, sol fare düğmesini ön plan rengini karşılık gelir ve farenin sağ düğmesiyle karşılık gelen arka plan rengi.

Aşağıdaki tabloda aracı özelliklerini açıklar.

|Aracı|Özellikler|
|----------|----------------|
|Tüm araçlar ve seçimleri|**Tarafından Döndür**<br /> Seçimi veya aracı etkisi yönünde içinde döndürüldüğüne derece cinsinden tutar tanımlar.|
|**Kalem**, **fırça**, **havalı fırça**, **silme**|**Kalınlığı**<br /> Aracı tarafından etkilenen alanının boyutunu tanımlar.|
|**Metin**|**Yumuşatma**<br /> Kenar yumuşatma kenarları sahip bir metin çizer. Bu metin daha sorunsuz bir görünümünü sağlar.<br /><br /> **Değer**<br /> Çizilecek metin.<br /><br /> **Yazı tipi**<br /> Metin çizmek için kullanılan yazıtipi.<br /><br /> **Boyutu**<br /> Metin boyutu.<br /><br /> **Kalın**<br /> Yazı tipi kalın hale getirir.<br /><br /> **İtalik**<br /> Yazı tipi italik yapar.<br /><br /> **Altı çizili**<br /> Altı çizili yazı tipi yapar.|
|**2B ilkel**|**Yumuşatma**<br /> Kenar yumuşatma kenarları sahip temelleri çizer. Bu onları daha sorunsuz bir görünümünü sağlar.<br /><br /> **Kalınlığı**<br /> Basit sınırı oluşturur çizgi kalınlığını tanımlar.<br /><br /> **RADIUS X**<br /> (Yalnızca yuvarlak dikdörtgen) Yuvarlama RADIUS basit üst ve alt kenarları için tanımlar.<br /><br /> **RADIUS Y**<br /> (Yalnızca yuvarlak dikdörtgen) Yuvarlama RADIUS basit sol ve sağ kenarlarının tanımlar.|
|**Kalem**, **fırça**, **havalı fırça**, **2B ilkel**|**Kanalları**<br /> Etkinleştirir veya görüntüleme ve çizim için belirli bir renk kanalları devre dışı bırakır. Varsa **Görünüm** için belirli bir renk kanal kümesi, bu kanala görüntüde görünür olur; Aksi takdirde görünür değil. Varsa **çizin** ayarlanmış belirli bir renk kanalı için kanal işlemleri çizim tarafından etkilenen; Aksi takdirde, bu değildir.|
|**Değnek seçimi**, **doldurun**|**Dayanıklılık**<br /> Daha az veya daha fazla benzer renkleri etkilenen ya da seçilen bölge parçası yapılması içinde bunlar benzer, kabul edilen bitişik renkleri arasındaki maksimum farkı tanımlar. Varsayılan olarak, 32, özgün rengin 32 gri (koyu veya açık) içinde bitişik piksel bölgesinin bir parçası olarak değerlendirilir yani değerdir.|

## <a name="keyboard-shortcuts"></a>Klavye kısayolları

|Komut|Klavye kısayolları|
|-------------|------------------------|
|Geçiş **seçin** modu|S|
|Geçiş **yakınlaştırma** modu|Z|
|Geçiş **Pan** modu|K|
|Tümünü seç|Ctrl+A|
|Geçerli seçimi sil|Sil|
|Geçerli seçimi iptal et|Esc|
|Yakınlaştır|Ctrl+Fare tekerleği ileriye doğru<br /><br /> Ctrl+PageUp<br /><br /> Artı İşareti (+)|
|Uzaklaştır|Geriye dönük CTRL-fare tekerleği<br /><br /> CTRL-PageDown<br /><br /> Eksi İşareti (-)|
|Görüntüyü oluşturan kaydırma|Fare tekerleği geriye doğru<br /><br /> PageDown|
|Görüntüyü aşağı kaydırma|Fare tekerleği ileriye doğru<br /><br /> PageUp|
|Sol görüntüyü kaydırma|Shift+Fare tekerleği geriye doğru<br /><br /> Fare tekerleği sol<br /><br /> Shift + PageDown|
|Görüntüyü sağa kaydırma|Shift+Fare tekerleği ileriye doğru<br /><br /> Fare tekerleği sağ<br /><br /> Shift + PageUp|
|Gerçek boyutuna Büyüt|CTRL + 0 (sıfır)|
|Resmi pencereye sığdır|CTRL + G, Ctrl + F|
|Pencere genişliği uygun görüntüyü|CTRL + G ve Ctrl + ı|
|Geçiş Kılavuzu|CTRL + G, Ctrl + G|
|Geçerli seçim için görüntüyü Kırp|CTRL + G, Ctrl + C|
|Görünüm sonraki (daha yüksek ayrıntı) MIP düzeyi|CTRL + G, Ctrl + 6|
|Önceki (düşük ayrıntı) görüntülemek MIP düzeyi|CTRL + G, Ctrl + 7|
|İki durumlu kırmızı renk kanalı|CTRL + G, Ctrl + 1|
|İki durumlu yeşil renk kanalı|CTRL + G, Ctrl + 2|
|İki durumlu mavi renk kanalı|CTRL + G, Ctrl + 3|
|İki durumlu alfa (Saydamlık) kanal|CTRL + G, Ctrl + 4|
|İki durumlu düğme alfa Damalı düzeni|CTRL + G, Ctrl + B|
|Düzensiz seçim aracı arasında geçiş|L|
|Değnek seçim aracı arasında geçiş|M|
|Aracı Kurşun Kalem anahtarı|P|
|Geçiş aracı fırça|B|
|Dolgu aracı anahtarı|F|
|Silme aracı arasında geçiş|E|
|Metin aracı arasında geçiş|T|
|Renk seçin (Damlalık) aracı arasında geçiş|I|
|Etkin seçimi ve içeriği taşıyın.|Ok tuşları.|
|Etkin seçimi ve içeriği yeniden boyutlandırın.|CTRL + ok tuşları|
|Etkin seçimi, ancak içeriğini değil taşıyın.|Shift + ok tuşları|
|Etkin seçimi, ancak içeriğini değil yeniden boyutlandırın.|Shift + Ctrl + ok tuşları|
|Geçerli katmana Yürüt|Döndür|
|Aracı kalınlığını azaltmak|[|
|Aracı kalınlığı artırın|]|

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[3B varlıklarıyla oyunları ve uygulamaları için çalışma](../designers/working-with-3-d-assets-for-games-and-apps.md)|Visual Studio'da dokuları, görüntüler, 3B modeller ve gölgelendirici etkileri gibi grafik varlıklar çalışmak için kullanabileceğiniz araçlar genel bir bakış sağlar.|
|[Model Düzenleyicisi](../designers/model-editor.md)|3B modeller ile çalışmak için Visual Studio Model Düzenleyicisi'ni kullanmayı açıklar.|
|[Gölgelendirici Tasarımcısı](../designers/shader-designer.md)|Visual Studio gölgelendirici Tasarımcısı gölgelendiriciler ile çalışmak için nasıl kullanılacağını açıklar.|