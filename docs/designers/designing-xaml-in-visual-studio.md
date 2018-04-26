---
title: Visual Studio'da XAML tasarlama
ms.date: 07/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 288e2415-9fcf-408e-bc35-9848315e14fd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: c4ebc75ccd436b36e6f96bdc94372ee37b048989
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="design-xaml-in-visual-studio"></a>Visual Studio'da XAML tasarım

Çeşitli uygulama türleri için XAML ile zengin medya deneyimlerini ve Visual Studio ve Visual Studio için Blend kullanıcı arabirimleri çekici oluşturma için görsel araçlar sağlar. Her iki araçları ortak bir görsel XAML Düzenleyicisi'ni dahil olmak üzere özelliklerini sahip, ancak animasyon ve davranışları gibi daha gelişmiş görevler için Visual Studio için Blend ek tasarım araçlar sağlar.

Bir uygulama tasarlama işlemi seçtiğiniz aracı ve hedef platformunuzu bağlıdır. Bu makalede, Visual Studio ve Visual Studio için Blend'de XAML Tasarım araçları karşılaştırır. Araçları kullanarak, daha ayrıntılı izlenecek yollar için aşağıdaki konulara bakın:

- [Visual Studio’da XAML Tasarımcısı’nı kullanarak kullanıcı arabirimi oluşturma](creating-a-ui-by-using-xaml-designer-in-visual-studio.md)
- [Visual Studio için Blend’i kullanarak kullanıcı arabirimi oluşturma](creating-a-ui-by-using-blend-for-visual-studio.md)

## <a name="choose-the-right-tool"></a>Doğru aracı seçin

Tasarım araçları seçiminizi yetenek kümesi üzerinde büyük ölçüde bağlıdır. Daha fazla kod odaklı varsa, daha gelişmiş tasarım görevleri gerçekleştirmek için Visual Studio'da XAML kod yazabilirsiniz. Daha fazla tasarım kaynaklı olan, Visual Studio için Blend kod yazmadan gelişmiş görevleri gerçekleştirmenize olanak sağlar.

Visual Studio ve Visual Studio için Blend arasında ileri ve geri geçiş yapabilirsiniz ve aynı anda hem de aynı projeyi bile olabilir. Diğer IDE geçiş yaptığınızda bir IDE XAML dosyalarda yapılan değişiklikleri otomatik yeniden yüklemeye uygulanabilir. Seçeneklerinde aracılığıyla yeniden yükleme davranışını kontrol edebilirsiniz **Araçları**, **seçenekleri** IDE ya da iletişim kutusunda.

### <a name="shared-capabilities"></a>Paylaşılan Özellikleri

En temel görevler için Visual Studio IDE ve Visual Studio için Blend paylaşır windows ve özellikleri, aynı kümesini bazı farklar. Bazı önemli noktalar:

