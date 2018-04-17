---
title: Menüler ve Visual Studio için komutları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 0a1ed675-2bd1-4603-ba3a-f40dfb5cfb69
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 16f67faf7ffe3a3fd119b7ddf002ab463822a830
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="menus-and-commands-for-visual-studio"></a>Menüleri ve Visual Studio komutları
## <a name="command-usage"></a>Komutu kullanım  
  
### <a name="overview"></a>Genel Bakış  
 Birçok ayrı ürün oluşur bir paketidir, Microsoft Office Visual Studio ürününe her genel Visual Studio IDE için kendi komut kümelerini katkıda içerir. IDE bağlama göre kullanıcı mevcut olan işlevlere filtreleyerek komutları binlerce karmaşıklığını yönetir.  
  
 Bir kullanıcının bağlamında değiştirir - tasarım penceresinden penceresi düzenleme bir kod değiştirme gibi - işlevselliği ilişkisiz kaldırdığınızda yeni bağlam kaybolur. Aynı anda, özellikleri ve araç seçenekleri gibi ilgili dinamik bilgileriyle birlikte yeni işlevsellik yüzeyleri. Kullanıcı kullanılabilir komut kümesini değiştirme dikkat etmelidir değil. Kullanıcı dikkatinizin veya görüntülenmesini veya kayboluyor komutlarla kafası ise, kullanıcı Arabirimi tasarımı ayarlaması gerekir. Kullanıcının geçerli içerik her zaman bir veya daha fazla yollarla gibi IDE başlık çubuğu, Özellikler penceresini veya özellik sayfaları iletişim kutusu gösterilir.  
  
 Komut çubukları UI esneklik sağlar. Yalnızca komut ortamı olan ana menü ve her ikisi de özelleştirilebilir ve hatta gizli ana komut çubuğunda Visual Studio devralınmış yapıları. Diğer komut çubukları görüntülenir ve uygulama durumuna göre kaybolur. Araç pencereleri ve belge düzenleyicileri katıştırılmış araç çubukları penceresi kenarlarına içinde de içerebilir.  
  
#### <a name="basic-guidelines"></a>Temel yönergeleri  
  
##### <a name="use-existing-shared-commands-command-groups-and-menus-whenever-possible"></a>Var olan paylaşılan komutları, komut grupları ve menüleri mümkün olduğunca kullanın.  
 Komutları genellikle içeriğine göre gösterilen olduğundan, varolan paylaşılan menüleri ve komut grupları kullanımını komut yapısını bağlamda değişiklikler arasında göreceli olarak tutarlı kalmasını sağlar. Paylaşılan komutları yeniden kullanmak ve ilgili paylaşılan komutları yakın yeni komutları yerleştirmeyi de IDE karmaşıklığını azaltır ve daha kullanıcı dostu bir deneyim oluşturur. Yeni bir komut tanımlanmış olması gerekiyorsa, varolan bir paylaşılan komut grubu yerleştirmeyi deneyin. Yeni bir grup tanımlanmış olması gerekiyorsa, ilgili komut grubu yakın varolan bir paylaşılan menüsüne yeni bir üst düzey menü oluşturmadan önce yerleştirin.  
  
##### <a name="do-not-create-icons-for-every-command"></a>Her komut için simgeler oluşturmayın.  
 Komut simgesinin oluşturmadan önce dikkatle düşünün. Simgeler, yalnızca komutları için oluşturulmuş olması:  
  
-   Varsayılan araç çubuğunda görünür.  
  
-   araç çubuğu aracılığıyla için kullanıcılar tarafından eklenecek olasılığı olan **Özelleştir...**  iletişim.  
  
-   başka bir Microsoft ürünü üzerinde aynı eylemiyle ilişkili bir simgesi vardır.  
  
##### <a name="limit-the-addition-of-keyboard-shortcuts"></a>Klavye kısayolları eklenmesi sınırla  
 Kullanıcıların çoğunluğu tüm kullanılabilir kısayolları küçük bir bölümünü kullanın. Şüpheli olduğunda, özellik için bir klavye kısayolu bağlamayın. Kullanıcı ile çalışma kısayollar eklemeden önce takım karşılaşırsınız.  
  
