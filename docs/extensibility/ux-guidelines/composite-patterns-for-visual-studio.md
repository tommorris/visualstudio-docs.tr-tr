---
title: Visual Studio için bileşik desenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: e48ecfb2-f4b5-4d3a-b4a2-7a4d62fa4ec0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6515b5aefc0536ea92f09a92b1a17050b820008d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31148957"
---
# <a name="composite-patterns-for-visual-studio"></a>Visual Studio için bileşik desenleri
Bileşik desenleri farklı yapılandırmayı etkileşim ve tasarım öğeleri birleştirin. Visual Studio tutarlılık açısından en önemli bileşik düzenleri bazıları şunlardır:  
  
-   [Veri Görselleştirme](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_DataVisualization)  
  
-   [Nesne üzerinde kullanıcı Arabirimi ve gözatma](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_OnObjectUI)  
  
-   [Seçim modelleri](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_SelectionModels)  
  
-   [Kalıcılığı ve ayarları kaydediliyor](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_PersistenceAndSavingSettings)  
  
-   [Dokunmatik giriş](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_TouchInput)  
  
##  <a name="BKMK_DataVisualization"></a> Veri Görselleştirme  
  
### <a name="overview"></a>Genel Bakış  
 Grafikler, toplama ve işlerinize geliştirmek için verileri görselleştirmek için görsel bir yoludur. Bunlar çok miktarda veri ancak bkz: ne dikkat hak ve hangi eylemin gerekebilecek küçük anlamına gelir ile karşılaştığı kullanıcıların yardımcı olur.  
  
 Aşağıdaki koşullardan herhangi biri doğruysa, kullanıcı bir grafik yararlı olacaktır:  
  
-   Grafik çalışabilmek için görevleri tanımlamak kullanıcılara yardımcı olur?  
  
-   Grafik, olası değişiklikleri sonuçlarını tahmin etmek kullanıcıların olanak sağlar?  
  
-   Grafik eğilimleri bulmak ve düzenleri tanımlamak kullanıcılara yardımcı olur?  
  
-   Grafik daha iyi kararlar almak kullanıcılara izin verecek misiniz?  
  
-   Grafik verilen içerikte kullanıcınız belirli bir soruya yanıt yardımcı olur?  
  
#### <a name="general-rules-for-charts"></a>Grafik için genel kurallar  
  
-   Açıkça etiket verileri. Açıklama olmadan çizimler olan yalnızca resim asıl.  
  
-   Eksen eğriltme oranları önlemek için sıfırdan başlatın. Veri noktaları arasındaki ilişkileri anlamak için önemli görsel ipuçları satır uzunluğu ve çubuğu boyutu var.  
  
-   Grafikler, değil infographics oluşturun. Infographics veri Artistik gösterimlerini, ve bunların birincil hedef visual storytelling. Grafikler olabilir ve gereken görsel olarak çekici, ancak kendini ifade etmesini veri sağlar.  
  
-   Skeumorphism, resimsel çubuk grafikler, karşıtlık hashmarks ve diğer bilgi grafiği rötuşları kaçının.  
  
-   3B efektler dekoratif bir öğe olarak kullanmayın. Bunları yalnızca kullanırsanız, kullanıcının özelliğine bilgileri kavrama gerçekten tam sayı.  
  
-   Bu grafik türü birden fazla iki renkten okuyun ve doğru şekilde yorumlamak zor hale getirebilir gibi birden çok satır ve dolgular kullanmaktan kaçının.  
  
-   Bir kavram anlama veya verilerle etkileşim tek yolu olarak bir grafik (veya tüm çizim) kullanmayın. Bu, görme engelli kullanıcılara zorluklarla kullanıcılar için gösterir.  
  
-   Grafikler, bir sayfadaki gereksiz veya dekoratif öğeler olarak kullanmayın. Diğer bir deyişle, bir grafik herhangi bir değer veya Yardım kullanıcının bir sorunu çözmek değil eklerseniz, kullanmayın.  
  
### <a name="chart-types"></a>Grafik türleri  
 Visual Studio'da kullanılan grafik türleri şunlardır çubuk grafikler, çizgi grafiklerde, bir halka grafik ya da "halka grafiği," zaman çizelgelerini, bilinen değiştirilmiş bir pasta grafik dağılım ("grafikleri küme" da denir) çizimleri ve Gantt grafikleri. Grafik türlerinin farklı türde bilgi iletişim kurmak için yararlıdır.  
  
### <a name="other-charting-considerations"></a>Diğer grafik konuları  
  
#### <a name="color"></a>Renk  
 Visual Studio'da kullanılmak üzere tanımlanmış renkleri grafik, belirli bir palet yoktur. Palet renk görme engeli ana türleri için erişilebilir olduğundan ve renklerin renk çok dar dilimler kullanıldığında bile Ayrıştırılan. Bu renkleri herhangi bir bileşimini, kullanıcı Arabiriminde herhangi bir türde grafiği veya grafiği için kullanabilirsiniz. Bu kadar sayıda tek tek renkler gerekmiyorsa tüm yedi renklerini kullan gerekmez. Bu renkleri metin ya da bu renkleri üstünde karakterlerin yerleştirmeyin için tüm ön plan öğeleri ile kullanılmak üzere tasarlanmamıştır. Bu tonlar sabit kodlanmış ve gerekir kullanıcı özelleştirme altında maruz **Araçlar > Seçenekler** (bkz [son kullanıcılar için renk gösterme](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ExposingColorsForEndUsers)).  
  
|Renk örneği|Onaltılık|RGB|  
|------------|---------|---------|  
|![Renk örneği 71B252](../../extensibility/ux-guidelines/media/0711_71b252.png "0711_71B252")|#71B252|113,178,82|  
|![Renk örneği BF3F00](../../extensibility/ux-guidelines/media/0711_bf3f00.png "0711_BF3F00")|#BF3F00|191,63,0|  
|![Renk örneği FCB714](../../extensibility/ux-guidelines/media/0711_fcb714.png "0711_FCB714")|#FCB714|252,183,20|  
|![Renk örneği 903F8B](../../extensibility/ux-guidelines/media/0711_903f8b.png "0711_903F8B")|#903F8B|144,63,139|  
|![Renk örneği 117AD1](../../extensibility/ux-guidelines/media/0711_117ad1.png "0711_117AD1")|#117AD1|17,122,209|  
|![Renk örneği 79D7F2](../../extensibility/ux-guidelines/media/0711_79d7f2.png "0711_79D7F2")|#79D7F2|121,215,242|  
|![Renk örneği B5B5B5](../../extensibility/ux-guidelines/media/0711_b5b5b5.png "0711_B5B5B5")|#B5B5B5|181,181,181|  
  
##  <a name="BKMK_OnObjectUI"></a> Nesne üzerinde kullanıcı Arabirimi ve gözatma  
 Bu bölümde, kod gözlem görünümü olarak da bilinen, nesne üzerindeki UI Visual Studio için benzersiz bir tür gözatma için bağlamı sağlar.  
  
### <a name="overview"></a>Genel Bakış  
  
-   Nesne üzerinde UI kullanıcının daha fazla bilgi veya etkileşim kendi ana görevden detracting olmadan vermesi gerekir.  
  
-   Visual Studio'da nesne üzerindeki UI ana deseni "bilgileri dikkat noktasında." olarak bilinir  
  
