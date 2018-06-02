---
title: Visual Studio 2017 Gelişmiş özellikleri
ms.date: 06/01/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e50bd5231387261e56a62234858d10c3806de3dc
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34694119"
---
# <a name="features-of-visual-studio-2017"></a>Visual Studio 2017 özellikleri

[Visual Studio IDE genel bakış](../ide/visual-studio-ide.md) konu Visual Studio için temel bir giriş sağlar. Bu makalede deneyimli geliştiriciler ya da Visual Studio ile bilginiz kişiler için daha uygun olabilir özellikleri açıklar.

## <a name="modular-installation"></a>Modüler yükleme

Visual Studio'nun modüler yükleyici seçin ve yüklemenize olanak sağlar *iş yükleri*, hangi gruplarıdır programlama dili veya tercih ettiğiniz platform için gerekli özellikleri. Bu strateji, yükler ve çok daha hızlı güncelleştirmeleri yüklemesi ayak izinin Visual Studio daha küçük kalmasına yardımcı olur.

Visual Studio 2017 henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

Sisteminizde Visual Studio'yu ayarlama hakkında daha fazla bilgi edinmek için [yükleme Visual Studio 2017](../install/install-visual-studio.md).

## <a name="create-cloud-enabled-apps-for-azure"></a>Azure için bulut özellikli uygulamalar oluşturma

Visual Studio Paketi kolayca Microsoft Azure tarafından desteklenen bulut özellikli uygulamalar oluşturmanıza olanak sağlayan araçlar sunar. Yapılandırın, yapı, hata ayıklama, paket ve uygulamaları ve Hizmetleri IDE doğrudan Microsoft Azure üzerinde dağıtın. Azure araçlarını ve proje şablonları almak için seçin **Azure geliştirme** Visual Studio yüklediğinizde iş yükü.

![Azure geliştirme iş yükü](../data-tools/media/azure-development-workload.png)

Yükledikten sonra **Azure geliştirme** iş yükü, aşağıdaki **bulut** şablonları için C# ' de kullanılabilir **yeni proje** iletişim:

![Visual Studio için bulut proje şablonları](media/cloud-project-templates.png)

Visual Studio'nun [Cloud Explorer](/azure/vs-azure-tools-resources-managing-with-cloud-explorer) görüntülemek ve Visual Studio içinde Azure tabanlı bulut kaynakları yönetmenize olanak tanır. Bu kaynaklar sanal makineler, tablolar, SQL veritabanları ve daha fazlasını içerebilir. **Cloud Explorer** tüm hesapları Azure kaynaklarında yönetilen içine açtığınızdan Azure aboneliği altında gösterir. Ve belirli bir işlemi Azure portalında gerektiriyorsa **Cloud Explorer** portal gidin gereken yer götüren bağlantılar sağlar.