##### <a name="give-commands-a-default-menu-placement"></a>Varsayılan menü yerleştirme komutları verin.  
 Komutlarınızı başkaları tarafından özelleştirilmiş ve buna uygun olarak tasarlamanız unutmayın. Gizli bir komut olarak böyle bir şey yoktur. Tüm Visual Studio komutları görünür **Araçlar > Özelleştir** iletişim kutusunda, komut penceresinde otomatik tamamlama **Araçlar > Seçenekler > klavye** iletişim ve geliştirme araçları ortamı (DTE). Kullanıcıların bunları kolayca bulabilmeniz için bir ad ve araç ipucu .ctc dosyanızdaki komutlarınızı koyduğunuzdan emin olun.  
  
##### <a name="do-not-duplicate-shared-commands-on-an-embedded-toolbar"></a>Katıştırılmış araç çubuğunda paylaşılan komutları yinelenen değil.  
 Kullanıcının odak alanı yakın komutları yerleştirmek yararlıdır. Bunu yapmanın bir yolu katıştırılmış bir araç çubuğu Düzenleyicisi araç penceresi veya belgenin en üstte oluşturmaktır. Araç çubuğunda yerleştirilen komutları penceresi içinde içerik bölgeye özgü olmalıdır. Bu araç çubuklarında paylaşılan komutları yinelenen değil. Örneğin, bir "Kaydet" simgesi katıştırılmış araç içinde hiçbir zaman yerleştirin.  
  
### <a name="content-and-command-visibility"></a>İçerik ve komut görünürlüğü  
 Komutları mevcut şu kapsamlarda: **ortam**, **hiyerarşi**, ve **belge**. Komut yerleşimi kullanmayacağınıza için her kapsam bilmesi.  
  
 İçindeki komutlar **ortam** kapsamı birincil içeriği oluşturmak ve birden çok bağlamları arasında paylaşılır. Bunlar, görünürlüğünü ya da belgeler ve aracı windows düzenini değiştirin. Kapsam ortamında komutları arasındadır **yeni proje**, **sunucuya Bağlan**, **ekleme işlemi**, **Kes**,  **Kopya**, **Yapıştır**, **Bul**, **seçenekleri**, **özelleştirme**, **yeni pencere**, ve **görüntülemek Yardım**.  
  
 İçindeki komutlar **hiyerarşi** kapsamını yönetmek Visual Studio dahil olmak üzere de hiyerarşileri **proje**, **takım**, ve **veri**. İçin bir projenin üzere - örneğin, ilişkili oldukları **hata ayıklama**, **yapı**, **Test**, **mimarisi**, veya **Çözümle** . Kapsam hiyerarşi komutlarda arasındadır **Yeni Öğe Ekle**, **yeni sorgu**, **proje ayarları**, **yeni veri kaynağı Ekle**, **Performans Sihirbazı**, ve **yeni diyagram**.  
  
 İçindeki komutlar **belge** kod, tasarım veya bir iş öğesi sorgusunu (WIQ) gibi bir belge içeriğine kapsam eylemidir. Bunlar ayrıca araç penceresi görünümünde hareket veya aksi takdirde, araç penceresi özeldir. Belge kapsam komutları da hareket kendileri gibi hiyerarşi özgü dosya nesneler üzerinde **projeden kaldırmak**. Belgedeki komutları arasında kapsamı olan **yeniden düzenlemeniz > yeniden adlandırma**, **iş öğesi kopyası oluştur**, **Tümünü Genişlet**, **Tümünü Daralt**, ve **Kullanıcı görev oluşturma**.  
  
