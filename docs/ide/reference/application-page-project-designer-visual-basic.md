---
title: Uygulama sayfası, Proje Tasarımcısı (Visual Basic) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vb.ProjectPropertiesApplicationWPF
- vb.ProjectPropertiesApplication
helpviewer_keywords:
- Project Designer, Application page
- Application page in Project Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9372f915fb1914bea971ffb287fa5788a9372449
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="application-page-project-designer-visual-basic"></a>Uygulama Sayfası, Proje Tasarımcısı (Visual Basic)

Kullanım **uygulama** bir projenin uygulama ayarlarını ve özelliklerini belirtmek için Proje Tasarımcısı'nın sayfası.

Erişim için **uygulama** sayfası, proje düğümüne seçin (değil **çözüm** düğümü) içinde **Çözüm Gezgini**. Ardından **proje** > **özellikleri** menü çubuğunda. Proje Tasarımcısı göründüğünde seçin **uygulama** sekmesi.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="general-application-settings"></a>Genel Uygulama ayarları

Aşağıdaki seçenekler, bir uygulama için genel ayarlarını yapılandırmak etkinleştirin.

### <a name="assembly-name"></a>Derleme adı

Derleme bildirimi içerecek çıktı dosyası adını belirtir. Bu özelliği değiştirirseniz **çıktı adı** özelliğini de değiştirir. Kullanarak bir komut isteminden çıkış dosyasının adı belirtebilirsiniz [/out (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/out) derleyici anahtar. Bu özellik program aracılığıyla erişme hakkında daha fazla bilgi için bkz: <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.

### <a name="root-namespace"></a>Kök ad alanı

Projedeki tüm dosyalar için temel ad alanını belirtir. Örneğin, ayarlarsanız **kök Namespace** için `Project1` ve sahip olduğunuz bir `Class1` kodunuzdaki tüm ad alanı dışında kendi ad olacaktır `Project1.Class1`. Varsa bir `Class2` bir ad alanındaki `Order` kodda, kendi ad olacaktır `Project1.Order.Class2`.

Silerseniz **kök Namespace**, kodda projenizin ad alanı yapısını belirtebilirsiniz.

> [!NOTE]
> Genel anahtar sözcük kullanırsanız, bir [Namespace deyimi](/dotnet/visual-basic/language-reference/statements/namespace-statement), projenizin kök ad alanı dışında bir ad alanı tanımlayabilirsiniz. Silerseniz **kök Namespace**, `Global` gereksinimini ortadan kaldırır üst düzey ad hale `Global` in anahtar sözcüğü bir `Namespace` deyimi. Daha fazla bilgi için bkz: "Genel anahtar sözcüğü içinde arama Namespace deyimleri" [Visual Basic'de ad alanları](/dotnet/visual-basic/programming-guide/program-structure/namespaces).

Ad alanları, kodunuzda oluşturma hakkında daha fazla bilgi için bkz: [Namespace deyimi](/dotnet/visual-basic/language-reference/statements/namespace-statement).

Kök ad alanı özelliği hakkında daha fazla bilgi için bkz: [/RootNamespace](/dotnet/visual-basic/reference/command-line-compiler/rootnamespace).

Bu özellik program aracılığıyla erişme hakkında daha fazla bilgi için bkz: <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.

### <a name="target-framework-all-configurations"></a>Hedef Framework'ü (tüm yapılandırmaları)

.NET Framework sürümünü belirtir, uygulama hedefler. Bu seçenek bilgisayarınızda yüklü sürümlerini .NET Framework'ün bağlı olarak farklı değerlere sahip olabilir.

Varsayılan değer, belirtilen hedef Framework'ü eşleşen **yeni proje** iletişim kutusu.

> [!NOTE]
> Listelenen önkoşul [Önkoşullar iletişim kutusu](../../ide/reference/prerequisites-dialog-box.md) iletişim kutusu ilk kez açıldığında otomatik olarak ayarlanır. Projenin hedef çerçevesi daha sonra değiştirirseniz, yeni hedef Framework'ü el ile eşleşecek şekilde önkoşulları belirtmeniz gerekir.

Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../../ide/how-to-target-a-version-of-the-dotnet-framework.md) ve [Visual Studio çoklu sürüm desteğine genel bakış](../../ide/visual-studio-multi-targeting-overview.md).

### <a name="application-type"></a>Uygulama türü

Derlenecek uygulamanın türünü belirtir. Windows 8.x uygulamaları için belirttiğiniz **Windows mağazası uygulaması**, **sınıf kitaplığı**, veya **WinMD dosyası**. Diğer birçok uygulama türleri için belirttiğiniz **Windows uygulaması**, **konsol uygulaması**, **sınıf kitaplığı**, **Windows hizmeti**, veya **Web kontrol Kitaplığı**.

Bir web uygulaması projesi için belirtmelisiniz **sınıf kitaplığı**.

Belirtirseniz **WinMD dosyası** seçeneği türleri tüm Windows çalışma zamanı programlama dili öngörülen. Proje çıktı WinMD dosyası olarak paketleme tarafından uygulamanın birden çok dilde kod ve gibi yazdıysanız çalışmanız koda sahip tüm aynı dilde. Kullanabileceğiniz **WinMD dosyası** seçeneği de dahil olmak üzere Windows çalışma zamanı kitaplıkları hedefleyen çözümler için [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] uygulamalar. Daha fazla bilgi için bkz: [C# ve Visual Basic Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

> [!NOTE]
> Windows çalışma zamanı, böylece bunları hangi dil kullanır yerel nesneler olarak görünürler türleri yansıtabilirsiniz. Örneğin, isteğe bağlı olarak Windows çalışma zamanı ile etkileşim JavaScript uygulamaları JavaScript nesne kümesi kullanın ve C# uygulamalarının kitaplığı .NET nesneleri bir koleksiyon olarak kullanın. Proje çıktı WinMD dosyası olarak paketleyerek Windows çalışma zamanı kullanan aynı teknolojisi yararlanabilir.

Hakkında daha fazla bilgi için **uygulama türü** özelliği, bkz: [/target (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/target). Bu özellik program aracılığıyla erişme hakkında daha fazla bilgi için bkz: <xref:VSLangProj.ProjectProperties.OutputType%2A>.

### <a name="icon"></a>Simge

Program simgesi olarak kullanmak istediğiniz .ico dosyasını ayarlar. Seçin  **\<Gözat... >** için varolan grafiği gidin. Bkz: [/win32icon](/dotnet/visual-basic/reference/command-line-compiler/win32icon) (veya [/win32icon (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option)) daha fazla bilgi için. Bu özellik programlı olarak erişmek için bkz: <xref:VSLangProj.ProjectProperties.ApplicationIcon%2A>.

### <a name="startup-form--startup-object--startup-uri"></a>Başlangıç formu / Başlangıç nesnesi / başlangıç URI

Uygulamanın başlangıç form veya giriş noktasını belirtir.

Varsa **etkinleştir uygulama çerçevesi** seçilir (varsayılan), bu liste başlıklı **başlangıç formu** ve uygulama çerçevesi yalnızca başlatma formları desteklediğinden yalnızca formları olmayan nesneleri gösterir.

Bu liste bir WPF tarayıcı uygulaması projesiyse başlıklı **başlangıç URI**, ve varsayılan değer **Page1.xaml**. **Başlangıç URI** listesi uygulama başladığında, uygulama görüntüler kullanıcı arabirimi kaynak (XAML öğesi) belirtmenize olanak sağlar. Daha fazla bilgi için bkz. <xref:System.Windows.Application.StartupUri%2A>.

Varsa **etkinleştir uygulama çerçevesi** temizlendiğinde, bu liste hale **Başlangıç nesnesi** ve formlar ve sınıfları veya modüllerle gösterir bir `Sub Main`.

**Başlangıç nesnesi** uygulama yüklendiğinde çağrılacak giriş noktası tanımlar. Genellikle bu, uygulamanızın veya çok ana form ayarlandığından `Sub Main` yordamı, uygulama başladığında çalıştırmanız gerekir. Sınıf kitaplıkları bir giriş noktası olmadığı için tek seçenektir bu özellik için **(hiçbiri)**. Daha fazla bilgi için bkz: [/ana](/dotnet/visual-basic/reference/command-line-compiler/main). Bu özellik programlı olarak erişmek için bkz: <xref:VSLangProj.ProjectProperties.StartupObject%2A>.

### <a name="assembly-information"></a>Derleme bilgileri

Görüntülemek için bu düğmeye tıkladığınızda [derleme bilgileri iletişim kutusu](../../ide/reference/assembly-information-dialog-box.md).

### <a name="enable-application-framework"></a>Uygulama Çerçevesi etkinleştir

Bir proje uygulama çerçevesi kullanıp kullanmayacağını belirtir. Bu seçenek ayarı kullanılabilir seçenekleri etkiler **başlangıç formu**/**Başlangıç nesnesi**.

Bu onay kutusunu seçtiyseniz, uygulamanızın standart kullandığı `Sub Main`. Bu onay kutusunu işaretleyerek sağlayan özellikleri **Windows uygulama framework özelliklerini** bölüm ve bir başlangıç formu seçmenizi gerektirir.

Bu onay kutusu işaretli değilse, özel, uygulamanızın kullandığı `Sub Main` belirttiğiniz **başlangıç formu**. Bu durumda, bir başlangıç nesnesi belirtebilirsiniz (özel bir `Sub Main` bir yöntem ya da bir sınıf) veya bir form. Ayrıca, seçeneklerinde **Windows uygulama framework özelliklerini** bölüm kullanılamıyor.

### <a name="view-windows-settings"></a>Windows ayarlarını görüntüle

App.manifest dosyasını açmak ve oluşturmak için bu düğmeye tıklayın. Visual Studio, uygulama için bildirim verileri oluşturmak için bu dosyayı kullanır. Değiştirerek yürütme düzeyini kümesi UAC istenen sonra `<requestedExecutionLevel>` app.manifest içinde şu şekilde etiketleyin:

`<requestedExecutionLevel level="asInvoker" />`

ClickOnce ile düzeyini çalışır `asInvoker` veya sanallaştırılmış modda (bildirim üretme yok). Sanallaştırılmış modunu belirtmek için tüm etiket app.manifest kaldırın.

Bildirim oluşturma hakkında daha fazla bilgi için bkz: [Windows Vista'da ClickOnce dağıtımı](../../deployment/clickonce-deployment-on-windows-vista.md).

## <a name="windows-application-framework-properties"></a>Windows uygulama Framework özellikleri

Aşağıdaki ayarlar kullanılabilir **Windows uygulama framework özelliklerini** bölümü. Bu seçenekler kullanılabilir yalnızca **etkinleştir uygulama çerçevesi** onay kutusu seçilidir. Bunu aşağıdaki bölümde açıklanmıştır **Windows uygulama framework özelliklerini** Windows Presentation Foundation (WPF) uygulamaları için ayarlar.

### <a name="enable-xp-visual-styles"></a>XP görsel stilleri etkinleştir

Etkinleştirir veya Windows XP görsel stilleri olarak da bilinen devre dışı bırakır *Windows XP temaları*. Windows XP görsel stilleri Örneğin, yuvarlatılmış köşeleri ve dinamik renkleri denetimleriyle etkinleştirin. Varsayılan etkindir.

### <a name="make-single-instance-application"></a>Tek örnek uygulaması yap

Kullanıcıların uygulama birden çok örneğini çalıştırmasını engellemek için bu onay kutusunu seçin. Bu onay kutusu için varsayılan ayar *temizlenmiş*, uygulamanın çalıştırılması için birden çok örneğini sağlar. Daha fazla bilgi için bkz: <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> olay.

### <a name="save-mysettings-on-shutdown"></a>My.Settings kapanışında Kaydet

Uygulamanın belirtmek için bu onay kutusunu işaretleyin `My.Settings` ayarlar, kullanıcıların bilgisayarlarını kapattığınızda kaydedilir. Varsayılan ayar etkindir. Bu seçenek devre dışıysa, uygulama ayarlarını elle çağırarak kaydedebilirsiniz `My.Settings.Save`.

### <a name="authentication-mode"></a>Kimlik doğrulama modu

Seçin **Windows** (şu anda oturum açmış kullanıcıyı tanımlamak için Windows kimlik doğrulaması kullanımını belirlemek için varsayılan). Kullanarak bu bilgileri zamanında alabilirsiniz `My.User` nesnesi. Seçin **uygulama tanımlı** varsayılan Windows kimlik doğrulama yöntemleri kullanmak yerine kullanıcıların kimliklerini doğrulamak için kendi kodunuzu sağlayacaksa.

### <a name="shutdown-mode"></a>Kapatma modu

Seçin **başlangıç formu kapattığı zaman** (diğer forms açık olsalar bile formu başlangıç formu olarak ayarladığınızda uygulama çıkış kapanır olduğunu belirtmek için varsayılan). Seçin **zaman son formu kapanır** uygulama son form kapatıldığında veya zaman çıkmak belirtmek için `My.Application.Exit` veya `End` deyimi açıkça çağrılır.

Seçin **açık kapatma sırasında** açıkça çağırdığınızda uygulamadan çıkmak belirtmek için `Shutdown`.

Seçin **üzerinde son pencereyi kapatmanız** uygulama son penceresi kapatıldığında veya açıkça çağırdığınızda çıkma belirtmek için `Shutdown`. Varsayılan ayar budur.

Seçin **üzerinde ana pencereyi kapatmak** uygulamanın ana penceresi kapatıldığında veya açıkça çağırdığınızda çıkma belirtmek için `Shutdown`.

### <a name="splash-screen"></a>Giriş ekranı

Giriş ekranı kullanmak istediğiniz formu seçin. Daha önce bir giriş ekranı bir form veya bir şablon kullanarak oluşturmuş olmanız gerekir. Varsayılan değer **(hiçbiri)**.

### <a name="view-application-events"></a>Uygulama olaylarını görüntüle

İçinde yazabilirsiniz olayları uygulama framework olayları için bir olay kod dosyası görüntülemek için bu düğmeye tıkladığınızda `Startup`, `Shutdown`, `UnhandledException`, `StartupNextInstance` ve `NetworkAvailabilityChanged`. Ayrıca belirli uygulama framework yöntemlerini geçersiz kılabilirsiniz. Örneğin, giriş ekranı görüntü davranışını geçersiz kılarak değiştirebileceğiniz `OnInitialize`.

## <a name="windows-application-framework-properties-for-windows-presentation-foundation-wpf-applications"></a>Windows Presentation Foundation (WPF) uygulamaları için Windows uygulama Framework özellikleri

Aşağıdaki ayarlar kullanılabilir **Windows uygulama framework özelliklerini** bölümünde Proje bir Windows Presentation Foundation uygulaması olduğunda. Bu seçenekler kullanılabilir yalnızca **etkinleştir uygulama çerçevesi** onay kutusu seçilidir. Bu tabloda listelenen seçenekleri, yalnızca WPF uygulamaları ya da WPF tarayıcı uygulamaları için kullanılabilir. WPF kullanıcı denetimi veya özel denetimi kitaplıkları için kullanılamaz.

### <a name="shutdown-mode"></a>Kapatma modu

Bu özellik yalnızca Windows Presentation Foundation uygulamaları için geçerlidir.

Seçin **açık kapatma sırasında** açıkça çağırdığınızda uygulamadan çıkmak belirtmek için <xref:System.Windows.Application.Shutdown%2A>.

Seçin **üzerinde son pencereyi kapatmanız** uygulama son penceresi kapatıldığında veya açıkça çağırdığınızda çıkma belirtmek için <xref:System.Windows.Application.Shutdown%2A>. Varsayılan ayar budur.

Seçin **üzerinde ana pencereyi kapatmak** uygulamanın ana penceresi kapatıldığında veya açıkça çağırdığınızda çıkma belirtmek için <xref:System.Windows.Application.Shutdown%2A>.

Bu ayarı kullanma hakkında daha fazla bilgi için bkz: <xref:System.Windows.Application.Shutdown%2A>

### <a name="edit-xaml"></a>XAML Düzenle

Açın ve XAML Düzenleyicisi'nde uygulama tanımı dosyası (Application.xaml) değiştirmek için bu düğmeye tıklayın. Bu düğmeye tıkladığınızda, uygulama tanım düğümde Application.xaml açar. Kaynakları tanımlama gibi belirli görevleri gerçekleştirmek için bu dosyayı düzenlemek zorunda kalabilirsiniz. Uygulama tanımı dosyası mevcut değilse, Proje Tasarımcısı tane oluşturur.

### <a name="view-application-events"></a>Uygulama olaylarını görüntüle

Görüntülemek için bu düğmeye tıkladığınızda `Application` bir kod düzenleyicisinde kısmi sınıf dosyası (Application.xaml.vb). Dosya yoksa, Proje Tasarımcısı uygun sınıf ve ad alanına sahip bir tane oluşturur.

<xref:System.Windows.Application> Nesne (örneğin, uygulama başlatma veya kapatma) belirli uygulama durumu değişiklikler meydana geldiğinde olayları başlatır. Bu sınıf gösteren olayları tam bir listesi için bkz: <xref:System.Windows.Application>. Bu olaylar kullanıcı kodu bölümünde işlenmektedir `Application` parçalı sınıf.