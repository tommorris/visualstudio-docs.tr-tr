---
title: "Visual Studio 2017 genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 02/05/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bb2e7a3dcd800367ab54945cb0c406ce7afcf45a
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="visual-studio-ide-overview"></a>Visual Studio IDE genel bakış

Visual Studio etkileşimli geliştirme ortamı (IDE) bir yaratıcı launching görüntülemek ve kod, neredeyse her türlü düzenleyin ve sonra hata ayıklama, yapı ve Android, iOS, Windows, web ve bulut uygulamaları yayımlamak için kullanabileceğiniz bir ortamdır. Sürümleri Mac ve Windows için kullanılabilir. Bu konu Visual Studio IDE özelliklerini tanıtır. Biz, Visual Studio ile nasıl yüklemek ve kullanmak, basit bir proje oluşturun, işaretçileri hata ayıklama ve dağıtma kodu alın ve çeşitli aracı windows gezin bazı şeyleri adım geçireceğiz.

## <a name="what-can-you-do-with-the-visual-studio-ide"></a>Visual Studio IDE ile neler yapabileceğiniz?

Android telefonla için bir uygulama oluşturmak istiyor musunuz? Bunu yapabilirsiniz. Ne dersiniz C++ kullanarak modern oyun oluşturulsun mu? Bunu çok yapabilirsiniz ve çok, çok fazla. Visual Studio Yardım eden şablonlar sağlar Web siteleri, oyunlar, Masaüstü uygulamaları, mobil uygulamalar, Office için uygulamalar ve daha fazlasını yapın.

![Visual Studio projeleri](../ide/media/VSIDE_Tour_Projects_List.png)

Veya, neredeyse her yerden alın ve çalışma almak biraz kod açabilirler. Bir proje istediğiniz Github'da görüyor musunuz? Yalnızca depoyu kopyalayın, Visual Studio'da açın ve kod yazmaya başlayın!

### <a name="create-mobile-apps"></a>Mobil uygulamaları oluşturma

C# ve Xamarin veya Visual C++ kullanarak farklı platformlar için yerel mobil uygulamalar veya JavaScript Apache Cordova ile kullanarak karma uygulamalar oluşturabilirsiniz. Unity, gerçekleşmemiş hesabı, DirectX, Cocos ve daha fazla bilgi için mobil oyunlar yazabilirsiniz. Visual Studio çalıştırın ve Android uygulamalarını hata ayıklamaya yardımcı olması için Android öykünücüsünde içerir.