### <a name="command-placement-decisions"></a>Komut yerleştirme kararları  
 Bir komut oluşturmak karar verdim sonra uygun yerleşimi ve bir klavye kısayolu oluşturulup oluşturulmayacağını belirler gerekir. Komut nereye yerleştireceğinizi kurmak için bu kararı yolu izleyin:  
  
 ![Komut yerleştirme karar grafiği](../../extensibility/ux-guidelines/media/0501-a_commandplacement.png "0501 a_CommandPlacement")  
  
 **Visual Studio komut yerleşimi için karar yolu**  
  
### <a name="command-placement-in-menus"></a>Menülerde komut yerleşimi  
  
#### <a name="main-menu-bar"></a>Ana menü çubuğu  
 Ana menü çubuğu UI katkıda bulunan herhangi bir özel bağlam menüsü paket komutlar için standart konum olmalıdır. Ana menü çubuğu ortamı hangi komutların görünür denetlemek için kullandığı diğer komut yapıları farklıdır. Diğer tüm komut çubukları, bağlam dışında olan komutları yalnızca devre dışı bir menüsü veya bir araç çubuğunda yer alır.  
  
 Ortamı, tüm IDE ve birden çok görev etki alanları arasında ortak olan ana menü çubuğu'na yerleşik komut kümesini tanımlar. Bu komutlar her zaman ne olursa olsun VSPackages ortama yüklenen görülebilir. Bu komut kümesini VSPackages genişletebilmenize karşın, her ürün ve bunların komutları yerleşimini set komutu her takım sorumluluğundadır.  
  
 Visual Studio ana menü yapısını aşağıdaki menü kategorilere ayrılabilir:  
  
##### <a name="core-menus"></a>Çekirdek menüleri  
  
-   Dosya  
  
-   Düzenle  
  
-   Görüntüle  
  
-   Araçlar  
  
-   Pencere  
  
-   Yardım  
  
##### <a name="project-specific-menus"></a>Proje özgü menüler  
  
-   Proje  
  
-   Derleme  
  
-   Hata ayıklama  
  
##### <a name="context-specific-menus"></a>Bağlama özgü menüleri  
  
-   Takım  
  
-   Veri  
  
-   Test  
  
-   Mimari  
  
-   Çözümle  
  
##### <a name="document-specific-menus"></a>Belge özgü menüler  
  
-   Biçimi  
  
-   Tablo  
  
##### <a name="when-designing-main-menus-adhere-to-these-rules"></a>Ana menü tasarlarken, bu kuralları uyar:  
  
-   Belirli bir bağlam 25 en üst düzey öğe aşamaz.  
  
-   Menüleri hiçbir zaman 600 piksel cinsinden yüksekliği aşmalıdır.  
  
-   Ultimate SKU ve genel profil gibi birden çok bağlamlarda ana menü değerlendirin.  
  
-   Açılan menüler kabul edilir.  
  
-   Açılan menüler en az üç öğe ve en fazla yedi içermelidir.  
  
-   Açılan menüler yalnızca bir düzey derinlikte gitmesi gereken - bazı Visual Studio menü öğeleri basamaklı alt menüler sahip, ancak bu deseni olmayan teşvik.  
  
-   En fazla altı ayırıcı kullanın. Aşağıdaki çizimde gruplandırmaları uyması:  
  
     ![Ana menü gruplandırma için yönergeleri](../../extensibility/ux-guidelines/media/0501-b_mainmenus.png "0501 b_MainMenus")  
  
-   Her gruplama şekilde sağlamak için gerekli olmasa da, ek gruplandırmaları ekleme sınırlıdır.  
  
-   Her gruplandırma iki yedi menü öğelerine sahip olması gerekir.  
  
#### <a name="main-menu-ordering"></a>Ana menü sıralama  
 Yeni bir üst düzey öğe eklemeden önce mevcut bir üst düzey menüye komut yerleştirmeyi düşünün. Yeni bir üst düzey menü eklerken, doğru konuma yerleştirmek emin olun. Menü proje, bağlam veya belge özgü olup olmadığına karar. En üst düzey menü adını kısa tutun ve yalnızca bir Word'ü kullanın.  
  
 Çekirdek menüleri bağlayıcının komutları geri kalanı gerekir. Dosya, düzenleme ve görünümü her zaman sol ve araçları, penceresinde olmalıdır ve Yardım her zaman sağ tarafta olmalıdır.  
  