-   Visual Studio'da nesne üzerinde UI ya da satır içi veya kayan ve dayanıklı veya geçici değil.  
  
    -   Kod gözlem Visual Studio'da nesne üzerindeki UI türü satır içi ve dayanıklı görünümüdür.  
  
    -   Kayan ve geçici CodeLens, Visual Studio'da nesne üzerindeki UI türü  
  
 Bir kod parçasını nasıl çalıştığını anlamak veya bu kodu ayrıntılarını bulma genellikle bağlamı değiştirmek ve diğer içerik veya başka bir gitmek bir geliştirici gerektirir penceresi. Kendi ana penceresi bırakırsanız kullanıcılar kendi özgün görev odaklanmak kaybedebilir olduğundan bu bağlamda kaydırmalar kesintiye uğratan, olabilir. Ayrıca, özgün bağlamı geri özellikle windows geçiş diğer kullanıcı Arabirimi tarafından görünmeyebilir kendi özgün kod neden olursa zor olabilir alınıyor.  
  
 Nesne üzerinde UI "bilgileri dikkat noktasında." olarak adlandırılan bir deseni takip eder Bu iletiler, açılır pencereleri ve iletişim kutuları kullanıcılara açıklama veya etkileşim ana görevini odaklanmak kaybetmeden ekler, ilgili ek bilgi verin. Bir kullanıcı kendi işaretçi geldiğinde bildirim alanında bir simge, yanlış yazılmış bir sözcük ve Visual Studio 2013'te tanıtılan gözlem görünüm altında kırmızı dalgalı üzerinden görüntülenen açılır pencereleri nesne üzerindeki UI örneklerindendir.  
  
### <a name="decision-points"></a>Karar noktaları  
 Visual Studio içinde dikkat noktasında bilgilerinin bu deseni kullanılacak birkaç yolu vardır. Genel deneyimi sağ mekanizmasını seçme ve tutarlı ve öngörülebilir bir şekilde uygulama gereklidir. Aksi halde, kullanıcıların içeriği odağı detracts kafa karıştırıcı veya tutarlı bir deneyim sunulabilir.  
  
#### <a name="relationships-between-master-and-detail-content"></a>Ana ve ayrıntı içerik arasındaki ilişkileri  
 Bir ilişki görüntülemek için bilgi dikkat noktasında kullanılan arasında içerik ("ana" içerik) odaklanmıştır ve ek kullanıcıdır ilgili içerik ("ayrıntı" içeriği). Bu modelinde ayrıntı içeriği, kullanıcı ile çalışma ve yakın ana içerik görüntülenebilir içeriğe açıkça ilişkilidir. Ek bilgiler veya ana içerik yayma olmadan özetlenen olamaz bilgilerini araç penceresi gibi başka bir deseni izlemelidir.  
  
-   **Her zaman** ana içerik yakın ayrıntı içeriği görüntüle.  
  
-   **Her zaman** ayrıntı içeriği hala bir kullanıcının ana içerik odaklanmış kalmasına olanak tanıdığından emin olun. Genellikle, bunu başarmak için en iyi ana içerik mümkün olduğunca yakın ayrıntı içeriği olarak işlemek için yoludur. Bu ana içerik yanındaki açılır pencerede ayrıntı içeriğini işlemek ya da ana içerik altında ayrıntı içerik satır içi işleme yapılabilir.  
  
-   **Hiçbir zaman** ana içerik çıktığınızda kullanıcı alır dikkat noktasında bilgileri kullanın. Kullanıcıların ayrıntı içeriği ayrı olarak görüntülemek gerekiyorsa, bunu yapmak kullanıcının sağlayan açık bir eylem kullanıma sunar.  
  
#### <a name="design-details"></a>Tasarım ayrıntıları  
 Nesne üzerinde UI doğru seçim olduğunu belirledikten sonra dört ana tasarım konuları vardır:  
  
1.  **Kalıcılık:** içeriği kalıcı veya geçici olması bekleniyor?   
    Kullanıcıların bilgilere başvurun veya etkileşimde görünsün etmek istiyor musunuz? Veya kullanıcılar bilgilerine Hızlı bakış ve ana görevini ile devam etmek istiyor musunuz?  
  
2.  **İçerik türü:** içeriği bilgi, işlem yapılabilir veya gezinme olacak?   
    Kullanıcı ana içerik hakkında ek ayrıntılar gerekiyor mu? Kullanıcı ana içeriği etkiler bir görevi tamamlamak gerekiyor mu? Ya da kullanıcı başka bir kaynağa yönlendirilmesi gerekiyor mu?  
  
3.  **Gösterge türü:** bir ortam göstergesi için anlamlı mı?   
    Bilgilerin kullanılabilir kullanışlı şekilde özetlenmiş ve ana içerik yayma olmadan görüntülenen?  
  
4.  **Hareketleri:** hangi hareketleri çağırma ve kullanıcı arabirimini kapatmak için kullanılacak?   
    Nasıl kullanıcı ayrıntı içeriğin getirin ve hemen gönder? Geçici ve kalıcı durumları arasında geçiş yapmak için sabitleme gibi hareket ekleme değer var?  
  
 Bu dört karar noktaları her bir nesne üzerindeki UI başlıca bileşenleri üzerinde etkisi olacaktır.  
  
### <a name="on-object-ui-components"></a>Nesne üzerinde UI bileşenleri  
  
1.  Kapsayıcı (içerik sunan) türü  
  
    -   Kayan  
  
    -   Satır içi  
  
2.  İçerik türü  
  
    -   Bilgi amaçlı: veri, statik veya dinamik olabilir  
  
    -   İşlem yapılabilir: ana içerik değiştirme komutları  
  
    -   Gezinme: başka bir pencere veya MSDN gibi uygulama için kullanıcı götüren bağlantılar  
  
3.  Hareketleri  
  
    -   Çağırma  
  
    -   İşten çıkarma  
  
    -   Sabitleme  
  
    -   Diğer etkileşimler  
  
4.  Kalıcılığı ve yürütme modeli  
  
    -   Geçici  
  
    -   dayanıklı  
  
    -   Otomatik  
  
    -   İsteğe bağlı  
  
5.  Ortam göstergeleri (isteğe bağlı)  
  
    -   Dalgalı alt çizgi  
  
    -   Akıllı etiket simgesi  
  
    -   Diğer ortam göstergeleri  
  
#### <a name="container-content-presenter-type"></a>Kapsayıcı (içerik sunan) türü  
 İçerik dikkat noktasında sunmak kullanılabilecek iki ana seçenek vardır:  
  
1.  **Satır içi:** varolan içeriğin değiştirerek Visual Studio 2013 Kod düzenleyicisinde, sunulan gözlem görünümü gibi bir satır içi sunan yeni içerik için alanı sağlar.  
  
    -   **Tercih** kullanıcılar önemli miktarda başvurma veya içeriği ile etkileşim zaman harcamanız istediğiniz bekliyorsanız, satır içi sunucuları sunar.  
  
    -   **Kaçının** kullanıcılar bekliyorsanız, satır içi sunucuları sunmak, sonra en az kesintiyi ile ana görevini devam bilgilerine bakışta istediğiniz.  
  
2.  **Kayan:** kayan sunucu seçilen içeriği gibi mümkün olduğunca yakın yerleştirilmiş ancak mevcut içeriğinin düzenini değiştirmez. Üzerinden bir kayan İçerik paneli görüntüleme gibi çeşitli stratejileri çalıştırılacağı seçili simgesine kullanılabilir boşluk en yakın.  
  
    -   **Tercih** kullanıcılar bekliyorsanız sunucuları kayan istediğiniz sunmak, sonra en az kesintiyi ile ana görevini devam bilgilerine genel bakış.  
  
    -   **Kaçının** kullanıcılar bekliyorsanız sunucuları kayan istediğiniz önemli miktarda başvurma veya içeriği ile etkileşim zaman harcamanız, mevcut.  
  
#### <a name="content-type"></a>İçerik türü  
 Üç ana içinde herhangi bir nesne üzerinde UI kapsayıcısına görüntülenen içerik türleri vardır. Bu tür bilgiler herhangi bir bileşimini gösterilebilir. Üç tür şunlardır:  
  
