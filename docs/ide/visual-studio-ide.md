---
title: Visual Studio 2017 genel bakış
ms.date: 06/01/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- MSDNSTART
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a7667cac2a26a3e98d2e92dfeb13cee36d870e9
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691166"
---
# <a name="visual-studio-ide-overview"></a>Visual Studio IDE genel bakış

Visual Studio etkileşimli geliştirme ortamı (IDE) bir yaratıcı launching görüntülemek ve kod, düzenlemek ve ardından hata ayıklama, yapı ve bir uygulamayı yayımlamak için kullanabileceğiniz bir ortamdır.

Visual Studio, Windows ve Mac için kullanılabilir [Mac için Visual Studio](/visualstudio/mac/) Visual Studio 2017 aynı özelliklerinin çoğu vardır ve platformlar arası ve mobil uygulamalar geliştirmek için optimize edilmiştir.

Bu makalede Windows için Visual Studio 2017 odaklanır. IDE temel özellikleri sunar. Visual Studio ile yapabileceğiniz bazı şeyleri size rehberlik basit bir proje oluşturma, IntelliSense kodlama Yardımı olarak kullanma ve bir uygulama program yürütme sırasında bir değişkenin değerini görmek için hata ayıklama dahil. Biz de çeşitli aracı windows gezin.

## <a name="install-the-visual-studio-ide"></a>Visual Studio IDE yükleyin

