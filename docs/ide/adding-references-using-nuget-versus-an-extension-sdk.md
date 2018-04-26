---
title: Başvuru Eklerken NuGet veya Uzantı SDK Kullanma Karşılaştırması
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 49854e401bdefa4da776f888fff8cff6fdb0d136
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="adding-references-using-nuget-versus-an-extension-sdk"></a>Başvuru eklerken NuGet uzantı SDK ile kullanma

Visual Studio için NuGet uzantısı ya da bir yazılım geliştirme seti (SDK) kullanarak Visual Studio projeleri içinde tüketimi için bir paket sağlayabilirsiniz. İki mekanizma arasındaki farklar ve benzerlikler açıklayarak, bu konuda göreviniz için en iyisi seçmenize yardımcı olabilir.

- NuGet, bir proje çözüme kitaplıkları ekleme işlemini basitleştiren bir açık kaynaklı paket Yönetimi sistemidir. Daha fazla bilgi için bkz: [NuGet belgelerine](/nuget).

- Bir SDK, Visual Studio tek başvuru öğesi olarak davranır dosyaları koleksiyonudur. **Başvuru Yöneticisi** iletişim kutusu, bu iletişim kutusunu görüntülediğinizde, açık olan projeye ilgili tüm SDK'ları listeler. Bir projeye bir SDK eklediğinizde, tüm bu SDK içeriği IntelliSense erişebilirsiniz **araç**, tasarımcıları, **Nesne Tarayıcısı**, MSBuild, hata ayıklama ve paketleme dağıtımı. SDK hakkında daha fazla bilgi için bkz: [bir yazılım geliştirme seti oluşturma](../extensibility/creating-a-software-development-kit.md).

## <a name="which-mechanism-should-i-use"></a>Hangi mekanizması kullanmalıyım?

Aşağıdaki tabloda, bir SDK başvuruda bulunan özellikler NuGet başvuru özellikleri ile karşılaştırmanıza yardımcı olur.

