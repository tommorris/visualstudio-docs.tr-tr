---
title: "Visual Studio SDK sözlüğü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: glossary [Visual Studio SDK]
ms.assetid: b64d432b-c39b-4904-ad18-3c3218b6e3aa
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9bf6b39d74e88289d9521216f98aa3195e30d6d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-sdk-glossary"></a>Visual Studio SDK sözlüğü
Bu sözlük kullanılan terimler için tanımları sağlar, [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] belgeleri.  
  
## <a name="terms"></a>Koşulları  
 eklentisi  
 Bir yardımcı programı uygulaması, sürücü veya birincil bir uygulamaya eklenen diğer yazılım. Visual Studio tümleşik geliştirme ortamında (IDE) bir eklenti IDE özelliklerini genişleten bir Otomasyon tabanlı uygulamasıdır.  
  
 otomatikleştirme modeli  
 Visual Studio genişletilebilirlik modeli olarak önceki sürümlerinde bilinen Otomasyon, size sağladığı bir programlama arabirimi erişmek için temel alınan yordamları o sürücüye IDE modelidir. Eklentiler, sihirbazlar ve makrolar denetlemek için Otomasyon modeldeki nesneleri kullanın veya IDE işlevselliğini genişletin.  
  
 komut UI bağlamı  
 Bir kullanıcı Arabirimi komut veya gibi bir araç çubuğu öğesi görünürlüğünü bir GUID ilişkilendirmesini. Bir pencere eklenmemiş komutu UI bağlam seçimi bağlam olmamasıdır.  
  
 Komut UI bağlamı için kullanılabilir:  
  
-   Belirli bir pencere etkin olduğunda görüntülenen bir araç için bir GUID atayın.  
  
-   Bir GUID yüklemek veya bir VSPackage çalıştırmak zorunda kalmadan bir komut kullanılabilirliğini atayın.  
  
-   Etkin anahtar bağlama etkilemek için bir GUID atayın.  
  
-   Makro kaydı açmak için bir GUID atayın.  
  