1.  **Bilgi amaçlı:** çoğu üzerinde nesne UI kapsayıcıları bazı bilgilendirme içerik türünü görüntüler. İçerik ortamının mevcut durumu hakkındaki bilgileri gösterebilir veya ortam bir olası gelecekteki durumu hakkındaki bilgileri gösterebilir. Örneğin, bir, varolan kod yeniden düzenleme gibi belirli bir komutun etkisini göstermek için kullanılabilir.  
  
    -   **Her zaman** görüntü bilgileri kurallı gösterimini kullanın. Örneğin, kod kod, sözdizimi vurgulama, tamamlandı gibi görünmelidir ve yazı tipinde ve kullanıcı diğer ortam ayarları dikkate.  
  
    -   **Her zaman** aynı bilgileri ana içerik olarak verilirse sağlayabileceğinizden bilgilendirici içerik üzerinde herhangi bir eylem destekleme göz önünde bulundurun. Örneğin, bir nesne üzerinde UI kapsayıcısı içinde var olan kod sunan, kesinlikle göz atın ve bu kodu değiştirme yeteneğini destekleme düşünün.  
  
    -   **Her zaman** bilgilendirme içeriği sunan bir olası gelecekteki durumu temsil ediyorsa farklı arka plan rengi kullanmayı düşünün.  
  
2.  İşlem yapılabilir: Bazı nesne üzerinde UI kapsayıcılar yeniden düzenleme işlemi gerçekleştirme gibi ana içerik üzerinde bazı eylemleri gerçekleştirmenize olanak sağlar.  
  
    -   **Her zaman** getirin tıklatılabilir komutları ayrı ayrı bilgi içeriği.  
  
    -   **Her zaman** etkinleştirin ve uygun olduğunda eylemleri devre dışı.  
  
    -   **Her zaman** iletişim kutuları içindeki komutları temsil etmek için standart yönergelere bakın.  
  
    -   **Her zaman** mutlak bir nesne üzerinde UI kapsayıcıya sunulan eylemlerin sayısını en düşük tutun. Nesne üzerindeki kullanıcı Arabirimi ile etkileşim basit, hızlı bir deneyim olmalıdır. Kullanıcı nesnesi üzerinde UI kapsayıcı kendisini yönetme enerji harcaması olmalıdır.  
  
    -   **Her zaman** nasıl ve ne zaman bir nesne üzerinde UI kapsayıcısı kapalı kapatıldığında veya göz önünde bulundurun. Bu eylem çalıştırıldığında en iyi uygulama, ana ve ayrıntı içerik arasındaki iletişim sonucuna herhangi bir eylem ayrıca nesne üzerinde UI kapsayıcısı kapatmanız gerekir.  
  
3.  **Gezinme:** bazı üzerinde UI kapsayıcıları başka bir pencere veya bir MSDN makalesine kullanıcının web tarayıcısında açarak gibi uygulama, kullanıcının götüren bağlantılar içeren nesne.  
  
    -   **Her zaman** böylece kullanıcılar diğer içerikler gittiğinizde tarafından sürprizle değil "Açık" herhangi bir gezinme bağlantıyı önüne ekleyin.  
  
    -   **Her zaman** gezinme bağlantıları tıklatılabilir bağlantılarından ayırın.  
  
#### <a name="ambient-indicators-optional"></a>Ortam göstergeleri (isteğe bağlı)  
 Ortam göstergeleri hafif, kod geri kalanından karşıt renkte sunulan metin dahil veya açıktır, dalgalı alt çizgiler ve akıllı etiket simgeler gibi tickler semboller de dahil olmak üzere olabilir. Ortam göstergeleri ilgili ek bilgiler kullanılabilirliğini iletişim kurar. İdeal olarak, hatta onlarla etkileşime girmesini gerektirmeden yararlı bilgiler sağlar.  
  
-   **Her zaman** bırakmaz gelen rahatsız veya kullanıcı doldurmaya böylece bir ortam gösterge getirin. Bir ortam gösterge biçimde konumlandırmak mümkün değildir, başka bir çözüm düşünün.  
  
-   **Her zaman** ortam göstergesi için ilgili içeriğe mümkün olduğunca yakın getirin.  
  
-   **Her zaman** kullanılabilir kolaylaştırır bilgileri özetler bir gösterge oluşturmayı deneyin. Kullanılabilir veri öğesi sayısı, (örneğin, "3 başvurular" Basit "Başvurular" yerine) sayısı sağlamayı düşünün veya özetlemek için başka bir şekilde düşünün.  
  
    -   Burada bir gösterge verileri her zaman hesaplanan görüntülenir ve durumlarda değerler hesaplanan gibi aşamalı geribildirim sağlama hemen göz önünde bulundurun. Örneğin, benzer bir Windows Phone e-posta Canlı kutucuğu okunmamış e-postaları artar sayı olarak yeniler biçimde kullanılabilir verilere güncelleştirmelerini yansıtma değişiklikleri animasyonu göz önünde bulundurun.  
  
-   **Hiçbir zaman** bir kullanıcı belirli bir içerik için makul biçimde ele çok daha fazla göstergeleri ekleyin. Ortam göstergeleri kullanıcı etkileşimi gerektirmeden kullanışlı olması gerekir. Taşma ve diğer yönetim denetimleri görünüme getirilmesi gerekiyorsa göstergeleri kendi çevre kaybedersiniz.  
  
#### <a name="gestures"></a>Hareketleri  
 Ana içerik odaklanmak korumak kullanıcının önemli nokta, açmak ve ek ayrıntı içerik kapatmak için sağ hareketleri destekleyerek ' dir.  
  
-   **Her zaman** ek içeriği açmak için bazı açık hareketi gerçekleştirmek kullanıcının gerektirir. Ortak açık hareketleri şunları içerir:  
  
    -   **Vurgulu:** araç ipuçları veya etkileşimli olmayan bilgilendirme içeriği  
  
    -   **Açık komutu:** satır içi sunum  
  
    -   **Ortam göstergesi çift:** CodeLens açılır penceresi  
  
-   **Her zaman** her kullanıcı Esc tuşuna bastığında ayrıntı içerik yok sayın.  
  
-   **Her zaman** nesnesi üzerinde UI bağlamında göz önünde bulundurun. Kapsayıcı içinde etkileşim için izin içerik sunucuları için ek bilgiler gidildiğinde, büyük olasılıkla kullanıcının iş akışını kesintiye uğratan olduğu gösterilip gösterilmeyeceğini dikkatlice düşünün.  
  
-   **Hiçbir zaman** düzenlenebilir gibi görünüyor veya kullanıcı etkileşimi başvurulmasını gidildiğinde içeriği görüntüle. İmleci, üretilen içeriği asıl artık olduğunda hemen kapatmak için bir araç ipucu için standart davranış olduğu gibi imleci ayrıntı içerik taşımaya çalışırsanız bu davranış kullanıcıları rahatsız.  
  
##  <a name="BKMK_SelectionModels"></a> Seçim modelleri  
  
### <a name="overview"></a>Genel Bakış  
 Bir seçim modeli belirtmek ve bir veya daha fazla nesneleri kullanıcı arabiriminden ilgi işlemleri onaylamak için kullanılan mekanizmadır. Bu konuda seçimi etkileşim desenleri Visual Studio belge düzenleyiciler içinde ele alınmıştır: metin düzenleyicileri, tasarım yüzeyleriyle ve modelleme yüzeyleri.  
  
 Kullanıcıların ne üzerinde çalıştıkları Visual Studio'ya belirten bir yol olmalıdır ve Visual Studio ne üzerinde çalışıyor hakkında kullanıcılara geri bildirim beklendiği yanıtlaması gerekir. Farklılıkları veya kullanıcı ve kullanıcı arabirimi arasında miscommunication sahip olabilen bir eylem değil haberiniz bile kullanıcı sonuçlanabilir istenmeyen sonuçları. Genellikle, bir şeyin eksik veya değişti kullanıcının gördüğü kadar hata gözden kaçan gider. Seçim modelleri olan bu nedenle kullanıcı arabirimi tasarımı en önemli parçaları biri. Visual Studio seçimi modellerinde Windows ile tutarlı olmasına rağmen hafif Çeşitlemeler vardır.  
  
 Visual Studio'da, Windows, olduğu gibi seçim modelleri etkileşim gerçekleştiği bağlamı bağlı olarak farklılık gösterir. Seçimleri nesneleri dört tür oluşabilir:  
  