- **Tutarlı bir kullanıcı arabirimi:** tanıdık bağlamında uygulamalarınızı daha eğlenceli ve üretken bir deneyim IDE arasında geçiş yapar Visual Studio kullanıcı arabiriminin tasarlayabilirsiniz. Visual Studio kullanımlar odaklanmanıza yardımcı olan Visual Studio koyu tema içeriğinizi ve kullanıcı arabirimi arasında karşıtlığı geliştirerek tasarlarken içerik üzerinde karışır. Bkz: [XAML Tasarımcısını kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

     ![Visual Studio IDE için Blend](../designers/media/blendide.png "BlendIDE")

- **XAML IntelliSense:** hem IDE desteği tüm IntelliSense deyim tamamlama, yorum oluşturma ve biçimlendirme kodu ve kaynaklara, gezinti gibi ortak Düzenleyicisi işlemleri için destek dahil olmak üzere gelen beklediğiniz ortak özellikleri bağlama ve kod.

- **Temel özellikleri hata ayıklama:** karışım çalışan uygulamanızın hatalarını ayıklama için kodunda kesme noktalarını ayarlama dahil olmak üzere, şimdi ayıklayabilirsiniz. Visual Studio ile hata ayıklama tutarlı bir deneyim sağlamak için Visual Studio için Blend Visual Studio'nun hata ayıklama windows ve araç çubuklarını çoğunu içerir. Gelişmiş hata ayıklama yetenekleri gibi tanılama ve Kod Analizi yalnızca Visual Studio'da kullanılabilir. Bkz: [Visual Studio'da hata ayıklamayı](../debugger/debugging-in-visual-studio.md).

- **Dosya yeniden yükleme deneyimi:** sahip düzenlenen dosyalarınızı yeniden otomatik olarak aralarında geçiş gibi ve XAML dosyalarınızda ya da Visual Studio için Blend veya Visual Studio düzenleyebilirsiniz. İş akışı kesintileri en aza indirmek için artık dosyanızı yeniden Tercihler dosyası yeniden Yükle iletişim kutusunda ayarlayabilirsiniz.

     ![Dosya yeniden yükleme deneyimi](../designers/media/blendfilereload.png "BlendFileReload")

- **Eşitlenen düzenleri ve ayarları:** özel düzenler kaydedebilir ve aracı pencere düzenini özelleştirmeleri uygulayabilirsiniz olanak tanır. Aynı Microsoft hesabı ile oturum açtığınızda visual Studio bu özelleştirmeler ve Visual Studio ve Visual Studio için Blend tercihlerini makinelerde eşitler. Bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

- **Ortak bir Çözüm Gezgini:** Çözüm Gezgini projelerinizi ve bunların dosyaları, yanı sıra ilişkili komutlara hazır erişim düzenli bir görünümünü ile sağlar. Çözüm Gezgini büyük kurumsal projelerle çalışmak daha kolay olur. Bkz: [çözümler ve projeler](../ide/solutions-and-projects-in-visual-studio.md).

- **Takım Gezgini:** Takım Gezgini ile projelerinizi takım işbirliği kolaylaştırmak için GIT veya TFS depoları ile yönetebilirsiniz. Bkz: [Takım Gezgini'nde iş](http://msdn.microsoft.com/Library/fd7a5cf7-7916-4fa0-b5e6-5a83cf377a02).

- **NuGet:** NuGet paketlerini Visual Studio ve Visual Studio için Blend yönetebilirsiniz. NuGet Paket Yöneticisi yükleme ve bir çözümden paketlerin kaldırılmasını kolaylaştırır .NET Framework için ' dir.

## <a name="advanced-capabilities-in-blend-for-visual-studio"></a>Visual Studio için blend'de Gelişmiş özellikleri

Verimliliğinizi artırmak için aşağıdaki görevler için Visual Studio için Blend kullanarak göz önünde bulundurun. Bu, Visual Studio için Blend daha fazla hızı ve işlevleri Visual Studio Tasarımcısı veya tek başına kodu daha burada sunan alanlarıdır.

|Bitiş|Visual Studio|Visual Studio için Blend|Daha fazla bilgi|
|--------|-------------------|-----------------------------|----------------------|
|**Animasyon oluşturma**|Animasyon için tasarım aracı yoktur; Program aracılığıyla oluşturmanız gerekir. Bu animasyon ve zamanlama sistemini WPF ve kapsamlı kodlama uzmanlık bilinmesini gerektirir.|Animasyon görsel olarak oluşturabilir ve bunları Visual Studio için blend'de önizleyebilirsiniz. Bu daha hızlı ve kodda, animasyon oluşturma daha kesin değildir. Kullanıcı etkileşimi işlemek için Tetikleyiciler ekleyebilirsiniz ve olay işleyicileri ve diğer işlevleri eklemek için kodu geçiş yapabilirsiniz.|[Nesnelere animasyon ekleme](../designers/animate-objects-in-xaml-designer.md)|
|**Şekil ve metinler daha kolay işleme için yollar dönüştürmek**|Desteklenmez.|Hafif veya çarpıcı (örneğin, dikdörtgenler ve üç nokta) şekillere daha iyi düzenleme denetimi sağlamak yollara dönüştürerek değişiklik yapabilirsiniz.  Yeniden şekillendirmek veya yolları birleştirmek ve birden çok şekillerden bileşik yollar oluşturabilir.<br /><br /> Vektör görüntüler olarak işlemek için yollar metin blokları dönüştürebilirsiniz.|[Şekiller ve yollar çizme](../designers/draw-shapes-and-paths.md)|
|**Etkileşim, UI tasarımları ekleme**|C#, Visual Basic ya da C++ kodu gerektirir.|Sürükle ve bırak davranışları statik sizin tasarımlar etkileşim eklemek için denetimleri üzerine. Davranışları sürükle ve bırak, yakınlaştırma ve görsel durum değişiklikleri gibi işlevleri kapsülleyen kullanıma hazır kod parçacıkları ' dir. Aralarından seçim yapabileceğiniz davranışları artan bir dizi yoktur ve kendi oluşturabilirsiniz.<br /><br /> Visual Studio için blend'de özelliklerini değiştirerek veya kodda olay işleyicileri ekleme sonra her davranışını özelleştirebilirsiniz.|[Denetimler ekleme ve bunların davranışlarını değiştirme](../designers/insert-controls-and-modify-their-behavior-in-xaml-designer.md)|
|**Adobe resmi kullanın**|Desteklenmez.|Adobe FXG, PhotoShop veya Illustrator resmi almak ve Visual Studio için blend'de kullanıcı arabirimini uygular.|[Görüntü, video ve ses klipleri ekleme](../designers/insert-images-videos-and-audio-clips-in-xaml-designer.md)|
|**Denetimleri, şablonlar ve stiller Düzenle**|Kodlama ve WPF stilleri ve şablonları bilgisi gerektirir.|Herhangi bir görüntü denetime açın.<br /><br /> Düzenleme araçları şablonu denetimleri, stil ve birkaç kere fareyi tıklatarak şablonlarıyla değişiklikler yapmak için kullanın.<br /><br /> Örneğin, Visual Studio stil kaynakları için Blend (örneğin, düğmeleri, liste kutuları, kaydırma çubukları, menüler, vb.) genel WPF denetimlerinin uygulamak ve kendi renk, stil veya doğrudan Visual Studio için blend'de temel şablonu değiştirmek için kullanabilirsiniz. İstiyorsanız, son rötuşları kodunu sonra dönebilirsiniz.|[Nesnelerin stilini değiştirme](../designers/modify-the-style-of-objects-in-blend.md)|
|**UI verilere bağlanma**|SQL Server veritabanları, WCF veya web Hizmetleri, nesneler veya SharePoint listeleri gibi bir veri kaynağı oluşturun ve veri kaynağı UI denetimlerinizi bağlayın.<br /><br /> Tasarım zamanı verileri etkileşimli tasarım deneyimi için el ile oluşturulması gerekir.|Örnek veriler prototip oluşturma ve test etme için kolayca oluşturun. Hazır olduğunuzda canlı veri anahtarı.<br /><br /> Harmanlama özellikleri bekleyen Visual Studio'nun veri oluşturma için (ekleyebilirsiniz ad, sayılar, URL'ler, anında üzerinde kolayca fotoğraf) ve çok zaman kazandırabilir.<br /><br /> Dinamik veri için bir XML dosyasına veya herhangi bir CLR veri kaynağı, kullanıcı Arabirimi denetimlerini bağlayabilirsiniz.|[Verileri görüntüleme](../designers/display-data-in-blend.md)|

Gelişmiş XAML tasarımı hakkında daha fazla bilgi için bkz: [Visual Studio için Blend'i kullanarak kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-blend-for-visual-studio.md).