-   Hata ayıklama modunu etkinleştirmek veya tasarım ve bir düzenleyicide çalışma modu arasında geçiş yapmak için bir GUID atayın.  
  
 bileşenleri  
 Bu uygulama yazılımın uygulaması hakkında önceden var olan tüm bilgilere sahip olmadan bir uygulamanın işlevselliğini parçası yapılan yazılım parçası. Bir bileşeni ve bir uygulama arasındaki iletişim sadece OLE stili arabirimleri önemlidir.  
  
 Bileşen Yöneticisi  
 Hizmet, bir `SOleComponentManager`, en üst düzey bileşenleri için kullanıcı olmayan arabirimi düzenleme hizmet sağlar. `SOleComponentManager` Hizmet uygulayan `IOleComponentManager` arabirimi.  
  
 Bileşen UI Yöneticisi  
 Hizmet, bir `SOleComponentUIManager`, kullanıcı arabiriminin düzenlemesi hizmetler sağlar. `SOleComponentUIManager` Hizmet uygulayan `IOleComponentUIManager` ve `IOleInPlaceComponentUIManager` arabirimleri.  
  
 İçerik Paketi  
 Bir `IVsUserContext` nesnesini (COM nesnesi) bağlı bir ortamı bileşeni. Bu nesne, arama anahtar sözcükleri, F1 anahtar sözcükleri ve bileşenle ilgili olduğu öznitelikleri tutar. İçerik paketleri ayrıca onlara bağlı tüm üzere paketler üzerine gelin.  
  
 İçerik sağlayıcı  
 Kendisiyle ilişkili bir içerik paketi sahip IDE bir bileşendir. Bu bileşenler, araç penceresi, Düzenleyicisi veya proje hiyerarşisi içerir.  
  
 tasarımcı  
 (Forms, düğmelerin ve diğer denetimlerin) kullanıcı Arabirimi öğelerini işlemek kullanıcılara bir programlama arabirimi.  
  
 DocData  
 Temel alınan veri bir dünyada belgenin şifrelenmiş bir COM nesnesi belge/görünüm ayrımı olduğu (örneğin bir metin düzenleyicisi durumunda, bu tüm metin düzenleyicisi görünümleri temel metin arabelleğini olacaktır). Bu nesne EditorFactory sağlamazsa, IDE adına birinde üretirler. Bu nesnenin veri kalıcılığını yönetmek için sorumluluğundadır ve birden çok paylaşım anlamları bu görünümlerini aynı `DocData`. Varsa `DocData` nesnesi `IOleCommandTarget` arabirimi, komut UIShell yönlendirme olarak eklenecektir.  
  
 DocObject  
 Ana bilgisayar tarafından sağlanan bir çerçevesinde UI barındırmak için kullanılan teknolojisi. Bu terim herhangi destekleyen katıştırmak için daha belirgin olarak başvuran `IOleDocument` ve ilgili arabirimler. Bu teknoloji COM belgeleri uygulama ayrıntılarını, aracı windows 5.0 Visual Basic'te, Visual Basic 6.0 ve benzeri ActiveX tasarımcılarına gibi birçok olası uygulama vardır.  
  
 belge  
 Genel bir bütün olarak belge başvurmak için kullanılan — hem `DocData` ve `DocView`. Örneğin, bir DocumentFrame içeren bir `DocView`, ancak aynı zamanda bir başvuru korur `DocData` Kalıcılık işlemek için.  
  
 DocView  
 DocObject/katıştırma/görüntülemek ve arka plandaki işlemek için kullanıcı ile etkileşim WindowPane `DocData`. Kullanıcıların parçası olan belge/görünüm ayrımı avantajlarından yararlanabilir mi Not `DocObject` tasarım arabirim. Kullanıcılar, temel alınan veri olarak bilinen daha soyut (ve daha az resmileştirilmiş) kavramını kullanmak yerine bir görünüm olarak davranacak şekilde tüm DocObject kullanmak `DocData`. `DocView`Belge çerçeve nesneleriyle IDE (MDI alt pencereleri) katıştırılmış nesneler her zaman.  
  
 DTE  
 `DTE` (Geliştirme araçları genişletilebilirliği) nesnesidir program aracılığıyla otomatikleştirmek ve IDE genişletmek sağlar Visual Studio Otomasyon modelinde en üstteki erişim noktası.  
  
 Dinamik Yardım penceresini  
 IDE tarafından uygulanır ve arama anahtar sözcüğü veya F1 Yardım konularını listesini görüntüleyen araç penceresi.  
  
 düzenleyici  
 Uygulayan kod (sınıfı, CLSID) `DocView`. Ayrıca uygulayan `DocData` verilerini görüntüleme ayrımı destekleniyorsa.  
  
 uzantı  
 Değiştirir, bir özellik özelleştirir veya bir IDE ekler. Uzantılarını otomasyon modeli veya VSPackages kullanarak oluşturun.  
  
 Dış Düzenleyicisi  
 Microsoft Word gibi IDE özel değildir bir düzenleyici. Kendi mekanizmalar aracılığıyla kayıtlı ve IDE dışında kullanılabilir. Bu düzenleyici katıştırılabilen, IDE içindeki penceresi içinde görüntülenir. Katıştırılmış olamaz, ayrı üst düzey bir pencere oluşturulur.  
  
 hiyerarşi  
 Ağaç düğümleri, özellikler kümesi ile ilişkili her düğüm.  
  
 bağımsız üst düzey bileşeni  
 Engelleyici olmayan bir üst düzey pencere kullanır ve etkili bir şekilde bir tek başına uygulamayı pencere olarak çalışabilir, ancak bir işlem içi nesnesi olarak uygulanan bir bileşeni. Bu nedenle, bağımsız bir üst düzey bileşeni, Şekil ve IDE ileti döngüsü hizmetleriyle koordine gerekir. İşlem içi nesneleri kendi ileti döngüsü gerekmez.  
  
 bilgi sağlayıcısı  
 Bilgi sağlayıcısı, arama anahtar sözcükleri ve biçiminde konuların listesini döndürmek modülüdür `IVsUserContextItem` nesneleri. F1'e ve arama anahtar sözcüğü öğeleri için bilgi sağlayıcısı sağlamak için derlenmiş Yardım dosyanızı kaydetmek (. HxS) sistemiyle. Bu dosyalar Yardım konularında dinamik Yardım penceresinde görüntülenir ve kullanıcı F1 tuşuna bastığında olup olmadığını gösterilen konuların listesi sağlamak için kullanılır.  
  
 yerinde bileşeni  
 Arabirimini uygulayan bir VSPackage nesnesi `IOleInPlaceComponent` görsel olarak IDE tarafından sahip olunan bir belge penceresi içinde bulunan bir pencere yönetmek için arabirim. Yerinde bileşenleri standart OLE menü-birleştirme içinde yer almayan; Bunun yerine, kendi kullanıcı arabirimi öğeleri IDE içinde tümleştirin.  
  
 Yerinde bileşenlerinin iki tür vardır: sabit yerinde bileşenleri ve bileşen kontrol eder.  
  
 Sabit yerinde bileşenleri menüleri, araç çubukları ve doğrudan IDE içinde yerleşik varsa olarak görünen IDE kullanıcı arabirimine sıkı bir şekilde tümleşik komutlar vardır.  
  
 Bileşen denetimleri IDE içinde tümleşik kendi kullanıcı arabirimi öğeleri yoktur; Bunun yerine bunların IDE'nin menüleri, komutları ve araç çubuklarını kullanın. Örneğin, bir formda katıştırılmış zengin metin denetimi içinde seçili bir sözcük kalın kalın komutu kullanılabilir. Ancak, dinamik olarak yüklü bileşen özel kullanıcı Arabirimi öğeleri görüntülenmesi bileşeni denetimleri isteyebilir.  
  
 Dil hizmeti  
 İşaretleme ve renklendirme metin gibi bilgisayar dil kodu düzenleyicileri özelliklerini uygulamak VSPackage geliştiricilerinin sağlayan nesne kümesi.  
  
 Çeşitli dosyalar proje  
 Projesi herhangi bir projede olmayan ev açık dosyalar için kullanılır. Bu projede öğe listesinin kalıcı değildir.  
  
 proje  
 Projeleri yapılma hiyerarşi nesnelerin ve COM nesnelerini uygulayan `IVsHierarchy` arabirimi.  
  
 Proje özgü Tasarımcısı veya Düzenleyicisi  
 Bağımsız olarak proje türü kullanılamaz Tasarımcısı. Tüm proje özgü tasarımcıları kayıt defterinde Düzenleyici üreteci bilgilerini girmeniz gerekir. Belirli bir dosya türü daki belirli bir projeyi açtığınızda IDE Tasarımcı örneğini oluşturabilirsiniz.  
  
 Proje türü penceresi  
 Şu anda etkin proje hiyerarşisi ve öğesi genel seçimi bağlamdan sürekli izler penceresini açın. Proje türü pencerelerini kullanma `SVsTrackSelectionEx` hizmeti değişiklikleri IDE uyarı ve geri bildirim kullanıcıya görüntülenecek. Çözüm Gezgini proje türü penceresinin bir örnektir.  
  
 Özellik penceresi  
 Önceden özellik tarayıcısı.  
  
 başvuru tabanlı projeler  
 Aynı dizinde olması proje dosyalarını gerektirmeyen projesi. Bunun yerine, ilgisiz diğer dizinlerdeki dosyalara başvurularından tutulur ve proje tarafından korunur.  
  
 çalışan belge tablosu  
 İç yapısı olarak IDE tüm geçerli açık belgelerden listesini tutar. Bu liste bellek olup olmadığını belgeleri şu anda düzenlenmekte olan bağımsız olarak tüm açık belgeleri içerir. Bir belge, bir düzenleyici, proje dosyalarında veya ana proje dosyası (örneğin, *.vcproj) açılan saklı yordamları da dahil olmak üzere kaydedilir herhangi bir öğeyi ' dir.  
  
 Seçim bağlamı  
 IDE her penceresinde ayrıntılarını parçası olan ve etkin seçimleri izlemek için kullanılan veri. Seçim bağlam oluşur:  
  
