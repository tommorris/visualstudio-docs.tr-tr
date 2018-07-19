---
title: Uygulama Sayfası, Proje Tasarımcısı (C#)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesApplicationWPF
- cs.ProjectPropertiesApplication
helpviewer_keywords:
- Project Designer, Application page
- Application page in Project Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 0df628a83bf88acb4f73d7bb47269458bd34ace9
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38808891"
---
# <a name="application-page-project-designer-c"></a>Uygulama Sayfası, Proje Tasarımcısı (C#)

Kullanım **uygulama** sayfasının **Proje Tasarımcısı** projenin uygulama ayarları ve özellikleri belirtmek için.

Erişim için **uygulama** sayfasında, bir proje düğümü seçin (değil **çözüm** düğümü) içinde **Çözüm Gezgini**. Ardından **proje**, **özellikleri** menü çubuğundaki. Proje Tasarımcısı göründüğünde tıklayın **uygulama** sekmesi.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="general-application-settings"></a>Genel Uygulama ayarları
 Aşağıdaki seçenekler uygulama genel ayarlarını yapılandırmak etkinleştirin.

 **Derleme adı** derleme bildirimi tutacak çıkış dosyasının adını belirtir. Bu özelliği değiştirmek de değiştirecek **çıkış adı** özelliği. Kullanarak komut satırından bu değişikliği yapabilirsiniz [/out (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/out-compiler-option). Bu özelliğe program aracılığıyla erişmek için bkz: <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.

 **Varsayılan ad alanı** projeye eklenen dosyaları için temel ad alanını belirtir.

 Bkz: [ad alanı](/dotnet/csharp/language-reference/keywords/namespace) kodunuzda ad alanları oluşturma hakkında daha fazla bilgi için.

 Bu özelliğe program aracılığıyla erişmek için bkz: <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.

 **Hedef Framework** .NET Framework sürümünü belirtir, uygulama hedefler. Bu seçenek, bilgisayarınızda yüklü olan .NET Framework sürümleri bağlı olarak farklı değerlere sahip olabilir.

 Varsayılan olarak, seçtiğiniz hedef Framework'ü aynı değerdir **yeni proje** iletişim kutusu.

> [!NOTE]
> Listelenen önkoşul paketleri [Önkoşullar iletişim kutusu](../../ide/reference/prerequisites-dialog-box.md) iletişim kutusunu ilk açışınızda otomatik olarak ayarlanır. Projenin hedef çerçevesi daha sonra değiştirirseniz, yeni hedef Framework'ü el ile eşleştirmek için önkoşulları seçmeniz gerekecektir.


 Daha fazla bilgi için [nasıl yapılır: .NET Framework sürümü hedefleme](../../ide/how-to-target-a-version-of-the-dotnet-framework.md) ve [Visual Studio çoklu sürüm desteğine genel bakış](../../ide/visual-studio-multi-targeting-overview.md).

 **Uygulama türü** oluşturmak için uygulama türünü belirtir. Windows 8.x uygulamalar için belirttiğiniz **Windows Store App**, **sınıf kitaplığı**, veya **WinMD dosyası**. Çoğu diğer uygulama türleri için belirttiğiniz **Windows uygulama**, **konsol uygulaması**, **sınıf kitaplığı**, **Windows hizmeti**, veya **Web Denetim Kitaplığı**.

 Bir web uygulaması projesi belirtmelisiniz **sınıf kitaplığı**.

 Belirtirseniz **WinMD dosyası** seçenek türleri tüm Windows programlama dilini çalışma zamanına öngörülen. Proje bir WinMD dosyası olarak çıkış paketleme tarafından uygulamanın birden çok dilde kod ve kodu yazdığınız gibi birlikte çalışmak tümü aynı dilde. Windows çalışma zamanı kitaplıkları dahil olmak üzere, hedef çözümleri için bu seçeneği belirtebilirsiniz [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] uygulamalar. Daha fazla bilgi için [C# ve Visual Basic'te Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

> [!NOTE]
> Windows çalışma zamanı türleri, böylece bunları hangi dil kullanır yerel nesneler olarak görünürler yansıtabilirsiniz. Örneğin, isteğe bağlı olarak, Windows çalışma zamanı ile etkileşim JavaScript uygulamaları JavaScript nesneleri bir dizi kullanın ve C# uygulamaları kitaplığı bir .NET nesneleri koleksiyon olarak kullanın. Projenin çıkış bir WinMD dosyası olarak paketleyerek Windows çalışma zamanı kullanan aynı teknolojiyi yararlanabilir.


 Hakkında daha fazla bilgi için **uygulama türü** özelliğine bakın [/target (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/target-compiler-option). Bu özelliği programlama yoluyla erişim hakkında daha fazla bilgi için bkz: <xref:VSLangProj.ProjectProperties.OutputType%2A>.

 **Derleme bilgileri** düğmede seçeneğine tıkladığınızda [derleme bilgileri iletişim kutusu](../../ide/reference/assembly-information-dialog-box.md).

 **Başlangıç nesnesi** uygulama yüklenirken çağrılacak giriş noktasını tanımlar. Bu uygulama ya da çok ana forma ya da genel olarak ayarlanmıştır `Main` yordamı, uygulama başlatıldığında çalıştırmanız gerekir. Sınıf kitaplıkları, bir giriş noktası olmadığı için tek seçenektir bu özellik için **(ayarlanmamış)**.

 Bu seçenek bir WPF tarayıcı uygulaması projesinde varsayılan olarak **(ayarlanmamış)**. Diğer seçenek *Projectname*. uygulama. İçinde bu tür bir projeye ilişkin başlangıç URI uygulama başlatıldığında bir UI kaynak yüklemek için ayarlamanız gerekir. Bunu yapmak için projenizde Application.xaml dosyasını açın ve ayarlayın `StartupUri` gt;Window1.XAML gibi projenizi bir .xaml dosyasında özelliği. Kabul edilebilir kök öğeleri listesi için bkz. <xref:System.Windows.Application.StartupUri%2A>. Tanımlamak de bir `public static void Main()` projedeki bir sınıftaki yöntemi. Bu sınıf görünür **Başlangıç nesnesi** olarak listesinde *ProjectName.ClassName*. Ardından, sınıf Başlangıç nesnesi seçebilirsiniz.

 Bkz: [/Main (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/main-compiler-option) daha fazla bilgi için. Bu özelliğe program aracılığıyla erişmek için bkz: <xref:VSLangProj.ProjectProperties.StartupObject%2A>.

## <a name="resources"></a>Kaynaklar
 Aşağıdaki seçenekler uygulama genel ayarlarını yapılandırmak etkinleştirin.

 **Simge ve bildirim** varsayılan olarak, bu radyo düğmesi seçilir ve **simgesi** ve **bildirim** seçenekleri etkinleşir. Bu, kendi simgesini seçin veya farklı bildirim oluşturma seçenekleri seçmenizi sağlar. Bu radyo düğmesi projesi için kaynak dosyasını sağlanmaktadır sürece seçili bırakın.

 **Simge** , program simgesi kullanmak istediğiniz .ico dosyasını seçer. Var olan bir grafik göz atmak için üç nokta düğmesine tıklayın ya da istediğiniz dosyanın adını yazın. Bkz: [/win32icon (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option) daha fazla bilgi için. Bu özelliğe program aracılığıyla erişmek için bkz: <xref:VSLangProj.ProjectProperties.ApplicationIcon%2A>.

 **Bildirim** Windows Vista kullanıcı hesabı denetimi (UAC altında) uygulama çalışırken, bir bildirim üretme seçeneğini belirler. Bu seçenek, aşağıdaki değerlere sahip olabilir:

-   **Varsayılan ayarlarla bildirimi katıştırmak**. Windows Güvenlik bilgisini uygulamanın yürütülebilir dosyasına katıştırma için olan belirten Windows Vista'da, Visual Studio çalıştığı zamanki destekler `requestedExecutionLevel` olması `AsInvoker`. Varsayılan seçenek budur.

-   **Bir bildirim olmadan uygulama oluşturma**. Bu yöntem olarak da bilinen *sanallaştırma*. Eski uygulamalarla uyumluluk için bu seçeneği kullanın.

-   **Properties\app.manifest**. Bu seçenek, ClickOnce veya Registration-Free COM tarafından dağıtılan uygulamalar için gereklidir Bir uygulamayı ClickOnce dağıtımını kullanarak yayımlarsanız **bildirim** için bu seçenek otomatik olarak ayarlanır.

**Kaynak dosyası** projesi için kaynak dosyasını sağlanırken, bu radyo düğmesini seçin. Bu seçeneği devre dışı bırakır **simgesi** ve **bildirim** seçenekleri.

Bir yol adı girin veya Gözat düğmesini kullanın (**...** ) bir Win32 kaynak dosyası projeye eklenecek.