#### <a name="context-menus"></a>Bağlam menüleri  
 Bağlam menüleri içinde çok fazla işlevsellik yerleştirme öğrenin zor bir arabiriminde sonuçlanır. Tüm önde gelen işlevselliği ana menü çubuğu yoluyla kullanılabilir olması gerekir. Komutları yerleşimini yinelenen komutları önlemek için mevcut komutları ile aynı olmalıdır. Bağlam menülerini Kabuk bağlam menüsü çözüm, proje düğümüne ya da bir proje öğesi için olmasına bağlı olarak dahil edilecek standart menü grupları tanımlar.  
  
 Bağlam menüleri tasarlarken, ana menüden için ve ayrıca aynı kurallara uyar:  
  
-   25 en üst düzey menü öğeleri geçmeyin.  
  
-   Açılan menüler kabul edilebilir, ancak gerekir derin bir düzey aşmaması - hiçbir zaman basamaklı çıkarmalar kullanın.  
  
-   En fazla altı ayırıcı kullanın.  
  
### <a name="command-placement-in-toolbars"></a>Araç çubuğundaki komut yerleşimi  
  
#### <a name="general-toolbars"></a>Genel araç çubukları  
 Tasarlama ve araç çubukları yerleştirme, bu standartları izleyin:  
  
-   Düğme başına birden fazla fiil kullanmayın. Bir düğme bir eylem =.  
  
-   Yalnızca bu etiketle güçlendirilmiş gerekiyorsa simgesinin yanında metin kullanın.  
  
-   Yalnızca tek bir oturumda birden çok kez da bırakılacak özellikleri için birleşik giriş kutusunu kullanın. Aksi takdirde özelliği başka bir yerde kullanıma sunar.  
  
-   Açılan kutunun genişliği kutusunu + % 30 içinde uzun öğenin genişliğini eşit olmalıdır. Örneğin, en uzun öğeye 200 piksel ise, birleşik giriş kutusu 260 piksel genişliğinde olmalıdır.  
  
-   Ayırıcılar kullanımını sınırlayın. Açılan şeklin görsel ayırıcı olarak davrandığı için bir açılır yanındaki ayırıcı karşı bir desen kullanılır.  
  
-   Simge grupları üç için altı simgeler içermelidir.  
  
-   Birden çok yararlı komutlarda niteleyicileri neden oluyorsa son ayarı depolayan bir Bölünmüş düğme kullanın:  
  
     ![Visual Studio düğmeleri bölme](../../extensibility/ux-guidelines/media/0501-c_splitbuttons.png "0501 c_SplitButtons")  
  
     **Bölünmüş düğme örneği. Sol taraftaki altı komutları, bunun yerine bir düğmeye uygun olamaz.**  
  
#### <a name="product-specific-toolbars"></a>Ürüne özgü araç çubukları  
 Her ürünün ürün yüklendikten sonra Visual Studio ilk başlatılışında sık kullanılan içeren bir varsayılan araç çubuğu ve önemli komutlar ve her ürünün varsayılan araç çubuğu görüntülenmelidir sağlayabilir.  
  
 Ürünler ve IDE tarafından sağlanan menü paylaşılan komutu grupları da. Her paylaşılan komutu grup kullanıcı için anlamlı bir şekilde ilgili komutları düzenlemek için amacı bir paylaşılan menü yerleştirilir. Karmaşıklığını azaltmak için bu paylaşılan komut yapısını yararlanmak önemlidir.  
  
#### <a name="global-toolbars"></a>Genel araç çubukları  
 Kutu dışında bir satır sağdaki sığması için genel araç çubukları gereklidir. Yeni bir genel araç çubuğu oluştururken, bu araç çubuğu türü için yönergeleri izleyin.  
  
 **Genel araç yönergeleri:**  
  