-   İşaretçi `IVsHierarchy` proje hiyerarşisinin arabirimi  
  
-   Proje öğesi öğe tanımlayıcısı.  
  
-   İşaretçi `ISelectionContainer` arabirimi özelliklerini etkin nesneler için erişim sağlama.  
  
-   Öğesi değerleri dizisi.  
  
 hizmet  
 Tek bir COM nesnesinde bulunan COM arabirimleri kümesi için bir sözleşmede. Bir GUID ile tanımlanan, bir hizmet oluşturduğunuzda servisi taşıyan COM arabirimleri kümesini tanımlar. COM nesneleri Hizmetleri birbirleriyle iletişim kurmak için kullanın.  
  
 Çözüm  
 Bir kullanıcı ile çalıştığı ilgili projeleri grubudur.  
  
 Standart Tasarımcısı  
 Proje Türü bağımsız olarak kullanılabilir bir tasarımcı. Tüm standart tasarımcıları kayıt defterinde Düzenleyici üreteci bilgilerini girmeniz gerekir. Belirli bir uzantıya sahip bir dosyayı her açtığınızda IDE Tasarımcı örneğini oluşturabilirsiniz. Verileri bir dosyaya kalıcı olması gerekir.  
  
 Standart Düzenleyici  
 Herhangi bir projedeki türde bağımsız kullanılabilir düzenleyici. Bu tür düzenleyicileri kayıt defterinde kayıtlı EditorFactories sahip. Bu bulup Düzenleyicisi çağırmak IDE sağlar.  
  
 Standart işletim sistemi Düzenleyicisi  
 Visual Studio bir katıştırma değil belirli. İyi bilinen Win32 anahtarlar kullanılarak kaydedilir (örneğin, Win32 Explorer çağrılacak bildiği). Bu tür bir düzenleyici katıştırılabilen, düzenleyici hala IDE yerinde görünecek. Aksi takdirde, ayrı üst düzey bir pencere için bu tür düzenleyicileri oluşturulur.  
  
 üzere paketi  
 Bir `IVsUserContext` nesnesi bağlı bir içerik paketi. Bu nesne, arama anahtar sözcükleri, F1 anahtar sözcükler ve bir IDE bileşeni içinde bir seçim özniteliklerini tutar. Üzere bir komut bir araç penceresi ya da bir anahtar sözcüğü bir düzenleyicide örneklerindendir.  
  
 Görev listesi  
 IDE tarafından uygulanır ve etkin görevleri listesini görüntüler araç penceresi.  
  
 Metin arabelleği  
 Nesne için ortak ad `VSTextBuffer`.  
  
 Metin görünümü  
 Nesne için ortak ad `VSTextView`.  
  
 Aracı üst düzey bileşeni  
 IDE kullanıcı arabirimi ile sıkı bir şekilde düzenlemekten, bir geçici açılan pencere olarak çalışır bileşeni. Bağımsız seviye bileşenleri gibi aracı en üst düzey bileşenleri de şekil ve IDE ileti döngüsü hizmetleriyle koordine gerekir.  
  
 üst düzey bileşeni  
 Engelleyici olmayan bir üst düzey pencere bir IDE penceresinin istemci alanını yerine yönetir VSPackage nesnesi. Üst düzey bileşenleri gerçekleştirmek `IOleComponent` boşta kalma süresi ileti döngüsü Hizmetleri erişim gibi yararlanmak için arabirim.  
  
 Etkin kullanıcı Arabirimi  
 Görünür ve şu anda odaklanmış bir VSPackage nesnesi.  
  
 UI hiyerarşisi  
 Arabirimini uygulayan bir COM nesnesi `IVsUIHierarchy` bir hiyerarşinin görüntü izin vermek için arabirim. UI hiyerarşi penceresini uygulayan `ISelectionContainer` Özellikler penceresini güncelleştirmek üzere arabirim; diğer proje türü windows istenirse, bu uygulama kullanabilirsiniz.  
  
 VSCT  
 Visual Studio komut tablo. .Vsct dosya yerleşimi ve menüleri ve araç çubukları komutları XML biçiminde davranışları hakkında bilgi içerir.  
  
 VSPackage  
 Visual Studio IDE birini veya birkaçını katkıda bulunarak genişleten bir yazılım yüklenebilir bir parçasını: kullanıcı arabirimi, hizmetleri, proje türleri veya Düzenleyicisi/designer. Bir VSPackage uygulayan bir COM nesnesi oluşur `IVsPackage` arabirimi ve seçim ve diğer özellikleri desteklemek için diğer arabirimleri uygulayan bir veya daha fazla diğer COM nesneleri. Ayrıca, bir VSPackage belirli kayıt gereksinimleri vardır.