---
title: Visual Studio için Blend’i kullanarak kullanıcı arabirimi oluşturma
ms.date: 07/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- Blend.Start.Dev12
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c9c6f5febdf6ee3aacce0510f315a2f2c7b24bd4
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746890"
---
# <a name="creating-a-ui-by-using-blend-for-visual-studio"></a>Visual Studio için Blend’i kullanarak kullanıcı arabirimi oluşturma

Visual Studio için Blend tasarım XAML tabanlı Windows ve Web uygulamaları yardımcı olur. Visual Studio aynı temel XAML tasarım deneyimi sağlar ve animasyonları ve davranışları gibi gelişmiş görevler için görsel tasarımcılar ekler. Harmanlama ve Visual Studio arasında bir karşılaştırma için bkz: [Visual Studio ve Visual Studio için Blend'de XAML tasarlama](../designers/designing-xaml-in-visual-studio.md).

Visual Studio için Blend, Visual Studio'nun bir bileşenidir. Harmanlama, yüklemek için **Visual Studio yükleyicisi** seçin **Evrensel Windows platformu geliştirme** veya **.NET masaüstü geliştirme** iş yükü. Bu iş yükleri her ikisi de Visual Studio bileşeni için Blend içerir.

![UWP iş yükü bileşenleri](media/installer-uwp.png)&nbsp;&nbsp;&nbsp;&nbsp;![.NET masaüstü geliştirme iş yükü bileşenleri](media/installer-dotnet-desktop.png)

Visual Studio için Blend yeniyseniz, çalışma alanının benzersiz özelliklerle tanımak için bir dakikanızı ayırın. Bu konu hakkında hızlı bir tur alır.

> [!NOTE]
> Çalışma yüzeyi, Belge Anahattı penceresi ve aygıt penceresi gibi paylaşılan tasarım özellikleri turu için bkz: [XAML Tasarımcısını kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

## <a name="tour-of-the-tools-panel"></a>Araçlar panelinde turu

Kullanabileceğiniz **Araçları** uygulamanızdaki nesneleri oluşturup değiştirmesi Visual Studio için Blend panelinde. Bir aracı seçerek ve farenizi ile yüzeyinde çizim nesneleri oluşturun.

![Araçlar paneli](../designers/media/blend5toolspanel.png)

|||||
|-|-|-|-|
|![](../designers/media/b1_1.png)|**Seçim araçları** nesneleri ve yolları seçin.<br /><br /> Kullanım **doğrudan seçim** iç içe geçmiş nesnelerde ve yol kesimleri seçmek için aracı.|![Belirtme çizgisi A](../designers/media/b5_label_a.png)|**Gradyan ve fırça araçları**|
|![](../designers/media/b1_2.png)|**Görünüm Araçları** kaydırma ve yakınlaştırma için çalışma yüzeyi görünümünü gibi ayarlayın.|![Belirtme çizgisi B](../designers/media/b5_label_b.png)|**Yol araçları**|
|![](../designers/media/b1_3.png)|**Fırça Araçları** fırça dönüştürme, bir nesne boyama veya başka bir nesneye uygulamak için bir nesne öznitelikleri seçerek gibi bir nesne visual özniteliklerini ile çalışırsınız.|![Belirtme çizgisi C](../designers/media/b5_label_c.png)|**Şekil araçları**|
|![](../designers/media/b1_4.png)|**Nesne Araçları** yüzeyinde yolları, şekiller, Düzen panelleri, metin ve denetimleri gibi en yaygın nesneleri çizin.|![Belirtme çizgisi D](../designers/media/b5_label_d.png)|**Düzen panelleri**|
|![](../designers/media/b1_5.png)|**Varlık Araçları** erişim **varlıklar** panel ve en son göstermek için varlık kitaplıktan kullanılır.|![Belirtme çizgisi E](../designers/media/b5_label_e.png)|**Metin denetimleri**|
|||![Belirtme çizgisi F](../designers/media/b5_label_f.png)|**Ortak Denetimler**|

**Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.png) [araç](https://www.youtube.com/watch?v=VkdUJcvoo54&list=PLBDF977B2F1DAB358&index=4).

## <a name="tour-of-the-assets-panel"></a>Varlıklarını Masası turu

İçindeki tüm denetimler bulabilirsiniz **varlıklar** paneli, benzer **araç** Visual Studio. Denetimleri yanı sıra, her şeyi, yüzeyi için ekleme bulabilirsiniz **varlıklar** paneli, stiller, ortam, davranışları ve efektler dahil olmak üzere.

![Varlıklar paneli](../designers/media/blend5_assets_panel.png)

|||
|-|-|
|![](../designers/media/b1_1.png)|**Arama kutusuna** yazın **arama** varlıklar listesini filtrelemek için kutusu.|
|![](../designers/media/b1_2.png)|**Kılavuz modu ve liste modu** arasında geçiş **kılavuz modunu** Görünüm ve **listesi modu** varlıklar görünümü.|
|![](../designers/media/b1_3.png)|**Varlıklar kategorileri** bir kategori veya alt kategoriye varlıklar listesini görüntülemek için tıklatın.|
|![](../designers/media/b1_4.png)|**Stilleri** kaynak sözlükte bulunan tüm stilleri gösterir.|
|![](../designers/media/b1_5.png)|**Açıklama** seçili varlıklar kategori veya alt kategori açıklamasını görüntüleyin.|

## <a name="tour-of-the-objects-and-timeline-panel"></a>Zaman Çizelgesi ve nesneleri turu paneli

Bu pano, yüzeyinde nesneleri düzenlemek için kullanın ve bunları animasyon eklemek istiyorsanız.

![Animasyon modunda nesne ve zaman çizelgesi paneli](../designers/media/b5_object_timeline_animation.png)

|||
|-|-|
|![](../designers/media/b1_1.png)|**Görünüm nesneleri** görsel ağaç belgenin görüntüleyin. Farklı ayrıntı düzeyleri aşağıya doğru inebilir. Daha fazla yüzeyinde nesneleri düzenlemek için Katmanlar de ekleyebilirsiniz. Bu şekilde kilitlemek ve onları bir grup olarak gizleyebilirsiniz.|
|![](../designers/media/b1_2.png)|**Kayıt modu göstergesi** bir zaman çizelgesinde özellik değişiklikleri kaydederken olup olmadığını bakın.|
|![](../designers/media/b1_3.png)|**Film şeridi Seçici** oluşturduğunuz film şeritleri listesini görüntüleyin.|
|![](../designers/media/b1_4.png)|**Kapat film şeridi** geçerli film şeridi kapatın.|
|![](../designers/media/b1_5.png)|**Film şeridi seçenekleri** oluşturun, yinelenen, ters silin, yeniden adlandırmak veya film şeridi kapatın.|
|![](../designers/media/b1_6.png)|**Kayıttan yürütme denetimlerini** zaman çizelgesi boyunca gidin. Gezinmek için oynatma sürükleyebilirsiniz (veya *Temizle*) zaman çizelgesi.|
|![](../designers/media/b1_7.png)|**Kapsamına iade** nesneleri görüntülemek önceki kök nesnesi veya önceki kapsam için kapsam. Stil veya şablonu yalnızca değişiklik yaptığınız zaman bunu yapabilirsiniz.|
|![](../designers/media/b1_8.png)|**Bir ana kare kayıt** geçerli noktada seçili nesnenin özelliklerini görüntüsünü sürede kaydedin.|
|![](../designers/media/b1_9.png)|**Tutturma seçenekleri** tutturma zaman çizelgesi ayarlamak, ek çözümleme ve zaman çizelgesi tutturma devre dışı bırakma.|
|![](../designers/media/97fa60b9-0caf-4387-9225-b57510d32209.png)|**Göster/Gizle**, **kilit ve kilidini** göster veya görünürlük gizleme ve nesneleri görüntülemek için seçenekler kilitleme.|
|![](../designers/media/b1_11.png)|**Zaman Çizelgesi oynatma konumuna** geçerli süresini milisaniye olarak gösterir. Zaman içinde belirli bir noktaya atlamak için bu alana doğrudan bir zaman değeri girebilirsiniz. Duyarlık kümesinde ek çözümleme bağlıdır **tutturma seçenekleri**.|
|![](../designers/media/b1_12.png)|**Oynatma** ne animasyonun adresindeki zaman noktasından belirleyin. Animasyonun önizlemesini görüntülemek için, oynatma kafasını zaman çizelgesi boyunca sürükleyebilirsiniz.|
|![](../designers/media/b1_13.png)|**Zaman çizelgelerini üzerinde ayarlanmış ana kare** zamanında belirli bir noktada bir özellik değeri değiştirin.|
|![](../designers/media/d839d12c-07a1-4127-a830-4a8e7069f4fe.png)|**Nesnelerin sırasını değiştirmek** nesneleri görüntüleme sırasını ayarlayın. Nesneleri yapısı görünümünde Z düzenini (ön geri) veya işaretleme sıraya göre düzenlemek için bu düğmeye tıklayın (göründükleri içinde sipariş **XAML** Görünüm).|
|![](../designers/media/b1_15.png)|**Zaman çizelgesi yakınlaştırma** zaman çizelgesinin yakınlaştırma çözünürlüğünü ayarlayın. Yakınlaştırma bir animasyonu daha ayrıntılı düzenlemenize izin verir ve uzaklaştırmaysa daha uzun süreler boyunca neler olduğuna ilişkin daha kapsamlı bir özet gösterir. Yakınlaştırma yapar, ancak zaman içinde istediğiniz konumunda bir ana kare ayarlayamazsınız, yaslama çözünürlüğünün yeterince yüksek olarak ayarlandığını doğrulayın.|
|![Belirtme çizgisi 16](../designers/media/b5_label_16.png)|**Zaman Çizelgesi oluşturma alanını** zaman çizelgesi görüntülemek ve ana kare sürükleyerek veya kendi kısayol menülerini kullanarak taşıyabilirsiniz.|

## <a name="tour-of-the-properties-panel"></a>Özellikleri paneli turu

Bu panoyu görüntülemek ve bir nesne özelliklerini değiştirmek için kullanın. Bunları doğrudan yüzeyinde de ayarlayabilirsiniz. Bunu yaparsanız, özellik değişikliklerini yansıtılır **özellikleri** paneli.

![Özellikler paneli](../designers/media/blend5_properties_panel.png)

**Kategoriler** özellikleri kategorilerini genişletme ve daraltma. Tıklatın **genişletme** ![](../designers/media/6375953d-074c-421a-bbb3-6f5055b67b64.png) ve **Daralt** ![Daralt](../designers/media/b5_collapse_button.png) kategorisi ayrıntıları göstermek veya gizlemek için.

|||
|-|-|
|![](../designers/media/b1_1.png)|**Ad ve tür** simgesi, adını ve seçili nesnenin türünü görüntüleyin.|
|![](../designers/media/b1_2.png)|**Düzenleme ölçütü** adı, kaynak veya kategoriye göre alfabetik olarak özelliklerini düzenleyin.|
|![](../designers/media/b1_3.png)|**Fırça özellikleri** Fırçalar dolgu fırça, vuruş fırça ve ön plan Fırçası gibi görsel özelliklerini ayarlayın.|
|![](../designers/media/b1_4.png)|**Renk Düzenleyicisi** düz renk ve gradyan fırçalar için kullanın.|
|![](../designers/media/b1_5.png)|**Renk Seçici** bir renk seçin.|
|![](../designers/media/b1_6.png)|**Renk yongaları** başlangıç rengini, geçerli renk ve son rengi görüntüleyin|
|![](../designers/media/b1_7.png)|**Damlalıkları** ekranınızda herhangi öğesinin rengini kullanın. **Renk Damlalık** kullanılabilir olduğunda **düz renk fırça** seçilir. **Gradyan Damlalık** kullanılabilir olduğunda **gradyan fırçası** seçilir.|
|![](../designers/media/b1_8.png)|**Özellikleri ve olayları** özelliklerini ayarlama veya seçili öğe için olayları seçin.|
|![](../designers/media/b1_9.png)|**Arama kutusuna** özellikleri arayın. Filtre yazarak görüntülenen özellikleri **arama** kutusu.|
|![](../designers/media/97fa60b9-0caf-4387-9225-b57510d32209.png)|**Fırça Düzenleyicisi sekmeleri** fırça Düzenleyicisi seçmek için kullanın. Seçebileceğiniz **hiçbir fırça**, **düz renk fırça**, **gradyan fırçası**, **döşeme fırça**, veya **fırça kaynak**.|
|![](../designers/media/b1_11.png)|**Renk kaynakları** tam aynı renk farklı özellikleri için geçerlidir. **Renk kaynakları** sekmesi içerir **yerel kaynaklar** ve **sistem kaynaklarını**.|
|![](../designers/media/b1_12.png)|**RGB renk alanını** değerlerini ayarlayarak rengi değiştirme **R**, **G**, veya **B** numara Düzenleyicileri (kırmızı, yeşil, mavi).|
|![](../designers/media/b1_13.png)|**Alfa kanal** yanına numara Düzenleyicisi'ni kullanarak alfa değeri değiştirmek **A**.|
|![](../designers/media/d839d12c-07a1-4127-a830-4a8e7069f4fe.png)|**Renk kaynağına dönüştürme** seçili rengi renk kaynak Dönüştür. Renk Kaynaklar sekmesini tıkladığınızda renk kaynaklar kullanılabilir.|
|![](../designers/media/b1_15.png)|**Onaltılı değerini** görüntülenen rengi on altılık değeri görüntüleyin.|
|![Belirtme çizgisi 16](../designers/media/b5_label_16.png)|**Gradyan kaydırıcı** yalnızca bir gradyan fırçası seçtiyseniz görünür.|
|![](../designers/media/d50027a1-6824-4ad8-8b4e-558b0756dcf8.png)|**Gelişmiş Özellikler Göster** kategorilerini daha az yaygın olarak kullanılan özelliklerini görüntüleyin.|

**Kısa bir video izlemek:** ![yüklü Özellikleri Yapılandır](../designers/media/bldadminconsoleinitialconfigicon.png) [özellikleri paneli](https://www.youtube.com/watch?v=HCqQfiobdag&list=PLBDF977B2F1DAB358&index=7).

## <a name="see-also"></a>Ayrıca bkz.

- [Denetimler ekleme ve bunların davranışlarını değiştirme](../designers/insert-controls-and-modify-their-behavior-in-xaml-designer.md)
- [Nesnelere animasyon ekleme](../designers/animate-objects-in-xaml-designer.md)
- [Şekiller ve yollar çizme](../designers/draw-shapes-and-paths.md)
- [Visual Studio ve Visual Studio için Blend'de XAML tasarlama](../designers/designing-xaml-in-visual-studio.md)