![Visual Studio cloud Explorer'da](media/cloud-explorer.png)

Kullanarak, uygulamaları için Azure services yararlanabilirsiniz **bağlantılı Hizmetler** gibi:

- [Active Directory bağlı hizmet](/azure/active-directory/develop/vs-active-directory-add-connected-service) kullanıcıların kendi hesapları kullanabilmeniz için [Azure Active Directory](/azure/active-directory/active-directory-whatis) web uygulamaları bağlamak için
- [Azure depolama bağlı hizmeti](/azure/vs-azure-tools-connected-services-storage) blob storage'ı, kuyruklar ve tablolar
- [Anahtar kasası bağlı hizmet](/azure/key-vault/vs-key-vault-add-connected-service) web uygulamaları için parolaları yönetmek için

Kullanılabilir **bağlantılı Hizmetler** proje türüne bağlıdır. Nde projeye sağ tıklayarak bir hizmet eklemek **Çözüm Gezgini** ve seçme **Ekle** > **bağlı hizmet**.

![Visual Studio bağlı Hizmetleri](media/connected-services.png)

Daha fazla bilgi için bkz: [ile Visual Studio ve Azure buluta taşımak](https://www.visualstudio.com/vs/azure-tools/).

## <a name="create-apps-for-the-web"></a>Web uygulamaları oluşturma

Bizim modern world web sürücüler ve Visual Studio, uygulamalar için yazmanıza yardımcı olabilir. ASP.NET, Node.js, Python, JavaScript ve TypeScript kullanarak web uygulamaları oluşturabilirsiniz. Visual Studio web çerçeveleri Angular, jQuery, hızlı ve daha fazlası gibi bilir. ASP.NET Core ve .NET Core Windows, Mac ve Linux işletim sistemleri üzerinde çalıştırın. [ASP.NET Core](http://www.asp.net/core/overview) MVC, Webapı ve SignalR için önemli bir güncelleştirme ve Windows, Mac ve Linux üzerinde çalıştırır.  ASP.NET Core sıfırdan yukarı .NET yalın ve birleştirilebilir sizinle modern bulut tabanlı web uygulamaları ve hizmetleri oluşturmak için yığın sağlamak için tasarlanmıştır.

Daha fazla bilgi için bkz: [Modern web araçları](https://www.visualstudio.com/vs/modern-web-tooling/).

## <a name="build-cross-platform-apps-and-games"></a>Platformlar arası uygulamaları ve oyunları derleme

Visual Studio uygulamaları ve oyunları macOS, Linux ve Windows için yanı sıra Android, iOS ve diğer oluşturmak için kullanabileceğiniz [mobil aygıtları](https://www.visualstudio.com/vs/mobile-app-development/).

- Yapı [.NET Core](/dotnet/core/) Windows, macOS ve Linux üzerinde çalışan uygulamalar.

- Kullanarak iOS, Android ve Windows C# ve F # için mobil uygulamalar oluşturma [Xamarin](https://developer.xamarin.com/guides/cross-platform/windows/visual-studio/).

- Standart web teknolojileri kullanan&mdash;HTML, CSS ve JavaScript&mdash;kullanarak iOS, Android ve Windows için mobil uygulamaları oluşturmak için [Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/).

- 2B ve 3B oyunlar C# kullanarak yapı [Unity için Visual Studio Araçları](../cross-platform/visual-studio-tools-for-unity.md).

- Yapı yerel C++ uygulamaları iOS, Android ve Windows cihazları ve Paylaşım ortak kodun kullanarak iOS, Android ve Windows için yerleşik kitaplıklarında [C++ platformlar arası geliştirme için](../cross-platform/visual-cpp-for-cross-platform-mobile-development.md).

- Dağıtma, test ve Android uygulamaları ile hata ayıklama [Android öykünücüsü](../cross-platform/visual-studio-emulator-for-android.md).

## <a name="connect-to-databases"></a>Veritabanlarına bağlanma

**Sunucu Gezgini** göz atın ve SQL Server örnekleri ve varlıkları yerel olarak, uzaktan ve Azure, Salesforce.com, Office 365 ve Web siteleri yönetmenize yardımcı olur. Açmak için **Sunucu Gezgini**, ana menüde seçin **Görünüm** > **Sunucu Gezgini**. Bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md) Sunucu Gezgini kullanma hakkında daha fazla bilgi için.

[SQL Server veri Araçları (SSDT)](/sql/ssdt/download-sql-server-data-tools-ssdt) SQL Server, Azure SQL Database ve Azure SQL Data Warehouse güçlü bir geliştirme ortamı içindir. Yapı, hata ayıklama, korumanıza ve veritabanlarını yeniden düzenlemeniz sağlar. Bir veritabanı proje ile veya doğrudan ile bir bağlı veritabanı örneği veya kapalı-içi çalışabilir.

**SQL Server Nesne Gezgini** Visual Studio veritabanı nesnelerini SQL Server Management Studio'ya benzer bir görünümünü sağlar. SQL Server Nesne Gezgini tablo verileri düzenleme, şemalar karşılaştırma, bağlamsal menülerden sağ SQL Server Nesne Gezgini ve daha fazlasını kullanarak sorguları yürütme dahil olmak üzere açık vergi veritabanı yönetim ve tasarım çalışma yapmanıza olanak sağlar.

![SQL Server Object Explorer](../ide/media/vs2015_sqlobjectexplorer.png)

## <a name="debug-test-and-improve-your-code"></a>Hata ayıklama, test ve kodunuzu geliştirmek

Kodu yazarken, çalıştırmak ve hataları ve performans için test gerekir. Visual Studio'nun modern hata ayıklama sistem projenizdeki yerel veya uzak bir cihaz üzerinde çalışan kodda hata ayıklama sağlayan bir [Aygıt Öykünücüsü](../cross-platform/visual-studio-emulator-for-android.md). Bir seferde bir deyim kod adım adım ve ilerledikçe değişkenleri inceleyin. Belirtilen bir koşul doğru olduğunda, yalnızca isabet kesme noktaları ayarlayabilirsiniz. Böylece kodunuzu çıkmak zorunda değilsiniz tüm kod düzenleyicisinde kendisini yönetilebilir. Visual Studio'da hata ayıklama hakkında daha fazla bilgi edinmek için bkz: [hata ayıklayıcı, özellik Turu](../debugger/debugger-feature-tour.md).

Visual Studio'nun çıkışı checkout uygulamalarınızın performansını artırma hakkında daha fazla bilgi edinmek için [profil](../profiling/profiling-feature-tour.md) özelliği.

İçin [test](../test/improve-code-quality.md), Visual Studio birim testi, Canlı birim testi, Intellitest, yükleme ve performans testi ve daha fazla bilgi sunar. Visual Studio de Gelişmiş [kod çözümleme](../code-quality/code-analysis-for-managed-code-overview.md) tasarım, güvenlik ve diğer türleri açıkları yakalamak için özellikleri.

## <a name="deploy-your-finished-application"></a>Tamamlanmış uygulamanızı dağıtmak

Uygulamanızı kullanıcılara veya müşterilere dağıtmaya hazır olduğunda, bir SharePoint sitesine veya InstallShield veya Windows Installer teknolojileri ile Microsoft Store'a dağıtıyorsunuz olup olmadığını Visual Studio, bunu yapmak için araçlar sağlar. Bu, tüm IDE erişilebilir. Daha fazla bilgi için bkz: [uygulamaları, hizmetleri ve bileşenleri dağıtma](../deployment/deploying-applications-services-and-components.md).

## <a name="manage-your-source-code-and-collaborate-with-others"></a>Kaynak kodunuz yönetmek ve diğer kullanıcılarla işbirliği

Git depoları GitHub dahil olmak üzere tüm sağlayıcı tarafından barındırılan kaynak kodunuzda yönetebilirsiniz. Veya [Visual Studio Team Services (VSTS)](/vsts/index) kod hataları yanında yönetebilir ve iş öğeleri tüm projeniz için. Bkz: [Git ve Team Services (VSTS) kullanmaya başlama](/vsts/git/gitquickstart?tabs=visual-studio) Git depoları Visual Studio Takım Gezgini'ni kullanarak yönetme hakkında daha fazla bilgi edinmek için. Visual Studio ayrıca diğer yerleşik kaynak denetimi özellikleri vardır. Bunları hakkında daha fazla bilgi için bkz: [Visual Studio 2017 (blog)'deki yeni Git Özellikler](https://blogs.msdn.microsoft.com/visualstudioalm/2017/03/06/new-git-features-in-visual-studio-2017/).

Visual Studio Team Services yazılım projelerinin barındırma ve ekip işbirliği etkinleştirmek için bir bulut tabanlı bir hizmettir. VSTS Git ve Team Foundation kaynak denetimi sistemleri gibi Scrum, CMMI ve Çevik Geliştirme yöntemlerini destekler. Team Foundation sürüm denetimi (TFVC'yi) izlemek için bir tek, merkezi bir sunucu havuzu ve sürüm dosyalarını kullanır. Yerel değişiklikleri her zaman diğer geliştiricileri en son değişiklikleri nereden merkezi sunucu denetlenir.

Team Foundation Server (TFS) için Visual Studio uygulama yaşam döngüsü yönetimi hub'ı ' dir. Tek bir çözüm kullanarak katılmayı geliştirme işlemine dahil edilen herkes sağlar. TFS, heterojen takımlar ve projeler, çok yönetmek için yararlıdır.

Ağınızdaki bir Visual Studio Team Services hesabı veya Team Foundation Server varsa üzerinden bağlandığınız **Takım Gezgini** Visual Studio'daki. Bu pencereden kodu ya da kaynak denetiminden kontrol, iş öğelerini yönetmek, derlemeleri ve erişim takım odaları ve çalışma alanları başlatma. Açabilirsiniz **Takım Gezgini** gelen **hızlı başlatma** kutusunda veya ana menüden **Görünüm** > **Takım Gezgini** veya **Takım** > **bağlantılarını yönetme**.

Aşağıdaki resimde gösterildiği **Takım Gezgini** VSTS içinde barındırılan bir çözüm için penceresi.

![Visual Studio Takım Gezgini](../ide/media/vs2017_teamexplorer.png)

Sürüm denetimine takımınızdaki devs denetlediyseniz kodu oluşturmak için derleme süreci otomatik hale getirebilirsiniz. Örneğin, bir veya daha fazla projeleri gecelik veya kod iade her zaman oluşturabilirsiniz. Daha fazla bilgi için bkz: [derleme ve sürüm (VSTS ve TFS)](/vsts/build-release/index).

## <a name="extend-visual-studio"></a>Visual Studio’yu Genişletme

Visual Studio tam işlevsellik ihtiyacınız yoksa, ekleyebilirsiniz! İş akışı ve stil bağlı IDE'yi kişiselleştirme, henüz Visual Studio ile tümleşik harici araçlar için destek eklemek ve verimliliğinizi artırmak için varolan işlevlerini değiştirin. Visual Studio genişletilebilirlik Araçları (VS SDK) en son sürümünü bulmak için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

Kendi kod Çözümleyicileri ve kod oluşturucuları yazmak için .NET derleyici Platformu ("Roslyn") kullanabilirsiniz. Konumundaki ihtiyaç duyduğunuz her şeyi Bul [Roslyn](https://github.com/dotnet/Roslyn).

Bul [varolan uzantıları](https://marketplace.visualstudio.com/vs) Visual Studio geliştirme topluluğumuz yanı sıra Microsoft geliştiriciler tarafından oluşturulmuş.

Visual Studio genişletme hakkında daha fazla bilgi için bkz: [genişletmek Visual Studio IDE](https://www.visualstudio.com/vs/extend/).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio IDE genel bakış](../ide/visual-studio-ide.md)
- [Visual Studio 2017 yenilikler](../ide/whats-new-in-visual-studio.md)