|Özellik|SDK'sı desteği|SDK notları|NuGet desteği|NuGet Notlar|
|-------------|-----------------|---------------|-------------------|-----------------|
|Bir varlık mekanizması başvuruyor ve tüm dosyaları ve işlevsellik sonra kullanılabilir.|Y|Kullanarak bir SDK'sı ekleme **başvuru Yöneticisi** iletişim kutusunda, tüm dosyaları ve işlevselliği geliştirme iş akışı sırasında kullanılabilir.|Y||
|MSBuild otomatik olarak tüketir derlemeler ve Windows Meta veriler (*.winmd*) dosyaları.|Y|SDK başvurularında derleyiciye otomatik olarak geçirilir.|Y||
|MSBuild .h veya .lib dosyaları otomatik olarak kullanır.|Y|*SDKName.props* dosya söyler Visual Studio Visual C++ dizin ve otomatik için belirli bir benzeri nasıl ayarlanacağını *.h* veya *.lib* dosya tüketim.|N||
|MSBuild otomatik olarak tüketir *.js* veya *.css* dosyaları.|Y|İçinde **Çözüm Gezgini**, tek tek göstermek için JavaScript SDK'sı başvurusu düğümünü genişletin *.js* veya *.css* dosyaları ve ardından oluşturmak `<source include/>` sürükleyerek etiketleri Bu dosyaları kaynak dosyalarına. SDK, F5 ve otomatik paketi Kurulum destekler.|Y||
|MSBuild denetimde otomatik olarak ekler **araç**.|Y|**Araç** SDK'ları kullanabilir ve belirttiğiniz sekmeleri denetimlerini göster.|N||
|Mekanizması (VSIX) uzantıları için Visual Studio yükleyicisi destekler.|Y|VSIX özel bildirim ve SDK paketleri oluşturmak için mantığı vardır|Y|VSIX başka bir Kurulum programı'katıştırılabilir.|
|**Nesne Tarayıcısı** başvuruları numaralandırır.|Y|**Nesne Tarayıcısı** otomatik olarak SDK'ları içinde başvuruları listesini alır ve bunları numaralandırır.|N||
|Dosyaları ve bağlantıları otomatik olarak eklenen **başvuru Yöneticisi** iletişim kutusu (Yardım bağlantıları ve benzeri otomatik doldurma)|Y|**Başvuru Yöneticisi** iletişim kutusu Yardım bağlantıları ve SDK bağımlılıkları listesi birlikte SDK'ları, otomatik olarak numaralandırır.|N|NuGet sağlar, kendi **NuGet paketlerini Yönet** iletişim kutusu.|
|Birden fazla mimari düzeneğini destekler.|Y|SDK'ları birden çok yapılandırmayı gönderebilirsiniz. MSBuild her proje yapılandırması için uygun dosyaları kullanır.|N||
|Mekanizması birden çok yapılandırmayı destekler.|Y|SDK'ları birden çok yapılandırmayı gönderebilirsiniz. Proje mimarisine bağlı olarak, uygun dosyaları her proje mimari MSBuild tüketir.|N||
|"Kopyala için." mekanizması belirtebilirsiniz|Y|Dosyaları bırakılan bağlı olarak *\redist* veya *\designtime* klasörü, alıcı uygulamanın pakete kopyalamak için hangi dosyaların denetleyebilirsiniz.|N|Paket bildirimi kopyalamak için hangi dosyaların bildirin.|
|İçerik yerelleştirilmiş dosyalarında görünür.|Y|SDK'ları yerelleştirilmiş XML belgelerini daha iyi tasarım zamanı için bir deneyim otomatik olarak eklenir.|N||
|MSBuild bir SDK'ın birden çok sürümü aynı anda tüketen destekler.|Y|SDK, birden çok sürümü aynı anda tüketen destekler.|N|Bu başvuruda değil. Projenizdeki NuGet dosyaların birden fazla sürümünü aynı anda sahip olamaz.|
|Geçerli hedef çerçeve, Visual Studio sürümleri ve proje türleri belirtme düzeneğini destekler.|Y|**Başvuru Yöneticisi** iletişim kutusu ve **araç** kullanıcıları daha kolay uygun SDK'ları seçebilmeleri projesi için geçerli SDK göster.|Y (kısmi)|Pivot hedef çerçevedir. Hiçbir kullanıcı arabiriminde filtreleme yoktur. Yükleme sırasında bir hata döndürebilir.|
|Mekanizması belirten kayıt bilgileri için yerel WinMDs destekler.|Y|.Winmd dosya ve .dll dosyasına arasındaki bağıntıyı belirtebilirsiniz *SDKManifest.xml*.|N||
|Diğer SDK üzerinde bağımlılıkları belirtme mekanizması destekler.|Y|SDK'sı yalnızca kullanıcıyı uyarır; Kullanıcı hala bunları yüklemeniz ve bunları el ile başvuru gerekir.|Y|NuGet bunları otomatik olarak çeker; kullanıcı bildirimi değil.|
|Mekanizması tümleşir [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)] uygulama bildirimi ve Framework kimliği gibi kavramları|Y|SDK özgü kavramları geçmelidir [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)] kullanılabilir SDK'ları ile paketleme ve F5'ın düzgün çalışması için[!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)].|N||
|Ardışık düzeni için hata ayıklama uygulama mekanizması bütünleşir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar.|Y|SDK geçmelidir [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]-belirli kavramları SDK'ları bulunan ile paketleme ve F5'ın düzgün çalışması için [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)].|Y|NuGet içerik projenin bir parçası haline gelir. Herhangi bir F5 ayrıcalık gereklidir.|
|Mekanizması uygulama bildirimleri ile tümleşir.|Y|SDK geçmelidir [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]-belirli kavramları SDK'ları bulunan ile paketleme ve F5'ın düzgün çalışması için [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)].|Y|NuGet içerik projenin bir parçası haline gelir. Herhangi bir F5 ayrıcalık gereklidir.|
|Başvuru olmayan dosyaları mekanizması dağıtır (örneğin, test çerçevesi, testler alacağı dağıtmak [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamaları).|Y|Dosyaları düşüş *\redist* klasörü, dosyaları otomatik olarak dağıtılır.|Y||
|Mekanizması platform SDK'ları Visual Studio IDE içinde otomatik olarak ekler.|Y|Bıraktığınız varsa [!INCLUDE[win8](../debugger/includes/win8_md.md)] SDK veya belirli bir düzende belirli bir konumda Windows Phone SDK'sı SDK ile Visual Studio özellikleri otomatik olarak tümleşiktir.|N||
|Temiz Geliştirici makine düzeneğini destekler. (Diğer bir deyişle, herhangi bir yükleme gereklidir ve kaynak kodu denetimi basit alımı çalışır.)|N|Bir SDK aldığından, çözümünüz ve SDK ayrı olarak işaretlemeniz gerekir. MSBuild tekrarlanan SDK'ları iki kayıt defteri olmayan varsayılan konumlardan SDK'sındaki kontrol edebilirsiniz (Ayrıntılar için bkz [bir yazılım geliştirme seti oluşturma](../extensibility/creating-a-software-development-kit.md)). Alternatif olarak, özel bir konuma SDK'lar oluşuyorsa proje dosyasında aşağıdaki kodu belirtebilirsiniz:<br /><br /> `<PropertyGroup>    <SDKReferenceDirectoryRoot>C:\MySDKs</SDKReferenceDirectoryRoot>   </PropertyGroup>`<br /><br /> Ardından SDK'ları bu konuma denetleyin.|Y|Çözüm denetleyebilir ve Visual Studio hemen tanır ve dosyalar üzerinde çalışır.|
|Bir paketi yazarları varolan topluluğu büyük birleştirebilirsiniz.|Yok|Yeni bir topluluktur.|Y||
|Bir paket tüketici varolan topluluğu büyük birleştirebilirsiniz.|Yok|Yeni bir topluluktur.|Y||
|Bir (özel galerileri, depoları ve benzeri) iş ortakları ekosistemi birleştirebilirsiniz.|Yok|Visual Studio Market'te, Microsoft Download Center, kullanılabilir depoları içerir ve [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)].|Y||
|Paket oluşturma ve tüketimi için sürekli tümleştirme yapı sunucularıyla mekanizması tümleştirir.|Y|SDK iade edildi konumu (SDKReferenceDirectoryRoot özelliği) için MSBuild komut satırında geçmesi gerekir.|Y||
|Mekanizması her iki paketin kararlı ve yayın öncesi sürümlerini destekler.|Y|SDK ekleyerek başvuruları birden çok sürümü destekler.|Y||
|Otomatik güncelleştirme mekanizması yüklü paketleri destekler.|Y|Sevk VSIX veya Visual Studio Otomatik Güncelleştirmeler'in bir parçası olarak otomatik bildirimler SDK sağlar.|Y||
|Mekanizması bağımsız içeren *.exe* dosyası oluşturma ve paketleri kullanma.|Y|SDK'sı içerir *MSBuild.exe*.|Y||
|Sürüm denetimine paketleri denetlenebilir.|Y|Uzantı SDK'ları yapılmayacağını anlamına gelir Belgeler düğümü dışında bir şey iade edilemez. Uzantı SDK boyutu büyük olabilir.|Y||
|Oluşturma ve paketleri kullanmak için bir PowerShell arabirimi kullanabilirsiniz.|Y (tüketim), N (oluşturma)|Bir SDK oluşturmak için hiçbir araç. Tüketim MSBuild komut satırında yürütüyor.|Y||
|Hata ayıklama desteği için Sembol paketi kullanabilirsiniz.|Y|Bıraktığınız varsa *.pdb* SDK dosyalarında dosyaları toplanma otomatik olarak.|Y||
|Paket Yöneticisi otomatik güncelleştirmeleri düzeneğini destekler.|Yok|SDK ile MSBuild düzenlendi.|Y||
|Basit bir bildirim biçimi düzeneğini destekler.|Y|*SDKManifest.xml* birçok öznitelikleri destekler, ancak küçük bir alt genellikle gereklidir.|Y||
|Mekanizması tüm Visual Studio sürümleri için kullanılabilir.|Y|SDK tüm Visual Studio sürümlerini destekler.|Y|NuGet tüm Visual Studio sürümlerini destekler.|
|Mekanizması tüm proje türleri için kullanılabilir.|N|SDK'yı destekleyen [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] başlayarak uygulamaları [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|N|İzin verilen projelerinin listesini gözden geçirebilirsiniz.|

## <a name="see-also"></a>Ayrıca bkz.

- [Bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md)