Azure uygulama hizmetleri oluşturarak mobil uygulamalarınız için bulut gücünü yararlanabilirsiniz. Azure uygulama hizmetleri, uygulamalarınızı bulutta verileri depolamak, güvenli bir şekilde kullanıcıların kimliklerini doğrulamak ve otomatik olarak kaynaklarını ölçeği veya uygulamanızın ve işinizin gereksinimlerini karşılamak için aşağı üzere etkinleştirin. Daha fazla bilgi için bkz: [mobil uygulama geliştirme](https://www.visualstudio.com/vs/mobile-app-development/).

### <a name="create-cloud-apps-for-azure"></a>Azure için bulut uygulamaları oluşturma

Visual Studio Paketi kolayca Microsoft Azure tarafından desteklenen bulut özellikli uygulamalar oluşturmanıza olanak sağlayan araçlar sunar. Yapılandırın, yapı, hata ayıklama, paket ve uygulamaları ve Hizmetleri IDE doğrudan Microsoft Azure üzerinde dağıtın. .NET için Azure Araçları almak için seçin **Azure geliştirme** Visual Studio yüklediğinizde iş yükü. Daha fazla bilgi için bkz: [Azure için Visual Studio Araçları](https://www.visualstudio.com/vs/azure-tools/).

Bağlantılı Hizmetler gibi kullanarak, uygulamaları için Azure services yararlanabilirsiniz:

- [Azure mobil hizmetler](http://azure.microsoft.com/documentation/services/mobile-services/)

- [Azure Depolama](http://azure.microsoft.com/documentation/services/storage/)

[HockeyApp](https://www.visualstudio.com/hockey-app/) beta sürümlerini dağıtmak, Canlı çökme raporlarını toplar ve gerçek kullanıcılardan geri bildirim alma yardımcı olur. Ayrıca, Office 365 REST API'leri bulutta depolanan veriler bağlanmak için kendi uygulamanızı içine tümleştirebilirsiniz. Daha fazla bilgi için bkz: [bu GitHub örnekleri](https://github.com/OfficeDev/?utf8=%E2%9C%93&query=o365).

[Application Insights](https://marketplace.visualstudio.com/items?itemName=VisualStudioOnlineApplicationInsights.application-insights) algılamak ve uygulamalarınızı Kalite sorunlarını tanılamak ve web hizmetlerini yardımcı olur. Application Insights da yardımcı olur, kullanıcı deneyimini iyileştirmek için kullanıcılarınızın gerçekte ile uygulamanızı ne anlama.

### <a name="create-apps-for-the-web"></a>Web uygulamaları oluşturma

Bizim modern world web sürücüler ve Visual Studio, uygulamalar için yazmanıza yardımcı olabilir. ASP.NET, Node.js, Python, JavaScript ve TypeScript kullanarak web uygulamaları oluşturabilirsiniz. Visual Studio web çerçeveleri Angular, jQuery, hızlı ve daha fazlası gibi bilir. ASP.NET Core ve .NET Core Windows, Mac ve Linux işletim sistemleri üzerinde çalıştırın. [ASP.NET Core](http://www.asp.net/core/overview) MVC, Webapı ve SignalR için önemli bir güncelleştirme ve Windows, Mac ve Linux üzerinde çalıştırır.  ASP.NET Core sıfırdan yukarı .NET yalın ve birleştirilebilir sizinle modern bulut tabanlı web uygulamaları ve hizmetleri oluşturmak için yığın sağlamak için tasarlanmıştır.

Daha fazla bilgi için bkz: [Modern Web Tooling](https://www.visualstudio.com/vs/modern-web-tooling/).

### <a name="build-cross-platform-apps-and-games"></a>Platformlar arası uygulamaları ve oyunları derleme

Visual Studio, uygulamaları ve oyunları macOS, Linux ve Windows için yanı sıra Android, iOS ve diğer mobil cihazlar için oluşturmak için kullanabilirsiniz.

- Yapı [.NET Core](/dotnet/core/) Windows, macOS ve Linux üzerinde çalışan uygulamalar.

- Kullanarak iOS, Android ve Windows C# ve F # için mobil uygulamalar oluşturma [Xamarin](https://developer.xamarin.com/guides/cross-platform/windows/visual-studio/).

- Standart web teknolojileri kullanan&mdash;HTML, CSS ve JavaScript&mdash;kullanarak iOS, Android ve Windows için mobil uygulamaları oluşturmak için [Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/).

- 2B ve 3B oyunlar C# kullanarak yapı [Unity için Visual Studio Araçları](../cross-platform/visual-studio-tools-for-unity.md).

- Yapı yerel C++ uygulamaları iOS, Android ve Windows cihazları ve Paylaşım ortak kodun kullanarak iOS, Android ve Windows için yerleşik kitaplıklarında [C++ platformlar arası geliştirme için](../cross-platform/visual-cpp-for-cross-platform-mobile-development.md).

- Dağıtma, test ve Android uygulamaları ile hata ayıklama [Android öykünücüsü](../cross-platform/visual-studio-emulator-for-android.md).

Visual Studio yapabilir Yardım pek çok şey daha yapın. Daha kapsamlı bir liste için bkz: [www.visualstudio.com](https://www.visualstudio.com/vs/).

## <a name="install-the-visual-studio-ide"></a>Visual Studio IDE yükleyin

Başlamak için Visual Studio indirin ve sisteminizde yükleyin. Adresinden indirebilirsiniz [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).

Visual Studio zamankinden daha basit sunulmuştur. Modüler yükleyici seçin ve yüklemenize olanak sağlayan *iş yükleri*, hangi gruplarıdır programlama dili veya tercih ettiğiniz platform için gerekli özellikleri. Bu strateji, yükler ve çok daha hızlı güncelleştirmeleri yüklemesi ayak izinin Visual Studio zamankinden daha, daha küçük tutmaya yardımcı olur. Geliştirilmiş yükleme performansını yanı sıra, Visual Studio 2017 kısa IDE başlatma ve kez yük çözümü vardır.

Sisteminizde Visual Studio'yu ayarlama hakkında daha fazla bilgi edinmek için [yükleme Visual Studio 2017](../install/install-visual-studio.md). İçin adımları izlemeniz [bir program oluşturmak](#create-a-program), seçtiğinizden emin olun **.NET Core platformlar arası geliştirme** yükleme sırasında iş yükü.

![Visual Studio yükleyicisi](../ide/media/overview-net-core-workload.png)

## <a name="sign-in"></a>Oturum Aç

Visual Studio ilk kez başlattığınızda, isteğe bağlı olarak Microsoft hesabınızı veya iş kullanarak oturum açın veya Okul hesabı. İmzalı birden çok cihazda pencere düzenlerini gibi Visual Studio ayarları senkronize olanak sağlar. Ayrıca, otomatik olarak ihtiyacınız olabilecek, Azure abonelikleri gibi hizmetleri bağlanır ve [Visual Studio Team Services](/vsts/).

## <a name="create-a-program"></a>Bir program oluşturun

Bir konu hakkında bilgi edinmek için bir iyi kullanılacağını yoludur! Şimdi daha yakından inceleyin ve yeni, basit bir program oluşturun.

1. Visual Studio'yu açın. Menüsünde, **dosya** > **yeni** > **proje...** .

  ![Dosya > Yeni Proje menü çubuğunda](../ide/media/VSIDE_Tour_NewProject1.png)

1. **Yeni proje** iletişim kutusu birkaç proje şablonları gösterir. Seçin **.NET Core** kategorisi altında **Visual C#**ve ardından **konsol uygulaması (.NET Core)** şablonu. İçinde **adı** metin kutusuna, "HelloWorld" yazın. Seçin **Tamam** düğmesi.

  ![.NET core uygulama şablonu](../ide/media/overview-new-project-dialog.png)

  > [!NOTE]
  > Görmüyorsanız, **.NET Core** kategorisi, yüklemeniz gereken **.NET Core platformlar arası geliştirme** iş yükü. Bunu yapmak için seçin **açık Visual Studio yükleyicisi** alt sol tarafındaki bağlantı **yeni proje** iletişim. Sonra **Visual Studio yükleyicisi** açar, aşağı kaydırın ve seçin **.NET Core platformlar arası geliştirme** iş yükü ve ardından **Değiştir**.

   Visual Studio projenizi oluşturmak için şablon kullanır. Çağıran basit bir "Hello World" uygulaması olan <xref:System.Console.WriteLine> değişmez değer dize "Hello World!" görüntülenecek yöntemi Konsol penceresinde.

1. Kısa bir süre sonra aşağıdaki ekran görüntüsüne benzer bir şey görmeniz gerekir:

  ![Visual Studio IDE](../ide/media/overview-ide-console-app.png)

   Uygulamanız için C# kod alanı çoğunu alır Düzenleyicisi penceresinde gösterilir. Kod, anahtar sözcükleri ve türleri gibi farklı türlerde belirtmek için kod sözdizimini otomatik olarak renklendirilen dikkat edin. Ayrıca, hangi küme ayraçları birbiriyle eşleşen kodda küçük, dikey kesikli satırlar belirtmek ve kodu daha sonra bulun Yardım satır numaraları. Daraltma veya kod genişletmek için küçük, paketlenmiş eksi işareti seçebilirsiniz. Anahat oluşturma özelliği bu kod, ekranda dağınıklığı en aza indirmek için yardımcı olma, gerekmeyen kod gizleme olanak sağlar.

   Proje dosyaları olarak adlandırılan bir penceresinde sağ tarafta listelenen **Çözüm Gezgini**.

  ![Visual Studio IDE kırmızı kutuları](../ide/media/overview-ide-console-app-red-boxes.png)

  Diğer menüleri ve araç pencereleri kullanılabilir olduğundan, ancak şimdi taşımanız şimdilik.

1. Şimdi, uygulamayı başlatın. Bunu seçerek yapmak **hata ayıklama olmadan Başlat** gelen **hata ayıklama** menü çubuğundaki menüsü. Tuşlarına da basabilirsiniz **Ctrl**+**F5**.

  ![Hata ayıklama > Başlat menüsü hata ayıklama olmadan](../ide/media/overview-start-without-debugging.png)

  Visual Studio uygulaması oluşturur ve "Hello World!" iletisiyle bir konsol penceresi açar. Artık çalışan bir uygulamanın sahip!

  ![Konsol penceresi](../ide/media/overview-console-window.png)

1. Konsol penceresini kapatmak için klavyenizde herhangi bir tuşa basın.

1. Uygulama için bazı ek kod ekleyelim. Aşağıdaki C# kodu yazan satırı önce ekleyin `Console.WriteLine("Hello World!");`:

   ```csharp
   Console.WriteLine("\nWhat is your name?");
   var name = Console.ReadLine();
   ```

   Bu kodu ", adı nedir?" görüntüler Konsol penceresinde ve bazı metin kullanıcı girene kadar bekler ve ardından **Enter** anahtarı.

1. Şimdi yazan satırı değiştirmek `Console.WriteLine("Hello World!");` aşağıdaki kodu için:

   ```csharp
   Console.WriteLine($"\nHello {name}!");
   ```

1. Seçerek uygulamayı yeniden çalıştırın **hata ayıklama** > **hata ayıklama olmadan Başlat** basarak veya **Ctrl**+**F5**.

   Visual Studio uygulama yeniden oluşturur ve bir konsol penceresi açar ve için adınızı ister.

1. Konsol penceresi ve tuşuna adınızı girin **Enter**.

   ![Konsol penceresinde giriş](media/overview-console-input.png)

1. Konsol penceresini kapatmak için herhangi bir tuşa basın.

## <a name="debug-test-and-improve-your-code"></a>Hata ayıklama, test ve kodunuzu geliştirmek

Hiçbir şey mükemmel her zaman çalışır. Kodu yazarken, çalıştırmak ve hataları ve performans için test gerekir. Sistem hata ayıklama Visual Studio'nun modern projenizdeki yerel, uzak bir aygıt veya bir öykünücü gibi çalışan kodda hata ayıklama olanak tanır [Android cihazlar için bir](../cross-platform/visual-studio-emulator-for-android.md). Bir seferde bir deyim kod adım adım ve ilerledikçe değişkenleri inceleyin. Belirtilen bir koşul doğru olduğunda, yalnızca isabet kesme noktaları ayarlayabilirsiniz. Kod çalıştırır ve daha fazlasını olarak değişkenlerin değerleri izleyebilirsiniz. Böylece kodunuzu çıkmak zorunda değilsiniz tüm kod düzenleyicisinde kendisini yönetilebilir. Visual Studio'da hata ayıklama hakkında daha fazla bilgi edinmek için bkz: [hata ayıklayıcı, özellik Turu](../debugger/debugger-feature-tour.md).

Test etmek için Visual Studio birim testi, Intellitest, yükleme ve performans testi ve daha fazla bilgi sunar. Test etme hakkında daha fazla bilgi için bkz: [araçları ve senaryoları test](../test/developer-testing-scenarios.md). Uygulamalarınızın performansını artırma hakkında daha fazla bilgi için bkz: [özelliği turu profil](../profiling/profiling-feature-tour.md).

## <a name="deploy-your-finished-application"></a>Tamamlanmış uygulamanızı dağıtmak

Uygulamanızı kullanıcılara veya müşterilere dağıtmaya hazır olduğunda, bir SharePoint sitesine veya InstallShield veya Windows Installer teknolojileri ile Microsoft Store'a dağıtıyorsunuz olup olmadığını Visual Studio, bunu yapmak için araçlar sağlar. Bu, tüm IDE erişilebilir. Daha fazla bilgi için bkz: [uygulamaları, hizmetleri ve bileşenleri dağıtma](../deployment/deploying-applications-services-and-components.md).

## <a name="quick-tour-of-the-ide"></a>IDE hızlı turu

Visual Studio üst düzey bir görsel özeti vermek için büyük olasılıkla kullanacağınız birkaç anahtar aracı windows ile birlikte açık bir proje ile Visual Studio aşağıdaki görüntüde gösterir:

- [Çözüm Gezgini](../ide/solutions-and-projects-in-visual-studio.md) görüntülemek, gidin ve kod dosyalarınızın yönetmenize olanak tanır. Çözüm Gezgini, çözümler ve projeler gruplandırarak kodunuzu düzenlemenize yardımcı olur.

- [Düzenleyicisi](../ide/writing-code-in-the-code-and-text-editor.md) penceresinde, burada olasılıkla harcadığınız zamanınızın çoğunu, kodunuzu gösterir ve kaynak kodu düzenlemek ve bir kullanıcı Arabirimi tasarım sağlar.

- [Çıkış](../ide/reference/output-window.md) penceredir burada Visual Studio hata ayıklama ve hata iletileri, derleyici uyarıları, yayımlama durum iletilerini ve daha fazlası gibi kendi bildirimleri gönderir. Her ileti kaynağı kendi sekmesi vardır.

- [Takım Gezgini (VSTS)](/vsts/user-guide/work-team-explorer) izlemenize olanak tanır iş öğeleri ve paylaşma kod başkalarıyla sürüm denetimi teknolojileri kullanılarak [Git](https://git-scm.com/) ve [Team Foundation sürüm denetimi (TFVC'yi)](/vsts/tfvc/overview).

- [Cloud Explorer](/azure/vs-azure-tools-resources-managing-with-cloud-explorer) görüntülemek ve sanal makineler, tablolar, SQL veritabanları ve daha fazlasını gibi Azure kaynaklarınızı yönetmenize olanak tanır. Belirli bir işlemi Azure portalında gerektiriyorsa, bulut Gezgini gitmeniz gerekir Azure portalında yere götüren bağlantılar sağlar.

![The Visual Studio IDE](../ide/media/visualstudioide.png)

Bazı diğer ortak üretkenlik Visual Studio özellikleri şunlardır:

- [Hızlı başlatma](../ide/reference/quick-launch-environment-options-dialog-box.md) arama kutusudur Visual Studio'da gerekenler hızla bulmak için kullanışlı bir yoludur. Ne olursa olsun, aradığınız adına girmeye hemen başlamak ve Visual Studio tam olarak gitmek istediğiniz yere ele sonuçları listeler. Hızlı Başlatma ayrıca herhangi bir iş yükü veya tek tek bileşen için Visual Studio Yükleyicisi'ni başlatın bağlantılarını gösterir.

  ![Hızlı Başlatma arama kutusu](../ide/media/VSIDE_Tour_QuickLaunch.png)

- [Yeniden düzenleme](../ide/refactoring-in-visual-studio.md) akıllı taşıma değişkenler, yeniden adlandırma kod satırları başka konumlara, sipariş işlev parametrelerini ve daha fazla bilgi için kod taşıma ayrı bir işleve seçilen. gibi işlemleri içerir.

 ![Yeniden Düzenle](../ide/media/VSIDE_refactor.png)

- **IntelliSense** bir genel doğrudan Düzenleyicisi'nde kodunuzu tür bilgilerini görüntüleme ve bazı durumlarda, kod küçük BITS sizin için yazma popüler özellikler kümesi için bir terimdir. Bu ayrı Yardım penceresinde türü bilgileri aramak gereğini ortadan kaldırır düzenleyicisinde temel belgelere satır içi olması gibi olur. IntelliSense özellikleri dile göre farklılık gösterir. Daha fazla bilgi için bkz: [C# IntelliSense](../ide/visual-csharp-intellisense.md), [Visual C++ IntelliSense](../ide/visual-cpp-intellisense.md), [JavaScript IntelliSense](../ide/javascript-intellisense.md), ve [Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md). Aşağıdaki çizimde, İşte bazı IntelliSense özellikleri gösterir:

  ![Visual Studio üye listesi](../ide/media/vs2017_Intellisense.png)

- **Dalgalı çizgiler** yazarken, hatalar veya olası sorunları kodunuzda gerçek zamanlı uyarı kırmızı dalgalı şunlardır. Derleme sırasında bulunan veya çalışma zamanı hatası için beklenmeden hemen sorunu çözmek sağlar. Dalgalı getirirseniz, hatayla ilgili ek bilgileri görürsünüz. Bir ampul de hatayı gidermeye yönelik öneriler ile sol kenar boşluğunda görünebilir. Daha fazla bilgi için bkz: [hızlı Eylemler](../ide/quick-actions.md).

 ![Dalgalı çizgiler](../ide/media/vs2017_squiggle.png)

- [Çağrı hiyerarşisi](../ide/reference/call-hierarchy.md) penceresi çağırın ve, tarafından çağrılan yöntemleri göstermek için metin düzenleyicisi bağlam menüsünden açılabilir yöntemi şapka (ekleme noktasını) altında.

 ![Çağrı hiyerarşisi penceresi](../ide/media/VSIDE_call_hierarchy.png)

- [CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md) , değişiklikleri kod, bağlantılı hatalar, iş öğelerini, kod gözden geçirme ve birim testleri için tüm düzenleyiciden ayrılmadan ve başvurular bulmanızı sağlar.

 ![CodeLens](../ide/media/codelensoverview.png)

- [Tanımına Peek](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) penceresi çıktığınızda geçerli bağlamı gitmeden bir metot veya tür tanımı satır içi gösterir.

 ![Tanımına Gözat](../ide/media/VSIDE_peek_definition.png)

- **Tanıma Git** bağlam menüsü seçeneğini doğrudan burada işlevi veya nesne tanımlanmış yer alır. Diğer Gezinti komutları de Düzenleyicisi'nde sağ tıklayarak kullanılabilir.

 ![Tanıma gitme](../ide/media/VSIDE_go_to_definition.png)

## <a name="manage-your-source-code-and-collaborate-with-others"></a>Kaynak kodunuz yönetmek ve diğer kullanıcılarla işbirliği

Git depoları GitHub dahil olmak üzere tüm sağlayıcı tarafından barındırılan kaynak kodunuzda yönetebilirsiniz. Veya [Visual Studio Team Services (VSTS)](/vsts/index) kod hataları yanında yönetebilir ve iş öğeleri tüm projeniz için. Bkz: [Git ve Team Services (VSTS) ile çalışmaya başlama](/vsts/git/gitquickstart?tabs=visual-studio) Git depoları Visual Studio Takım Gezgini'ni kullanarak yönetme hakkında daha fazla bilgi edinmek için. Visual Studio ayrıca diğer yerleşik kaynak denetimi özellikleri vardır. Bunları hakkında daha fazla bilgi için bkz: [Visual Studio 2017 (blog) yeni Git özellikleri](https://blogs.msdn.microsoft.com/visualstudioalm/2017/03/06/new-git-features-in-visual-studio-2017/).

Visual Studio Team Services yazılım projelerinin barındırma ve ekip işbirliği etkinleştirmek için bir bulut tabanlı bir hizmettir. VSTS Git ve Team Foundation kaynak denetimi sistemleri gibi Scrum, CMMI ve Çevik Geliştirme yöntemlerini destekler. Team Foundation sürüm denetimi (TFVC'yi) izlemek için bir tek, merkezi bir sunucu havuzu ve sürüm dosyalarını kullanır. Yerel değişiklikleri her zaman diğer geliştiricileri en son değişiklikleri nereden merkezi sunucu denetlenir.

Team Foundation Server (TFS) için Visual Studio uygulama yaşam döngüsü yönetimi hub'ı ' dir. Tek bir çözüm kullanarak katılmayı geliştirme işlemine dahil edilen herkes sağlar. TFS, heterojen takımlar ve projeler, çok yönetmek için yararlıdır.

Ağınızdaki bir Visual Studio Team Services hesabı veya Team Foundation Server varsa için Visual Studio Takım Gezgini penceresinde aracılığıyla bağlayın. Bu pencereden kodu ya da kaynak denetiminden kontrol, iş öğelerini yönetmek, derlemeleri ve erişim takım odaları ve çalışma alanları başlatma. Takım Gezgini'nden açabilirsiniz **hızlı başlatma** kutusunda veya ana menüden **görünüm, Takım Gezgini** veya **takım, bağlantılarını yönet**.

Aşağıdaki resimde VSTS içinde barındırılan bir çözüm için Takım Gezgini penceresi gösterir.

![Visual Studio Team Explorer](../ide/media/vs2017_teamexplorer.png)

Sürüm denetimine takımınızdaki devs denetlediyseniz kodu oluşturmak için derleme süreci otomatik hale getirebilirsiniz. Örneğin, bir veya daha fazla projeleri gecelik veya kod iade her zaman oluşturabilirsiniz. Daha fazla bilgi için bkz: [derleme ve sürüm (VSTS ve TFS)](/vsts/build-release/index).

## <a name="connect-to-services-databases-and-cloud-based-resources"></a>Hizmetleri, veritabanları ve bulut tabanlı kaynaklara bağlanma

Bulut bugünün çevrimiçi dünya için kritik öneme sahiptir ve Visual Studio bundan faydalanabilir bulunmasını sağlar. Örneğin, bağlantılı hizmetler özelliği uygulamanızı hizmetlerine bağlanmak sağlar. Uygulamalarınızı, başka şeylerin Azure depolama verilerini depolamak için kullanabilirsiniz.

![Bağlı hizmetler](../ide/media/VSIDE_Tour_Connected_Services.png)

Üzerinde bir hizmet seçme **bağlantılı Hizmetler** bir bağlı Hizmetleri projenizi yapılandıran Sihirbazı başlatılır ve yüklemeleri başlamanıza yardım etmek için gerekli NuGet paketlerini çalışmaya karşı hizmet kodlama.

Görüntüleyebilir ve Visual Studio kullanarak içinde bulut tabanlı Azure kaynaklarınızı yönetmek [Cloud Explorer](/azure/vs-azure-tools-resources-managing-with-cloud-explorer). Cloud Explorer oturum açtığınız Azure aboneliği altında yönetilen tüm hesapları Azure kaynaklarını gösterir. Cloud Explorer seçerek alabileceğiniz **Azure geliştirme** Visual Studio yükleyicisi iş yükü.

![Cloud Explorer](../ide/media/VSIDE_CloudExplorer.png)

**Sunucu Gezgini** göz atın ve SQL Server örnekleri ve varlıkları yerel olarak, uzaktan ve Azure, Salesforce.com, Office 365 ve Web siteleri yönetmenize yardımcı olur. Ana menüde sunucu Gezgini'ni açmak için seçin **Görünüm** > **Sunucu Gezgini**. Bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md) Sunucu Gezgini kullanma hakkında daha fazla bilgi için.

[SQL Server veri Araçları (SSDT)](/sql/ssdt/download-sql-server-data-tools-ssdt) SQL Server, Azure SQL Database ve Azure SQL Data Warehouse güçlü bir geliştirme ortamı içindir. Yapı, hata ayıklama, korumanıza ve veritabanlarını yeniden düzenlemeniz sağlar. Bir veritabanı proje ile veya doğrudan ile bir bağlı veritabanı örneği veya kapalı-içi çalışabilir.

**SQL Server Nesne Gezgini** Visual Studio veritabanı nesnelerini SQL Server Management Studio'ya benzer bir görünümünü sağlar. SQL Server Nesne Gezgini tablo verileri düzenleme, şemalar karşılaştırma, bağlamsal menülerden sağ SQL Server Nesne Gezgini ve daha fazlasını kullanarak sorguları yürütme dahil olmak üzere açık vergi veritabanı yönetim ve tasarım çalışma yapmanıza olanak sağlar.

![SQL Server Object Explorer](../ide/media/vs2015_sqlobjectexplorer.png)

## <a name="extend-visual-studio"></a>Visual Studio’yu Genişletme

Visual Studio tam işlevsellik ihtiyacınız yoksa, ekleyebilirsiniz! İş akışı ve stil bağlı IDE'yi kişiselleştirme, henüz Visual Studio ile tümleşik harici araçlar için destek eklemek ve verimliliğinizi artırmak için varolan işlevlerini değiştirin. Visual Studio genişletilebilirlik Araçları (VS SDK) en son sürümünü bulmak için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

Kendi kod Çözümleyicileri ve kod oluşturucuları yazmak için .NET derleyici Platformu ("Roslyn") kullanabilirsiniz. Konumundaki ihtiyaç duyduğunuz her şeyi Bul [Roslyn](https://github.com/dotnet/Roslyn).

Bul [varolan uzantıları](https://marketplace.visualstudio.com/vs) Visual Studio geliştirme topluluğumuz yanı sıra Microsoft geliştiriciler tarafından oluşturulmuş.

Visual Studio genişletme hakkında daha fazla bilgi için bkz: [genişletmek Visual Studio IDE](https://www.visualstudio.com/vs/extend/).

## <a name="learn-more-and-find-out-whats-new"></a>Daha fazla bilgi edinin ve yeni Bul

Visual Studio önce hiç kullanmadıysanız bakmak [alma başlatıldı geliştirme ile Visual Studio](../ide/get-started-developing-with-visual-studio.md), veya kullanılabilir ücretsiz Visual Studio kurslara kullanıma [Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!index=2&lang=1033). Visual Studio 2017'deki yeni özelliklerin kullanıma istiyorsanız, bkz: [Visual Studio 2017'de](../ide/whats-new-in-visual-studio.md).

Visual Studio IDE turu tamamladıktan Tebrikler! Bazı ana özellikleri hakkında yararlı bir şey öğrenilen umuyoruz.

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio IDE](https://www.visualstudio.com/vs/)
* [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/)
* [Visual Studio Web günlüğü](https://blogs.msdn.microsoft.com/visualstudio/)
* [Visual Studio forumları](https://social.msdn.microsoft.com/Forums/vstudio/home?category=visualstudio%2Cvsarch%2Cvsdbg%2Cvstest%2Cvstfs%2Cvsdata%2Cvsappdev%2Cvisualbasic%2Cvisualcsharp%2Cvisualc)
* [Microsoft Virtual Academy](https://mva.microsoft.com/)