-   Her bir araç çubuğu 24 piksel ortak denetimleri (kavrayıcının, taşma) sahiptir.  
  
-   Her araç çubuğu düğmesi 22 doldurma dahil olmak üzere geniş pikseldir. Bölünmüş düğme simgesi yapmadan başka bir 11 piksel genişliği ekler.  
  
-   Araç çubukları arasında komutların çoğaltma izin verilir.  
  
 **Belgeye özel araç çubukları** belirli bir dosya türü etkin olduğunda görünür ve farklı bir dosya türü etkin olduğunda kaybolur.  
  
-   Belgeye özel araç çubukları 12'den fazla düğmeleri olmayabilir.  
  
-   Araç çubuğu toplam genişliğini 300 piksel aşamaz.  
  
-   Her dosya türü bir katıştırılmış araç veya bir belge özgü genel araç ancak ikisini olabilir.  
  
 **Bağlama özgü araç çubukları** belirli bir bağlam atandıklarında kümesidir ve uzun süreler etkin kalacak eğilimindedir.  
  
-   Düğme için tüm içerik özel araç çubukları 18 sınırıdır.  
  
-   Bağlam etkin olduğunda kullanıcıların çoğunun bu araç çubuğunun komutları tutarlı bir şekilde işe olmaz alırsanız, bu araç bağlamı ile ilişkilendirme.  
  
-   Araç çubuğu bağlam çıkarken kaybolur emin olun. Bu araç çubukları hiçbiri başlangıçta görüntülenmelidir.  
  
 **Araç çubukları bağlam ile** hiçbir zaman otomatik olarak görüntülenir. Bunlar yalnızca, kullanıcı onları etkinleştirir gösterir. En büyük genişliği 200 piksel altında tutun.  
  
### <a name="general-organization-and-shell-defined-groups"></a>Genel kuruluş ve Kabuk tanımlı grupları  
 Var olan paylaşılan komutları, komut grupları ve menüleri kullanın. Yeni bir komut tanımlanmış olması gerekiyorsa, varolan bir paylaşılan komut grubu yerleştirmeyi deneyin. Yeni bir grup tanımlanmış olması gerekiyorsa, ilgili komut grubu yakın varolan bir paylaşılan menüsünde yeni bir üst düzey menü oluşturmadan önce yerleştirmeyi deneyin. Bu komut karmaşıklık tutarlı komut yerleşimi IDE'de sağlarken azaltır.  
  
 Paylaşılan **biçimi** genellikle designer stili belge pencereleri bağlamında gösterilen menüsünde aşağıdaki görüntüde gösterilen:  
  
 ![Visual Studio biçim menüsü çağrılar ile](../../extensibility/ux-guidelines/media/0501-d_formatmenu.png "0501 d_FormatMenu")  
  
 **Visual Studio menü grupları**  
  
### <a name="reducing-and-reusing-commands"></a>Azaltma ve komutları yeniden kullanma  
 Komutları genellikle bağlamda, kullanıcı belirli bir zamanda görür komutları sayısını azaltmak için temel gösterilmektedir. Ancak, varolan paylaşılan menüleri yeniden kullanmamalısınız ve bağlamda değişiklikler arasında komut yapısını göreceli olarak kaldığından emin olmak için komut grupları kararlı.  
  
 Paylaşılan komutları yeniden kullanmak ve ilgili paylaşılan komutları yakın yeni komutları yerleştirme IDE karmaşıklığını azaltır ve daha kullanıcı dostu bir deneyim oluşturur.  
  
## <a name="naming-commands"></a>Adlandırma komutları  
  
### <a name="naming-conventions"></a>Adlandırma kuralları  
 Kullanıcıları bulmak ve komutlarını, komut satırı kullanılarak veya bir klavye kısayolu bağlama yürütme böylece tutarlı komutu adlandırma kritik öneme sahiptir. Komut adlarının ayrıca bir araç çubuğunda veya basamaklı veya bağlam menüsünde görüntülendiğinde komut hizmet amaca anlamasına yardımcı olur.  
  