Başlamak için [Visual Studio 2017 karşıdan](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ve sisteminizde yükleyin.

Modüler yükleyici seçin ve yüklemenize olanak sağlayan *iş yükleri*, hangi gruplarıdır programlama dili veya tercih ettiğiniz platform için gerekli özellikleri. İçin adımları izlemeniz [bir program oluşturmak](#create-a-program), seçtiğinizden emin olun **.NET Core platformlar arası geliştirme** yükleme sırasında iş yükü. Hızlı Başlangıç konuları gibi [Visual Studio'da C++ kullanmaya başlama](getting-started-with-cpp-in-visual-studio.md), diğer iş yüklerini yüklemek için yönergeleri içerir.

![Visual Studio Yükleyicisi](../ide/media/overview-net-core-workload.png)

Visual Studio ilk kez başlattığınızda, isteğe bağlı olarak Microsoft hesabınızı veya iş kullanarak oturum açın veya Okul hesabı.

## <a name="tour-of-the-ide"></a>IDE turu

Visual Studio üst düzey bir görsel özeti vermek için büyük olasılıkla kullanacağınız birkaç anahtar aracı windows ile birlikte açık bir proje ile Visual Studio aşağıdaki görüntüde gösterir:

![Visual Studio IDE](../ide/media/visualstudioide.png)

- [Çözüm Gezgini](../ide/solutions-and-projects-in-visual-studio.md) görüntülemek, gidin ve kod dosyalarınızın yönetmenize olanak tanır. Çözüm Gezgini, çözümler ve projeler gruplandırarak kodunuzu düzenlemenize yardımcı olur.

- [Düzenleyicisi](../ide/writing-code-in-the-code-and-text-editor.md) penceresinde, burada olasılıkla harcadığınız zamanınızın çoğunu, kodunuzu gösterir ve kaynak kodu düzenlemek ve bir kullanıcı Arabirimi tasarım sağlar.

- [Çıktı penceresi](../ide/reference/output-window.md) burada Visual Studio hata ayıklama ve hata iletileri, derleyici uyarıları, yayımlama durum iletilerini ve daha fazlası gibi kendi bildirimleri gönderen olduğu. Her ileti kaynağı kendi sekmesi vardır.

- [Takım Gezgini (VSTS)](/vsts/user-guide/work-team-explorer) izlemenize olanak tanır iş öğeleri ve paylaşma kod başkalarıyla sürüm denetimi teknolojileri kullanılarak [Git](https://git-scm.com/) ve [Team Foundation sürüm denetimi (TFVC'yi)](/vsts/tfvc/overview).

Visual Studio bazı diğer popüler üretkenlik özellikleri şunlardır:

- [Yeniden düzenleme](../ide/refactoring-in-visual-studio.md) akıllı taşıma değişkenler, yeniden adlandırma kod satırları başka konumlara, sipariş işlev parametrelerini ve daha fazla bilgi için kod taşıma ayrı bir işleve seçilen. gibi işlemleri içerir.

   ![Yeniden Düzenle](../ide/media/VSIDE_refactor.png)

- [IntelliSense](../ide/using-intellisense.md) bir genel doğrudan Düzenleyicisi'nde kodunuzu tür bilgilerini görüntüleme ve bazı durumlarda, kod küçük BITS sizin için yazma popüler özellikler kümesi için bir terimdir. Bu ayrı Yardım penceresinde türü bilgileri aramak gereğini ortadan kaldırır düzenleyicisinde temel belgelere satır içi olması gibi olur. IntelliSense özellikleri dile göre farklılık gösterir. Daha fazla bilgi için bkz: [C# IntelliSense](../ide/visual-csharp-intellisense.md), [Visual C++ IntelliSense](../ide/visual-cpp-intellisense.md), [JavaScript IntelliSense](../ide/javascript-intellisense.md), ve [Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md). Aşağıdaki çizimde, İşte bazı IntelliSense özellikleri gösterir:

   ![Visual Studio üye listesi](../ide/media/vs2017_Intellisense.png)

- [Hızlı başlatma](../ide/reference/quick-launch-environment-options-dialog-box.md) arama kutusudur Visual Studio'da gerekenler hızla bulmak için kullanışlı bir yoludur. Ne olursa olsun, aradığınız adını yazmaya başlayın ve Visual Studio tam olarak gitmek istediğiniz yere ele sonuçları listeler. **Hızlı başlatma** de gösterir bağlantılar başlayan **Visual Studio yükleyicisi** herhangi bir iş yükü veya tek tek bileşen için.

   ![Hızlı Başlatma arama kutusu](../ide/media/VSIDE_Tour_QuickLaunch.png)

- **Dalgalı çizgiler** yazarken, hatalar veya olası sorunları kodunuzda gerçek zamanlı uyarı dalgalı alt çizgiler şunlardır. Derleme sırasında bulunan veya çalışma zamanı hatası için beklenmeden hemen sorunu çözmek sağlar. Dalgalı getirirseniz, hatayla ilgili ek bilgileri görürsünüz. Bir ampul de hatayı düzeltmek için Eylemler ile sol kenar boşluğunda görünebilir. Daha fazla bilgi için bkz: [hızlı Eylemler](../ide/quick-actions.md).

   ![Dalgalı çizgiler](../ide/media/vs2017_squiggle.png)

- [Çağrı hiyerarşisi](../ide/reference/call-hierarchy.md) penceresi çağırın ve, tarafından çağrılan yöntemleri göstermek için metin düzenleyicisi bağlam menüsünden açılabilir yöntemi şapka (ekleme noktasını) altında.

   ![Çağrı hiyerarşisi penceresi](../ide/media/VSIDE_call_hierarchy.png)

- [CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md) , değişiklikleri kod, bağlantılı hatalar, iş öğelerini, kod gözden geçirme ve birim testleri için tüm düzenleyiciden ayrılmadan ve başvurular bulmanızı sağlar.

   ![CodeLens](../ide/media/codelensoverview.png)

- [Tanımına Peek](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) penceresi çıktığınızda geçerli bağlamı gitmeden bir metot veya tür tanımı satır içi gösterir.

   ![Tanımına Gözat](../ide/media/VSIDE_peek_definition.png)

- [Tanıma Git](../ide/go-to-and-peek-definition.md) bağlam menüsü seçeneğini doğrudan burada işlevi veya nesne tanımlanmış yer alır. Diğer Gezinti komutları de Düzenleyicisi'nde sağ tıklayarak kullanılabilir.

   ![Tanıma gitme](../ide/media/VSIDE_go_to_definition.png)

## <a name="create-a-program"></a>Bir program oluşturun

Şimdi daha yakından inceleyin ve yeni, basit bir program oluşturun.

1. Visual Studio'yu açın. Menüsünde, **dosya** > **yeni** > **proje**.

  ![Dosya > Yeni Proje menü çubuğunda](../ide/media/VSIDE_Tour_NewProject1.png)

1. **Yeni proje** iletişim kutusu gösterir birkaç proje *şablonları*. Bir şablonu temel dosyaları ve verilen proje türü için gerekli ayarları içerir. Seçin **.NET Core** kategorisi altında **Visual C#** ve ardından **konsol uygulaması (.NET Core)** şablonu. İçinde **adı** metin kutusunda, **HelloWorld**ve ardından **Tamam** düğmesi.

  ![.NET core uygulama şablonu](../ide/media/overview-new-project-dialog.png)

   Visual Studio projesi oluşturur. Çağıran basit bir "Hello World" uygulaması olan <xref:System.Console.WriteLine?displayProperty=nameWithType> değişmez değer dize "Hello World!" görüntülenecek yöntemi Konsol penceresinde.

  > [!NOTE]
  > Görmüyorsanız, **.NET Core** kategorisi, yüklemeniz gereken **.NET Core platformlar arası geliştirme** iş yükü. Bunu yapmak için seçin **açık Visual Studio yükleyicisi** alt sol tarafındaki bağlantı **yeni proje** iletişim. Sonra **Visual Studio yükleyicisi** açar, aşağı kaydırın ve seçin **.NET Core platformlar arası geliştirme** iş yükü ve ardından **Değiştir**.

   Kısa bir süre sonra aşağıdakine benzer bir şey görmeniz gerekir:

   ![Visual Studio IDE](../ide/media/overview-ide-console-app.png)

   Uygulamanız için C# kod alanı çoğunu alır Düzenleyicisi penceresinde gösterilir. Anahtar sözcükler ve türleri gibi kodu değişik yönlerini göstermek için metni otomatik olarak renklendirilen dikkat edin. Ayrıca, hangi küme ayraçları birbiriyle eşleşen kodda küçük, dikey kesikli satırlar belirtmek ve kodu daha sonra bulun Yardım satır numaraları. Daraltma veya kod genişletmek için küçük, paketlenmiş eksi işareti seçebilirsiniz. Anahat oluşturma özelliği bu kod, ekranda dağınıklığı en aza indirmek için yardımcı olma, gerekmeyen kod gizleme olanak sağlar.

   Proje dosyaları olarak adlandırılan bir penceresinde sağ tarafta listelenen **Çözüm Gezgini**.

  ![Visual Studio IDE kırmızı kutuları](../ide/media/overview-ide-console-app-red-boxes.png)

  Diğer menüleri ve araç pencereleri kullanılabilir olduğundan, ancak şimdi taşımanız şimdilik.

1. Şimdi, uygulamayı başlatın. Bunu seçerek yapmak **hata ayıklama olmadan Başlat** gelen **hata ayıklama** menü çubuğundaki menüsü. Tuşlarına da basabilirsiniz **Ctrl**+**F5**.

  ![Hata ayıklama > Başlat menüsü hata ayıklama olmadan](../ide/media/overview-start-without-debugging.png)

  Visual Studio uygulaması oluşturur ve iletisiyle bir konsol penceresi açar **Hello World!**. Artık çalışan bir uygulamanın sahip!

  ![Konsol penceresi](../ide/media/overview-console-window.png)

1. Konsol penceresini kapatmak için klavyenizde herhangi bir tuşa basın.

1. Uygulama için bazı ek kod ekleyelim. Aşağıdaki C# kodu yazan satırı önce ekleyin `Console.WriteLine("Hello World!");`:

   ```csharp
   Console.WriteLine("\nWhat is your name?");
   var name = Console.ReadLine();
   ```

   Bu kod görüntüler **adınızı nedir?** konsol penceresi, ve ardından kullanıcı arkasından bazı metinleri girene kadar bekler **Enter** anahtarı.

1. Yazan satırı değiştirin `Console.WriteLine("Hello World!");` aşağıdaki kodu için:

   ```csharp
   Console.WriteLine($"\nHello {name}!");
   ```

1. Seçerek uygulamayı yeniden çalıştırın **hata ayıklama** > **hata ayıklama olmadan Başlat** basarak veya **Ctrl**+**F5**.

   Visual Studio uygulama yeniden oluşturur ve bir konsol penceresi açar ve için adınızı ister.

1. Konsol penceresi ve tuşuna adınızı girin **Enter**.

   ![Konsol penceresinde giriş](media/overview-console-input.png)

1. Konsol penceresini kapatın ve çalışan programı durdurmak için herhangi bir tuşa basın.

## <a name="use-refactoring-and-intellisense"></a>Yeniden düzenleme ve IntelliSense kullanma

Yolları birkaç bakalım, [yeniden düzenleme](refactoring-in-visual-studio.md) ve [IntelliSense](using-intellisense.md) yardımcı olabilecek daha verimli bir şekilde kod.

İlk olarak, şimdi yeniden adlandırmak `name` değişkeni:

1. Çift `name` değişken seçin.

1. Değişken için yeni adı yazın `username`.

   Değişkeni ve bir ampul gri kutu görünür bildirimi kenar boşluğunda görüntülenir.

1. Kullanılabilir göstermek için ampul simgesini seçin [hızlı Eylemler](quick-actions.md). Seçin **yeniden adlandırma '' username' name'**.

   ![Visual Studio'da eylemini yeniden adlandır](media/rename-quick-action.png)

   Değişkeni olan bu örnekte yalnızca iki yerde projede adlandırılır.

   ![Visual Studio'da yeniden adlandırma düzenlemesi gösteren animasyonlu gif](media/rename-refactoring.gif)

1. Şimdi IntelliSense bir göz atalım. Yazan satırı aşağıda `Console.WriteLine($"\nHello {username}!");`, türü **DateTime şimdi DateTime =.**.

   Bir kutu üyelerini görüntüler <xref:System.DateTime> sınıfı. Ayrıca, şu anda seçili üyeyi açıklamasını ayrı bir kutu görüntüler.

   ![Visual Studio'da IntelliSense listesi üyeleri](media/intellisense-list-members.png)

1. Adlı üyeyi seçin **şimdi**, çift veya tuşuna basarak sınıfının bir özelliği olan **sekmesini**. Noktalı virgül ekleyerek kod satırı tamamlamak **;**.

1. Aşağıda, aşağıdaki kod satırlarını kopyalayın veya yazın:

   ```csharp
   int dayOfYear = now.DayOfYear;

   Console.Write("Day of year: ");
   Console.WriteLine(dayOfYear);
   ```

   > [!TIP]
   > <xref:System.Console.Write%2A?displayProperty=nameWithType> için biraz farklıdır <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> içeren Yazar sonra bir satır Sonlandırıcı eklemez. Çıktıyı gönderilen metni sonraki parçasını aynı çizgi üzerinde yazdırılır anlamına gelir. Bu yöntemlerin her biri üzerinde kendi açıklamasını görmek için kodunuzda gelebilirsiniz.

1. Ardından, yeniden yeniden düzenleme kod biraz daha kısa olmak için kullanacağız. Tıklatın değişkeni `now` satırına `DateTime now = DateTime.Now;`.

   Küçük bir tornavida simgesi o satırdaki kenar boşluğunda görüntülendiğine dikkat edin.

1. Sunabileceği önerileri görmek için tornavida simgesini Visual Studio olan kullanılabilir. Bu durumda, gösteren [satır içi geçici değişken](reference/inline-temporary-variable.md) yeniden düzenleme kod satırı genel davranışını değiştirmeden kaldırmak için:

   ![Satır içi geçici değişken Visual Studio'da yeniden düzenleme](media/inline-temporary-variable-refactoring.png)

1. Tıklatın **satır içi geçici değişken** kodu yeniden düzenlemeniz için.

1. Tuşlarına basarak programı yeniden çalıştırın **Ctrl**+**F5**. Çıktı şuna benzer:

   ![Program çıkış konsol penceresi](../ide/media/overview-console-final.png)

## <a name="debug-code"></a>Kodda hata ayıklama

Kodu yazarken, çalıştırmak ve hatalar için test gerekir. Visual Studio'nun hata ayıklama sistem, bir seferde bir deyim kod adım adım ve ilerledikçe değişkenleri incelemek sağlar. Belirtilen bir koşul doğru olduğunda, yalnızca isabet kesme noktaları ayarlayabilirsiniz. Kod çalıştırır ve daha fazlasını olarak değişkenlerin değerleri izleyebilirsiniz.

Şimdi değerini görmek için bir kesme noktası belirleyerek `username` program "Uçuş modunda" iken değişkeni.

1. Diyor kod satırı bulun `Console.WriteLine($"\nHello {username}!");`. Bu kod satırı, bu satırı yürütme duraklatmak program yapmak için diğer bir deyişle, bir kesme noktası ayarlamak için Düzenleyicisi kadar sol kenar boşluğunda'ı tıklatın. Ayrıca kod satırında herhangi bir yere tıklayın ve sonra basın **F9**.

   Şu ana kadar sol kenar boşluğunda kırmızı bir daire görünür ve kod kırmızıyla vurgulanır.

   ![Visual Studio'da kod satırına kesme noktası](media/breakpoint.png)

1. Seçerek hata ayıklamayı Başlat **hata ayıklama** > **hata ayıklamayı Başlat** basarak veya **F5**.

1. Konsol penceresinde görünür ve için adınızı ister, yazın ve basın **Enter**.

   Visual Studio kod düzenleyicisine odağı döndürür ve kesme noktası ile kod satırı sarı ile vurgulanmış dikkat edin. Bu kodun sonraki satırında, program yürütecek olduğunu belirtir.

1. Farenizi üzerine gelerek `username` değerini görmek için değişkeni. Alternatif olarak, üzerinde sağ tıklayarak `username` seçip **Gözcü Ekle** değişkeni eklemek için **izleme** penceresinde, burada da görebilirsiniz değeri.

   ![Visual Studio'da hata ayıklama sırasında değişken değeri](media/debugging-variable-value.png)

1. Programının tamamlanıncaya kadar çalışmasına izin vermek için basın **F5** yeniden.

Visual Studio'da hata ayıklama hakkında daha fazla bilgi edinmek için bkz: [hata ayıklayıcı, özellik Turu](../debugger/debugger-feature-tour.md).

## <a name="customize-visual-studio"></a>Visual Studio özelleştirme

Varsayılan renk temasını değiştirme gibi IDE kişiselleştirebilirsiniz. Değiştirmek için **koyu** tema:

1. Menü çubuğunda seçin **Araçları** > **seçenekleri** açmak için **seçenekleri** iletişim.

1. Üzerinde **ortam** > **genel** seçenekler sayfası, değişiklik **renk temasını** seçimi **koyu**ve ardından seçin **Tamam**.

   IDE değişikliklerini tüm renk temasını **koyu**.

   ![VS koyu tema içinde](media/quickstart-personalize-dark-theme.png)

IDE'yi kişiselleştirme diğer yollarını öğrenmek için bkz: [kişiselleştirme Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

## <a name="learn-more"></a>Daha fazla bilgi edinin

Bir Android veya iOS telefon için bir uygulama oluşturmak istiyor musunuz? Ne dersiniz 3B oyun veya Bulut özellikli bir uygulama? Bunlar ve diğer Visual Studio özellikleri hakkında bilgi edinmek için bkz: [Visual Studio 2017 özellikleri](../ide/advanced-feature-overview.md).

Şimdi kodlamaya başlamak için hemen hazır olduğunuzda hızlı başlangıç konulardan birine içindekiler tablosundan aşağıdaki gibi seçin [ilk ASP.NET Core web uygulamanızı oluşturma](quickstart-aspnet-core.md).

Kullanılabilir ücretsiz Visual Studio kurslara çıkışı kontrol edebilirsiniz [Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!index=2&lang=1033).

## <a name="see-also"></a>Ayrıca bkz.

* [Daha fazla Visual Studio özellikleri](../ide/advanced-feature-overview.md)
* [www.VisualStudio.com](https://www.visualstudio.com/vs/)
* [Visual Studio Web günlüğü](https://blogs.msdn.microsoft.com/visualstudio/)
* [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)