-   Metin  
  
-   Grafik nesneleri  
  
-   Listeler ve ağaçları  
  
-   Kılavuzları  
  
 Bu nesneler içinde seçimleri üç tür vardır:  
  
-   Bitişik  
  
-   Ayrık  
  
-   Bölge  
  
#### <a name="scope"></a>Kapsam  
 Seçim en önemli bileşeni, kullanıcının hangi penceresinde (etkinleştirme) çalışma ve odağı bulunduğu (seçim) olduğu bildiği sağlamaktır. Visual Studio Windows penceresi yönetim işlevselliği genişletir, ancak etkinleştirme düzeni aynı: bir pencere ile etkileşim odak pencereyi getirir. Visual Studio etkinleştirme için iki göstergeleri vardır: biri belge windows için ve biri aracı windows için.  
  
 Belge pencereleri için etkin pencereyi öne çıkacak ve arka plan rengi değiştirerek bir belge penceresi sekmesine tarafından belirtilir:  
  
 ![Visual Studio'da etkin sekme seçimi](../../extensibility/ux-guidelines/media/0713-01_activetab.png "0713 01_ActiveTab")  
  
 **Etkin sekme seçimi**  
  
 Aracı windows için araç penceresinin başlık çubuğunu alanı rengini değişikliği etkin pencereyi gösterilir:  
  
 ![Visual Studio'da etkin araç penceresi seçimi](../../extensibility/ux-guidelines/media/0713-02_activetoolwindow.png "0713 02_ActiveToolWindow")  
  
 **Bir düğümün birincil seçimi gösteren etkin araç penceresi**  
  
 ![Visual Studio'da etkin araç penceresi seçimi](../../extensibility/ux-guidelines/media/0713-03_inactivetoolwindow.png "0713 03_InactiveToolWindow")  
  
 **Etkin olmayan araç penceresi, düğümün görünmeyen seçimi gösterme**  
  
 Bir pencere etkin olduğunda, kendi odak yönergeleri Bu bölümde özetlendiği seçimi modelleri göre belirtilir.  
  
#### <a name="context"></a>Bağlam  
 Visual Studio, kullanıcı nerede çalışma izleme tutma bağlamı, güçlü bir kavramı korumak için tasarlanmıştır. Bir aracı ya da belge penceresi olup yalnızca bir pencere etkindir. Ancak, en üstteki belge penceresi, her zaman görünmeyen bir seçim korur. Odağı araç penceresinde olabilir, ancak son etkin belge penceresine bile etkin olmayan bir durumda bir seçim görüntüler. Bu, kullanıcının bağlamında bunlar, böylece dönün ve sorunsuz bir şekilde araç pencereleri ve belge pencereleri arasında kaydırma Visual Studio durumlarına koruduğunu gösteren düzenlemekte olduğunuz belgeyi korumak için gerçekleştirilir.  
  
### <a name="text-selection"></a>Metin seçimi  
 Gibi yerleşik metin düzenleyicide, kesinlikle metinsel visual Studio düzenleyicilerini kullanın aynı metin seçimi modeli ve görünüm açıklanan [işaretçileri ve fare](https://msdn.microsoft.com/en-us/library/dn742466.aspx) Windows kullanıcı deneyimi etkileşim kuralları sayfası MSDN. Giriş odağını metin düzenleyicisinde ekleme noktasını adlı dikey bir çubukla belirtilir. Tek bir piksel kalın ve arkasında görünür tersi olarak renkli ekleme noktasıdır. Tarafından belirlenen oranı göre yanıp **imleç blink hızı** ayarı **hızı** sekmesinde **klavye** Denetim Masası'ndaki uygulaması.  
  
#### <a name="contiguous-and-disjoint-selection"></a>Sürekli ve ayrık seçimi  
 Metin Düzenleyici içinde yalnızca bitişik seçimdir. Seçimleri izin verilmez, ancak grafik nesnesi düzenleyicilerde ele alınması gereken metin ayrık. İmleci, kullanıcının fare işaretçisini metin alanı olduğunda, bir ı ışını değiştirir. Tek bir tıklamayla ekleme noktasını tıklatın konumda metin düzenleyicisinde yerleştirir. Fare düğmesini basılı seçim Vurgusu başlatır ve fare düğmesini bırakmadan seçim Vurgusu sona erer.  
  
#### <a name="region-selection-box-selection"></a>Bölge Seçimi (kutusu seçimi)  
 Visual Studio bölgesi seçimlerin Metin Düzenleyicisi'nde destekler ve bu kutusu seçimi çağrılır. Kutusu seçimi normal metin akış izlemez metnin bir bölge seçin olanak tanır. Standart metin seçimle gibi seçimi bitişik olmalıdır. Kutusu seçimi fareyle sürükleme sırasında Alt tuşunu basılı tutarak başlatılır. Kutusu seçimi, Alt ve üst karakter tuşları aşağı seçimi bölge belirtmek için ok tuşlarını kullanırken tutarak da başlatılabilir. Kutusu seçimi normal seçim Vurgusu kullanır ve seçim alanı sonunda yanıp sönen ekleme noktası imleç gösterir.  
  
 ![Bölgesel &#40;kutusunu&#41; Visual Studio'da seçimi](../../extensibility/ux-guidelines/media/0713-04_boxselection.png "0713 04_BoxSelection")  
  
 **Visual Studio'da bölge (kutusu) Seçimi**  
  
#### <a name="text-selection-appearance"></a>Metin seçimi görünümü  
 Etkin ve etkin olmayan seçim Düzenleyicisi'nde için kullanılan renkleri özelleştirilebilir. Düzenleyici görsel görünümünü özelleştirmek için bir kullanıcı gidebilirsiniz **Araçlar > Seçenekler**ve kısmına bakın **ortam > yazı tiplerini ve renkleri > Metin Düzenleyicisi**.  
  
### <a name="graphical-selection"></a>Grafik seçimi  
  
#### <a name="interaction"></a>Etkileşim  
 Grafik Nesne Seçimi karmaşık olabilir ve bir dizi etkene bağlıdır:  
  
-   **Düzenleyicinin birincil seçimi modeli.** Grafik nesneleri içeren düzenleyicileri, metin veya kılavuzları düzenlemek için de kullanılabilir. Örneğin, düzenleyici de Visual Studio XAML Tasarımcısı gibi grafik nesneleri yerleşimini destekler metin tabanlı bir düzenleyici olabilir. Birden çok nesne türlerini destekleyen kullanıcı nesneleri farklı türdeki oluşan grupları nasıl seçtiği etkileyebilir.  
  
-   **Birincil ve ikincil seçimi durumları için destek.** Bir düzenleyici nesneleri çubuğuyla içinde düzenlenebilir böylece durumları birbirleri ile birlikte, vb. yeniden boyutlandırılabilir hizalı birincil ve ikincil seçimi sağlayabilirsiniz.  
  
-   **Yerinde düzenleme desteği.** Düzenleyiciler düzenlenmesi grafik nesnelerine içeriğini de izin verebilirsiniz. Örneğin, bir dikdörtgen kullanıcı tarafından değiştirilmiş iç metni içerebilir. Ayrıca, bu metin ortalanmış hizalı veya açılamadı. Yerinde düzenleme kullanıcı etkileşimi daha ayrıntılı bir düzeyde içerir ve bu nedenle kullanıcıya durum bilgileri sunmak için uygun bir görsel ipuçları kümesi gerektirir.  
  
#### <a name="mouse-interaction"></a>Fare etkileşimi  
  
|Giriş|Sonuç|  
|-----------|------------|  
|Seçili nesneyi tıklatın|Nesneyi seçer ve nesne yeniden boyutlandırılabilir ise kesikli çizgi ve seçim tanıtıcıları görüntüler.|  
|Seçili nesneyi tıklatın|Nesne destekliyorsa yerinde düzenleme etkinleştirir. Nesneyi dışında tıklatarak yerinde düzenleme modunu devre dışı bırakır.|  
|Bir nesneyi çift|Nesneyi düzenlemek üzere arkasındaki kodda açar ve bir varsayılan olay işleyicisi uygunsa ekleyebilirsiniz.|  
|Bir nesneye işaret|Taşıma imleci işaretçi. Kendi parlaklığını veya renk gibi nesnenin görünümü değişebilir.|  
|Bir seçim tutamacını işaretleyin|Yeniden boyutlandırma imlecini işaretçi. İşaretçinin (uzağa taşınmış farklı Örneğin,) göre seçim tutamacını konumlandırılır gibi döndürme desteği nesneler için bazı seçimi tanıtıcıları için döndürme imleç işaretçinin değişebilir.|  
|Sürükleme|Nesne önceden seçili değilse, taşıma imleci işaretçi ve nesne taşır.|  
|Düzenleyici odağı kaybettiğinde|Nesne içeriğini ve son işlemi/seçim durumuna sırasında vardı görünüm korusa da yerinde düzenleme modunu devre dışı bırakır.|  
|Nesne Seçimi|Bir sınır, noktalı çizgi ya da nesne sınır vurgulamak için diğer görsel olarak ayrı işleme gösterilir.|  
|Seçili nesneyi yeniden boyutlandırma|Seçim tanıtıcıları tarafından belirtilir.<br /><br /> Yeniden boyutlandırılabilir bir nesne, onu yeniden boyutlandırılabilir her yönünü temsil eden sekiz tanıtıcıları vardır. Nesne yalnızca belirli yönde yeniden boyutlandırılabilir, daha az tanıtıcıları kullanılabilir. Burada sekiz tanıtıcıları etkileşimli olmayacaktır aşağıya doğru bir nesne kullanıcı boyutları, dört tanıtıcıları kullanılabilir. Tanıtıcı boyutları bağlı pencere kenarlık ve kenar Ölçümleriyle için **GetSystemMetrics** API işlevi ekran çözünürlüğünü orantılı olarak bir boyut.<br /><br /> ![Tanıtıcıları yeniden boyutlandırma](../../extensibility/ux-guidelines/media/0713-05_resizehandles.png "0713 05_ResizeHandles")|  
|Seçili nesneyi Döndür|![Tanıtıcıları döndürme](../../extensibility/ux-guidelines/media/0713-06_rotate.png "0713 06_Rotate")|  
  
#### <a name="keyboard-interaction"></a>Klavye etkileşimi  
  
|Giriş|Sonuç|  
|-----------|------------|  
|Tab|Nesnelerin mantıksal sırası arasında odak göstergesi Düzenleyicisi'nde taşır. Bu soldan sağa veya üst alt bağlı olarak olabilir **TabIndex** (veya eşdeğer) özellik değeri, nesne oluşturma sırası ve düzenleyici genel amacı. Üst karakter + sekme odak göstergesi yönünü tersine çevirir.|  
|Boşluk çubuğu|Tuş vuruşu korunur sırasında panlama modunu etkinleştirir. Ek fare girdisi, Görünüm penceresi konumu kaydırmak için gereklidir.|  
|Ctrl+Ara Çubuğu|Tuş vuruşu korunur sırada yakınlaştırma modunu etkinleştirir. Ek fare girdisi artırmak ve yakınlaştırma faktörünü azaltmak için gereklidir.|  
|Ctrl + Alt + eksi işareti|Bir düzey yakınlaştırma faktörüyle azaltır.|  
|Ctrl + Alt + artı işareti|Bir düzey yakınlaştırma faktörüyle artırır.|  
|SHIFT veya Ctrl|Nesne seçim grubuna ekler. CTRL nesneleri tek tek seçim grubundan kaldırmanızı sağlar.|  
|Enter|Nesne için varsayılan komut gerçekleştirir (genellikle açın veya Düzenle).|  
|F2|Nesne için yerinde düzenleme etkinleştirir.|  
|Ok tuşları|Seçili nesneleri için ok tuşunu basılı (örneğin, aynı anda 1 piksel) küçük artışlarla yönünde taşır|  
|CTRL + ok tuşları|Seçili nesneleri için ok tuşunu basılı (örneğin, 10 piksel birer birer) daha büyük artışlarla yönünde taşır|  
|Shift + ok tuşları|Seçili nesneleri (örneğin, aynı anda 1 piksel) küçük artışlarla ilgili yönüne göre yeniden boyutlandırır|  
|Ctrl + Shift + ok tuşları|Seçili nesneleri (örneğin, 10 piksel birer birer) daha büyük artışlarla ilgili yönüne göre yeniden boyutlandırır|  
  
 Kullanıcıların denetimlerin düzenlediğinizde, bu kullanıcı girişi ile otomatik olarak yeniden boyutlandırmak nesneler için mantıklı olabilir. Etiket denetimi kullanıcı düzenlemeleri, örneğin, ardından etiketi kullanıcı yalnızca yazılan metni görüntülemek için büyümesini. Bu yapılmazsa, kullanıcı denetimi el ile metni düzenledikten sonra yeniden boyutlandırma gerekir. Kullanıcı denetimleri çok sahipse, bu rote ve üretken görevi haline gelir.  
  
#### <a name="graphical-containers"></a>Grafik kapsayıcıları  
 Bazı durumlarda, grafik düzenleyicilerden Windows Forms Panel denetimi veya HTML Tasarımcısı'nda Kılavuz düzeni denetimi gibi diğer grafik nesneleri için kapsayıcı sağlar. Düzenleyicinizi diğer grafik nesneler için kapsayıcıları sağlıyorsa, aşağıdaki seçim modelin kapsayıcısı için yalnızca (standart model olarak yukarıda kapsayıcı izleyin nesnelerinde) kullanılmalıdır:  
  
|Giriş|Sonuç|  
|-----------|------------|  
|Tek tıklamayla kapsayıcısında|Kapsayıcı nesnesinin içerdiği nesnelerden herhangi birini doğrudan seçmeden seçer. Kapsayıcı taşınır ve/veya standart fare ve klavye (yukarıda açıklandığı gibi) ile yeniden boyutlandırılabilir. Kapsanan nesneleri kapsayıcısına ilişkisinde taşınır, ancak aynı zamanda doğrudan seçmediğiniz sürece kapsanan nesneleri yeniden boyutlandırılıyor değil.|  
|Kapsayıcının sınır bölgesini üzerine getirin|Fare kapsayıcı taşınabilmesi belirten taşıma imleci etkinleştirir.|  
|Kapsayıcının sınır bölgesi sürükleyin|Fare taşıma imleci değiştirir ve kapsayıcı (ve içinde kapsanan nesneler) taşır. Kapsayıcı ilk taşınamaz tek bir tıklatmayla seçilmesini.|  
|Kapsayıcı içindeki bir nesne üzerinde tek tıklamayla|Kapsayıcı (seçildiyse) seçimini kaldırır ve yalnızca tıklatılan nesneyi seçer.|  
|Shift + tıklatın veya Ctrl + bir kapsanan nesne ve/veya kapsayıcı üzerinde tıklatın|Tıklatılan nesnesi bir varolan seçimi veya seçim gruba ekler. Tıklatılan nesne seçim grubunun bir üyesi ise, seçim grubundan kaldırılır.|  
  
 Kapsanan nesneler, önceki bölümde açıklandığı gibi temel seçim modeline uymanız gerekir. Windows Forms Tasarımcısı kullanılabilirlik sınama gelen kullanıcılar kapsanan nesneler sorunsuz erişim (kapsama nesne tarafından uygulanan) müdahalede bulunan adımları olmadan bekleniyordu.  
  
#### <a name="disjoint-and-region-selections"></a>Ayrık ve bölge seçimleri  
 Grafik nesne düzenleyicileri ayrık seçimleri desteklemelidir. Bu grafik Visual Studio için Denetim görünümü göstermez unutmayın. Bkz: [grafik nesne seçim görünümü](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_GraphicalObjectSelectionAppearance) ayrıntılı visual özellikleriyle ilgili.  
  
 ![Ayrık ve bölge seçiciler](../../extensibility/ux-guidelines/media/0713-07_disjointregionselectors.png "0713 07_DisjointRegionSelectors")  
  
 **Ayrık seçimi**  
  
 Grafik düzenleyicilerden ayrıca bir kayan yazı tipi seçimi göstergesi bölge seçimlerinde sağlamalıdır. Grafik düzenleyicisini diğer nesne türleri (örneğin, metin) destekliyorsa, bölge seçimleri bu nesne türleri kısıtlamaları bağlı olarak mümkün olmayabilir.  
  
 ![Seçim çerçevesi](../../extensibility/ux-guidelines/media/0713-08_marqueeselection.png "0713 08_MarqueeSelection")  
  
 **Seçim çerçevesi**  
  
#### <a name="primary-and-secondary-selections"></a>Birincil ve ikincil seçimleri  
 Bazı grafik nesnesi düzenleyicileri düzenleyin veya gruplardaki nesneleri hizalama izin verin. Bu durumda, birincil ve ikincil seçimleri kavramı sunulması gereken. Birincil seçimin tüm diğer nesnelerin grup işlemlerinde yanıt vermek nesnesidir. Kullanıcının ilk seçtiği nesne birincil denetim olur ve sonraki seçimleri ikincil seçim haline gelir. Birincil seçimin hangi nesne birincil belirtmek için ikincil selection(s) gelen farklı bir görsel işlemden sahiptir:  
  
 ![Birincil ve ikincil seçimi](../../extensibility/ux-guidelines/media/0713-09_primarysecondary.png "0713 09_PrimarySecondary")  
  
 **İki ikincil seçimleri birincil seçimi**  
  
####  <a name="BKMK_GraphicalObjectSelectionAppearance"></a> Grafik nesne seçim görünümü  
 Sınırlama kutusu nesnenin etrafında dikdörtgen desende çizilmiş kareler seçimi tanıtıcılarıdır. Grafik bir grafik nesnesi tanıtıcı, boyutlandırma ve yerinde düzenleme görünümü olabilir çeşitli durumlarını örnekleri gösterilir. Tanıtıcıları boyutunu pencere kenarlık ve kenar ölçümleri kullanarak bağlı olması **GetSystemMetrics** API.  
  
|Durum|Görünüm|Visual ayrıntıları|  
|-----------|----------------|--------------------|  
|**Seçilmemiş**|Varsayılan|![Varsayılan düğme durumu](../../extensibility/ux-guidelines/media/0713-10_defaultstate.png "0713 10_DefaultState")||  
|**Birincil seçimi**|Yeniden boyutlandırılabilir|![Birincil seçimi ile yeniden boyutlandırın tanıtıcıları](../../extensibility/ux-guidelines/media/0713-11_primaryresize.png "0713 11_PrimaryResize")|![Birincil seçimi ile yeniden boyutlandırın tanıtıcıları &#40;uzaklaştırılacağını&#41;](../../extensibility/ux-guidelines/media/0713-12_primaryresizezoom.png "0713 12_PrimaryResizeZoom")|  
|**Birincil seçimi**|Yeniden boyutlandırılabilir değil|![Birincil seçim olmadan yeniden boyutlandırma tanıtıcıları](../../extensibility/ux-guidelines/media/0713-13_primarynoresize.png "0713 13_PrimaryNoResize")|![Birincil seçim olmadan yeniden boyutlandırma tanıtıcıları &#40;uzaklaştırılacağını&#41;](../../extensibility/ux-guidelines/media/0713-14_primarynoresizezoom.png "0713 14_PrimaryNoResizeZoom")|  
|**Birincil seçimi**|Kilitli|![Kilitli birincil seçimi](../../extensibility/ux-guidelines/media/0713-15_primarylocked.png "0713 15_PrimaryLocked")|![Kilitli birincil seçimi &#40;uzaklaştırılacağını&#41;](../../extensibility/ux-guidelines/media/0713-16_primarylockedzoom.png "0713 16_PrimaryLockedZoom")|  
|**İkincil seçimi**|Yeniden boyutlandırılabilir|![İkincil seçimi ile yeniden boyutlandırın tanıtıcıları](../../extensibility/ux-guidelines/media/0713-17_secondaryresize.png "0713 17_SecondaryResize")|![İkincil seçimi ile yeniden boyutlandırın tanıtıcıları &#40;uzaklaştırılacağını&#41;](../../extensibility/ux-guidelines/media/0713-18_secondaryresizezoom.png "0713 18_SecondaryResizeZoom")|  
|**İkincil seçimi**|Yeniden boyutlandırılabilir değil|![İkincil seçim olmadan yeniden boyutlandırma tanıtıcıları](../../extensibility/ux-guidelines/media/0713-19_secondarynoresize.png "0713 19_SecondaryNoResize")|![Yeniden boyutlandırma olmadan ikincil seçimi &#40;uzaklaştırılacağını&#41;](../../extensibility/ux-guidelines/media/0713-20_secondarynoresizezoom.png "0713 20_SecondaryNoResizeZoom")|  
|**İkincil seçimi**|Kilitli|![Kilitli ikincil seçimi](../../extensibility/ux-guidelines/media/0713-21_secondarylocked.png "0713 21_SecondaryLocked")|![Kilitli ikincil seçimi &#40;uzaklaştırılacağını&#41;](../../extensibility/ux-guidelines/media/0713-22_secondarylockedzoom.png "0713 22_SecondaryLockedZoom")|  
|**Etkin kullanıcı Arabirimi**|Varsayılan|![Kullanıcı Arabirimi etkin durumu](../../extensibility/ux-guidelines/media/0713-23_uiactive.png "0713 23_UIActive")|![Kullanıcı Arabirimi etkin durumu &#40;uzaklaştırılacağını&#41;](../../extensibility/ux-guidelines/media/0713-24_uiactivezoom.png "0713 24_UIActiveZoom")|  
  
### <a name="view-selection-models"></a>Seçim modelleri görüntüle  
  
#### <a name="tree-view"></a>Ağaç görünümü  
 Ağaç görünümünde seçimi basit vurgulanmış gösterilir. Kullanıcı bir düğüm adı veya bir düğüm simgesi tıklarsa, düğüm seçili duruma gelir. Düğüm solundaki üçgen karakterlerin genişletin veya ağaç denetimi sözleşme ancak tek bir istisna, kullanıcının seçimini etkilemez: üst düğümü seçimi o düğümün bir alt olduğunda daraltma bağlı seçimi üst öğeye taşır.  
  
 ![Visual Studio tipik ağaç görünümünde](../../extensibility/ux-guidelines/media/0713-25_treeview.png "0713 25_TreeView")  
  
 **Visual Studio'da tipik ağaç görünümü**  
  
 Ağaç görünümleri bile ağacında birden çok düzeyi arasında bitişik ve ayrık seçimlerinizi destekleyebilir. Bitişik veya ayrık görünür ağaç düğümleri üzerinde birden çok seçimin yapılması gerekir. Bir düğüm daraltılmışsa, ayrık seçimi kaybolur ve daraltılmış düğümü seçimi alır. Bu şekilde, kullanıcı bir işlem tarafından etkilenen düğümleri görebilirsiniz. Düğümleri daraltıldığında bu hangi düğümlerin etkilenebilir belirsiz olur.  
  
 Üst düğümü seçildiğinde olabilir ancak burada üst ve tüm alt uygulamak bir işlem için bir anlam durumlarda işlemi üst öğeye uygulamalıdır. Bu durumda, bir onay kutusu veya "tüm alt öğelerini uygulama" seçeneği kullanıcıya açık yapmak için onay iletişim kutusu gibi işlemi sırasında ek kullanıcı Arabirimi sağlar.  
  
##### <a name="renaming"></a>Yeniden adlandırma  
 Ağaçtaki düğümler yeniden adlandırma destekliyorsa, yeniden adlandırma yerinde yapılması gerekir. Yerinde işlemi standart, Visual Studio tüm ağaç denetimlerinde arasında olmalıdır. Hemen tüm düğümünün adı, kullanıcı girişi kabul etmeye hazır kapsayan metin seçimle yerinde düzenleme modunu etkinleştirir rename komutu sağlar. Bir dosya düğümünü temsil ediyorsa, dosya adı uzantısını içermelidir. Seçim Vurgusu dosya adı uzantısını değil yalnızca gövdesini içermelidir.  
  
|Giriş|Sonuç|  
|-----------|------------|  
|Enter tuşu|Yeniden adlandırma işlemi tamamlar|  
|ESC tuşuna|Yeniden adlandırma işlemi iptal eder|  
|Yerinde düzenleme bölgesinin dışındaki tıklatarak|Yeniden adlandırma işlemi tamamlar|  
|Geri alma|Yeniden adlandırma işlemi iptal etmek için kolayca geri sağlayın|  
  
#### <a name="selection-within-lists-and-grid-controls"></a>Seçim listeleri ve kılavuz denetimleri içinde  
 Anahtar listesi seçimdeki kavramıdır satır tabanlı olduğundan, tüm satırı bir seçim yapıldığında, yani bir birim olarak seçilir. Bunun aksine, kılavuzları belirli herhangi bir satır yönünü etkilemeden seçilmesi hücrelere izin verebilirsiniz. Kılavuzları Ayrıca seçili ve üst satırları ile etkileşim kurarak seçimi hiyerarşinin tüm dalları izin iç içe geçmiş satır (TreeGrid olduğu gibi) bir hiyerarşi içermiyor olabilir. Seçim listesindeki tüm veri satırının üzerinde basit vurgulama renk tarafından gösterilir. Odağı geçerli düzenlenebilir satır veya hücre (tüm hücreleri salt okunur ise satır) çevresine tek pikselli noktalı kenarlık tarafından gösterilir.  
  
> [!NOTE]
>  **Odak** ve **seçimi** farklı kavram olmasıdır. *Odak* göstergesidir hangi UI öğesi hedeflediği açıkça başka bir nesnede yönlendirilmiş giriş almaya çalışırken *seçimi* nesneleri izleyen bir dizi eklenmek üzere bir nesnenin durumunu gösterir Operations yer alabilir.  
  
 Seçimleri listelerinde bitişik, ayrık, olabilir veya bölge. Ne zaman birden çok seçimin izin verilen, sürekli ve ayrık seçimi her zaman, bölge (kutusu) seçimleri desteği sırasında desteklenmesi gereken isteğe bağlıdır. Bölgesi seçimlerin listesi gövdesi boşluk içinde sürükleyerek başlatılır.  
  
|Nesne|Seçim|  
|------------|---------------|  
|List|Bitişik|(Birden çok seçimin izin verildiğinde) her zaman desteklenir.|  
|List|Ayrık|(Birden çok seçimin izin verildiğinde) her zaman desteklenir.|  
|List|Bölge|İsteğe bağlı destek. Fare listesi gövdesi boşluk içinde sürükleyerek başlattı.|  
  
 Bir listede bir kere tıklatarak tıklatın oluştuğu satırı seçer. Kullanıcı yerinde düzenleme destekleyen bir liste hücreyi tıklatın olursa, hücre de hemen yerinde düzenleme için etkinleştirilir. Aksi takdirde, tüm satırı hemen seçilir ve Vurgu gösterir.  
  
 Liste gövdesinde sürükleyerek üç şey yapar:  
  
-   Bir bölge seçim listesi destekliyorsa ve fare aşağı boşluk ise başlatır  
  
-   Sürükleme kaynağı olan liste hücre veya satır destekliyorsa, bir Sürükle ve bırak işlemi başlatır  
  
-   Geçerli satırda seçer  
  
##### <a name="in-place-editing"></a>Yerinde düzenleme  
 Yerinde düzenlemeye izin verirken, iki temel modeli vardır: Basit Düzen denetimi ve özellik Seçici. Basit Düzen denetimi ile içerik vurgulanmış ve kullanıcı yerinde düzenleme etkinleştirilir hemen girişi için hazır olur. Bir özellik Seçici uygulanan burada özelliği Seçici çağırır düğmesi yerinde düzenleme modu etkinleştirildikten sonra geçerli seçim değil vurgulanır görüntülenir. Seçici düğmesi hücrede sağa hizalı olması gerekir. Yerinde düzenleme örnekler için bkz: **Özellikler penceresini** ve **görev listesi** Visual Studio.  
  
##### <a name="keyboard-support"></a>Klavye desteği  
 Seçim listeleri ve kılavuzları klavye desteği standart Windows kuralları aşağıdaki gibidir:  
  
-   Ok tuşları odağı taşındıkça her satır/hücresi seçerek listenin gidin.  
  
-   Shift + ok ok tuşlarını yönde bitişik seçim gerçekleştirir.  
  
-   Ctrl + Ara çubuğu değiştirir tarafından ekleme ve liste öğeleri ayrık bir seçim oluşturma seçimden kaldırma arasında ardından OK.  
  
-   İç içe geçmiş hiyerarşileri içeren kılavuzları, bir üst satırın sağ ok tuşu genişletir ve sol ok tuşunu bir daraltır.  
  
-   Hücreleri düzenlenebilir olup olmadığını SEKME tuşuna odağı geçerli satır hücrelerde arasında taşır.  
  
-   Enter tuşuna varsayılan komutu yerine getirir, listedeki bir öğe (genellikle **açık**).  
  
-   Şu anda seçili hücre için yerinde düzenleme F2 anahtar etkinleştirir.  
  
##  <a name="BKMK_PersistenceAndSavingSettings"></a> Kalıcılığı ve ayarları kaydediliyor  
  
### <a name="overview"></a>Genel Bakış  
 Visual Studio'da her yazılım bileşeni kendi durumu ve kalıcılığı genellikle sorumlu olsa da, Visual Studio gibi bazı durumlarda, ayarları otomatik olarak pencere boyutları ve konumları ile kaydeder. Aşağıdaki tabloda, otomatik olarak kaydedilir ve açık bir kullanıcının gerektiren veya gerçekleştirilecek eylemin programlanmış ayarlarını birleşimidir.  
  
|Nesne|Ne kaydetmek için|Zaman kaydetmek için|Kaydedileceği yeri|  
|------------|------------------|------------------|-------------------|  
|Seçilebilir nesne (örneğin, kod satırı)|Kod satırında bir kesme noktası<br /><br /> Kod satırı ile ilişkili bir kullanıcı kısayolu|Proje zaman kaydedilir|**Kullanıcı seçenekleri (.suo)** proje dosyası|  
|İletişim kutusu|Taşıdıysanız iletişim kutusunda, konumu<br /><br /> Kullanıcı iletişim kutusunda en son kullanılan görünümü|Ne zaman iletişim kutusunu kapatır<br /><br /> Visual Studio oturumu sona erdiğinde|Bellek<br /><br /> Kayıt defterinde **HKEY_Current_User**|  
|Pencere|Boyut ve konum penceresi|Ne zaman penceresini kapatır<br /><br /> Visual Studio modu değiştiğinde<br /><br /> Visual Studio oturumu sona erdiğinde|**Kullanıcı seçenekleri (.suo)** proje dosyası<br /><br /> Pencere ayarları için özel seçenekleri dosyası|  
|Belge|Belgedeki geçerli seçim<br /><br /> Belgenin görünümü<br /><br /> Kullanıcının ziyaret son çeşitli yerlerde|Ne zaman Belge kaydedildiğinde|**Kullanıcı seçenekleri (.suo)** proje dosyası|  
|Proje|Dosyalara başvurular<br /><br /> Disk üzerindeki dizinlere başvuruları<br /><br /> Diğer yazılım başvurular<br /><br /> Bileşenler<br /><br /> Projeyle ilgili durum bilgileri|Proje zaman kaydedilir|Proje dosyası|  
|Çözüm|Proje başvuruları<br /><br /> Dosyalara başvurular|Proje ve çözüm zaman kaydedilir|**Çözüm (.sln)** dosyası|  
|Ayarlarında **Araçlar > Seçenekler**|Klavye özelleştirmeleri<br /><br /> Araç çubuğunu özelleştirme<br /><br /> Renk düzenleri|Zaman **Araçlar > Seçenekler** iletişim kutusunu kapatır<br /><br /> Visual Studio oturumu sona erdiğinde|Kayıt defterinde **HKEY_Current_User**|  
  
 Hangi kullanıcı yapıyor ve, yaptıklarını zaman proje ya da çözüm dosyanın bir parçası olarak bir parçası olarak bir ayar (oturumu sırasında), diske (oturumlarında bir kayıt defteri ayarı olarak), kaydedilen bellekte kaydedilmekte olduğu olup olmadığını belirleyen **çözümü Seçenekler (.suo)** dosya ya da bir özel ayarlar yalnızca yazılım bileşeninin dosyası olarak bilmektedir. Yukarıdaki tabloda ayarları kaydedilebilmesi için çeşitli olayları gösterir. Ancak, bazen durumu kaydetmek isteyebilirsiniz vardır:  
  
-   Kullanıcı bir iletişim kutusu veya penceresi içinde konuma değiştiğinde  
  
-   Ne zaman kullanıcı başka bir pencere için odak aktarır.  
  
-   Hata ayıklama modu olarak gelen kullanıcı geçiş yaptığında tasarlama  
  
-   Kullanıcı hesaplarında devre dışı oturum açtığında  
  
-   Bilgisayar zaman hazırda beklemeye geçtiğinde veya kapatıldığında  
  
-   Bilgisayar/sabit sürücüyü hakkında ve yeniden biçimlendirilen yeniden kurmak için olduğunda  
  
### <a name="window-configurations"></a>Pencere yapılandırmaları  
 Geliştirme ortamı temel sunumunu bir pencere yapılandırmadır - aracı windows mevcut listesi ve düzenlenmiş şekilde oluşan bir düzeni. Pencere düzenini IDE aynı görünür bir kullanıcı başlatır, bunlar zaman en son Visual Studio çıkıldı şekilde (IDE windows) IDE tarafından yönetilen windows için kullanıcı başına düzeni bilgileri kalıcıdır. IDE windows konumunu ve durumunu XML biçimi özel seçenekleri dosyasında kalıcıdır. IDE içinde yüklenen paketler tarafından oluşturulan aracı windows kayıt defterinde, durum bilgilerini kalıcı hale getirmek ve olabilir veya kullanıcı başına olmayabilir.  
  
#### <a name="profile-specific-layouts"></a>Profil özel düzenler  
 Her profil özel Geliştirici kişiler için tanıdık bir şekilde düzenlenmiştir aracı pencere düzenlerini içerir (Visual C++ geliştiriciler beklediğiniz görmek **Çözüm Gezgini** C# geliştiricileri görmeyibeklediğinizsıradaIDEsoltarafındaki **Çözüm Gezgini** sağ taraftaki). Kullanıcı profili başlangıçta seçtikten sonra profili özel pencere düzenlerini yüklenir. Bir paket yazarına, müşterinin deneyim için en uygun pencere düzenini penceresini yapılandırmanın kullanıcının yaptığı değişiklikler sonra kalıcı olduğunu bilmek belirlemeniz gerekir.  
  
##  <a name="BKMK_TouchInput"></a> Dokunmatik giriş  
 Kullanıcılar, dokunmatik aygıtlarda Microsoft geliştirme ürün giderek kullanıyor. Ancak, dokunmatik aygıtlarda geliştirme araçlarını kullanmayı zor hale engelleri vardır. Kullanıcıların bir güvenilir ve kesin dokunma deneyimi sağlamak için Ürünlerimiz beklediğiniz. Bu yönergeleri amacı, hangi dokunma özellikleri eklemenizi ve Visual Studio ve ilgili ürünler arasında tutarlı dokunmatik deneyimini teşvik eden hakkında kararlar bildirmek sağlamaktır.  
  
### <a name="levels-of-experience"></a>Deneyimi düzeyleri  
 Deneyimi aşağıdaki düzeylerini sunmak için hangi dokunma özellikleri dokunma yatırım ilgi istenen düzeyini göre takımlar karar vermenize yardımcı olacak bir kılavuz hizmet vermek üzere tasarlanmıştır.  
  
-   **Temel deneyimi** hiçbir geçerliliği sona erer işlerini boyunca tanımlanabilmesini sağlamak istediğiniz takımlar özellikleri dokunma aranır.  
  
-   **Deneyimi en iyi duruma getirilmiş** en yaygın dokunma özellikleri (örneğin, internet tarayıcı uygulamalarında genellikle mevcut kodlar) sağlamak istediğiniz takımlar içindir.  
  
-   **Yükseltilmiş deneyimi** yetenekleri gibi eklemek istediğiniz ekipleri olarak hareketleri veya kendi uygulama yapabilirsiniz diğer isteğe bağlı özellikleri dokunma-ilk kolay.  
  
||Temel deneyimi|En iyi duruma getirilmiş deneyiminin|Yükseltilmiş deneyimi|  
|-|----------------------|--------------------------|-------------------------|  
|Kullanıcılara sağlar...|Kod ve çözüm/proje geçerliliği sona erer okuma düzeyi Düzelt|Bakım, refactors ve gezinme görevleri|Tutarlı, sezgisel ve akıcı bir deneyim güvenle çalışmayabilir|  
|Düzenleyici|Dokunma kaydırma ve seçimi<br /><br /> Scrollbar dokunma atlamak ve basın + sürükleme için|Tutarak yakınlaştırma<br /><br /> Hızlı kaydırma<br /><br /> Seçim<br /><br /> Bağlam menüsünün kullanımı kolay||  
|Üst araç pencereleri|Liste kaydırma<br /><br /> Öğe seçimi<br /><br /> Scrollbar dokunma atlamak ve basın + sürükleme için|Kolay öğesi kaydırma ve seçimi||  
|Pencereleme||Pencereyi yeniden boyutlandırma<br /><br /> Hızlı erişim||  
|Belge iyi||Açık dosyalar arasında kolay gezinme||  
|Hareketleri||Ortak hareketleri IDE üzerinde çalıştığından emin olmak|Hareketi tabanlı Eylemler<br /><br /> Sürükle ve bırak ve tasarımcıları desteği|  
|Diğer konular|||Özel Ekran Klavyesi|  
  
#### <a name="gestures"></a>Hareketleri  
 Hareketleri kullanıcıların daha karmaşık bir etkileşim aksi gerektirebilir komutları bir kısayol sağlar. Üzerinde Windows yönergelerine başvurun [Masaüstü uygulamaları için ortak dokunma hareketleri](http://msdn.microsoft.com/en-us/library/windows/desktop/dd940543\(v=vs.85\).aspx)ve kaydırma ve yakınlaştırma gibi basit hareketler dahil olmak üzere çoğu hareketleri için bu yönergeleri izleyin.