#### <a name="when-naming-commands"></a>Ne zaman adlandırma komutlar:  
  
-   Böylece kolayca yerelleştirilebilir metin oluşturun. Metin yerelleştirme hakkında daha fazla bilgi için bkz: [World hazırlık Visual Studio için](http://msdn.microsoft.com/en-us/1cc35051-8126-441f-bea9-059245a47b1d).  
  
-   Kısa olmalıdır. Komutlar, en fazla üç sözcük kullanmanız gerekir.  
  
-   İlk harfler büyük harf kullanın: her sözcüğün ilk harfi büyük harfe. Visual Studio'da biçimlendirme metin hakkında daha fazla bilgi için bkz: [metin stili](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).  
  
-   Komut yerleştirileceği dikkate alın. Bir üst düzey menü veya bir çıkma mi? Örneğin, ne zaman gruplandırma hizalama çıkma, üst düzey komutu komutlarda "Hizala" ve çıkma komutları olmalıdır "Sol" "Sağ", "Center," "blokla" olabilir ve benzeri. "Sola Hizala" veya "Sağa Hizala." çıkma komutlar adı olarak yedekli  
  
     ![Visual Studio biçim menüsü](../../extensibility/ux-guidelines/media/0502-a_formatmenu.png "0502 a_FormatMenu")  
  
### <a name="using-icons-with-commands"></a>Simgeler komutları ile kullanma  
 Komutları ile eşleştirme simgesinin kullanımda sparing olabilir. Bu komut tanımlamak için kullanıcının özelliği bir komutla benzersiz bir görüntü ilişkilendirme hastens rağmen görüntü aşırı kullanımı ile visual dağınıklığı ve Etkisizliği oluşur. Aşağıdaki kuralları, bir komut simgesi oluşturmak karar verirken yardımcı olur.  
  
#### <a name="use-an-icon-with-a-command-only-if"></a>Bir simge ile komutu yalnızca IF kullanın:  
  
-   Aynı komutu bir Microsoft Office uygulamaları gibi başka bir belirgin Microsoft ürünü üzerinde ilişkili bir simgesi vardır.  
  
-   Komut varsayılan araç çubuğunda yer alır.  
  
-   Kullanıcılar için bir araç kullanarak eklemek büyük olasılıkla bir özel komut komuttur **"Özelleştir..."** iletişim.  
  
## <a name="access-and-shortcut-keys"></a>Erişim ve kısayol tuşları  
  
### <a name="overview"></a>Genel Bakış  
 Klavye atamalarının iki tür vardır:  
  
-   **Erişim tuşları** (Hızlandırıcıları olarak da bilinir) iletişim UI kumanda ve her etiket için menüleri aracılığıyla klavye erişim izni. Erişim tuşları çoğunlukla erişilebilirlik amaçlıdır tüm menüleri ve çoğu iletişim kutusu denetimleri atanmış amaçlanmamıştır ezberlediyseniz için yalnızca geçerli pencereyi etkileyen ve yerelleştirilmiştir.  
  
-   **Kısayol tuşları** çoğunlukla denetimi (Ctrl) ve işlev (Fn) anahtar dizilerini kullanın. Bunlar daha gelişmiş kullanıcılar ve yardımcı olmak için üretkenliği açısından tasarlanmış. Bunlar yalnızca en sık kullanılan komutlar için atanan ve ana menüye atlayarak sırasında hızlı erişim izni. Kısayol tuşları ezberlediyseniz amaçlanmıştır ve için neden Profil şeması ile tutarlı atanması gerekir. Kısayol tuş düzenleri profili profil farklılık gösterebilir. Bir kullanıcı kısayol tuşları aracılığıyla özelleştirebilir **Araçlar > Seçenekler > klavye**.  
  
### <a name="assigning-access-keys"></a>Erişim tuşları atama  
 Erişim tuşları Alt artı alfasayısal anahtarları oluşur. Özel durum olmadan her bir menü öğesi için bir erişim anahtarı atayın. Windows ve erişim tuşları atama için ortak kuralları izleyin. Örneğin, erişim anahtarı **Dosya > Yeni** her zaman olmalıdır **Alt, F, N**.  
  
 'İ' (büyük veya küçük harf) veya küçük 'l' gibi tek piksel genişliği harf kullanma ve Bu ayrım yapmak zor olduğu gibi karakterler (g, j, p, soru ve y) harfin alt ile kullanmaktan kaçının.  
  
 Mümkün olduğunda yinelenen anahtarlar kullanmaktan kaçının. Çoğaltma kaçınılmaz olduğu durumlarda, menü sistemi anahtarını kullanan tüm komutları dönüşüm tarafından çakışmaları işler. Örneğin, "Number" komutunu "N" erişim tuşu çoğaltan dosya menüsü altında bir kuramsal için **Alt, F, N** yeni bir dosya oluşturur ve **Alt, F, N, N** "Number" komutu gerçekleştirmelisiniz.  
  
### <a name="assigning-shortcut-keys"></a>Kısayol tuşları atama  
 Her komut için gerekli değildir ve sistem (ve kullanıcı bellek) aşırı kullanılmasına olursa vergi olduğundan yeni kısayol tuşları, atamaktan kaçının. Visual Studio kullanıcıların yalnızca küçük bir alt kümesini tümleşik kısayolları kullanmak veri gelen Müşteri Deneyimi Geliştirme Programı'nı (CEIP) gösterir.  
  
 Kısayollar tanımlarken, bu kurallar izleyin:  
  
-   **Denetim (Ctrl) ve işlev (Fn) anahtar dizilerini kullanın.**  
  
-   **Sık kullanılan kısayolları korur.** En popüler kısayolları korur.  
  
-   **Düzenleyici kısayollarının yazmak kolay hale getirir.** Geliştiriciler kod yazılırken çoğu gereksinim komutları türü kolay kısayolları bağlar. Örneğin, **Edit.InvokeSmartTag** Ctrl gibi hızlı kısayol tuşu sahip olması +/ ve değil Alt + SHIFT + F10.  
  
-   **Tutarlı bir şekilde konulu kısayolları çalışmalar yapılmaktadır.**  
  
-   **Kullanımlar için hangi değiştirici tuşları belirlemek için Windows yönergeleri izleyin.** Belgenin tamamına uygulamak komutları gibi büyük ölçekli etkileri komutlar için CTRL tuş birleşimlerini kullanın. Shift tuş birleşimleri genişletmek veya standart kısayol tuşunu eylemlerini tamamlamak için komutları kullanın. Ctrl + Alt birleşimleri kullanmayın.  
  
-   **Yabancı kısayolları kaldırın.** Eski bir özellik varsa, bir erişim anahtarı aynı komutu hızlı erişim sağlıyorsa, aşırı infrequency (daha az daha 10 kez verilerden CEIP) veya Orta infrequency (daha az 100 kez daha CEIP verileri) ile kullanılan kısayolları kaldırmayı düşünün. Örneğin: Alt, H, C Yardım/içeriğini açılır.  
  
 Kısayol kullanılabilirliğini denetlemek için basit bir yol değil. Bir kısayol eklemek istiyorsanız, aşağıdaki adımları izleyin:  
  
1.  Listesini kontrol edin [Visual Studio 2013 kısayolları](http://visualstudioshortcuts.com/2013/) sizin ile gruplandırmak için benzer komutları olup olmadığını belirlemek için.  
  
2.  Git **Araçlar > Seçenekler > ortamı > klavye** ve kısayolu test. "Aşağıdaki ek klavye kısayol düzenini Uygula." her klavye kısayol düzeni altında listelenen denetleyin Bu benzersiz kısayolları paylaşır gibi genel, C#, VB ve C++ profilleri denetleyin. Kısayolu bu yerlerin hiçbirinde eşlenmemiş varsa kullanılabilir.