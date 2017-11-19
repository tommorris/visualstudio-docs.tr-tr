---
title: "Uygulama sayfası, Proje Tasarımcısı (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cs.ProjectPropertiesApplicationWPF
- cs.ProjectPropertiesApplication
helpviewer_keywords:
- Project Designer, Application page
- Application page in Project Designer
ms.assetid: f13701a8-4e2e-4474-9d60-bb43decbe0c1
caps.latest.revision: "56"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5f32dceca8a6b14e6b1777e5c525327f46adca47
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="application-page-project-designer-c"></a>Uygulama Sayfası, Proje Tasarımcısı (C#)
Kullanım **uygulama** sayfasında **Proje Tasarımcısı** projenin uygulama ayarlarını ve özelliklerini belirtmek için.  
  
Erişim için **uygulama** sayfası, proje düğümüne seçin (değil **çözüm** düğümü) içinde **Çözüm Gezgini**. Ardından **proje**, **özellikleri** menü çubuğunda. Proje Tasarımcısı görüntülendiğinde **uygulama** sekmesi.  
  
[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="general-application-settings"></a>Genel Uygulama ayarları  
 Aşağıdaki seçenekler, uygulama için genel ayarlarını yapılandırmak etkinleştirin.  
  
 **Derleme adı**  
 Derleme bildirimi barındıracak çıkış dosyasının adını belirtir. Bu özelliğin değiştirilmesi de değiştirir **çıktı adı** özelliği. Kullanarak, bu değişikliği komut satırından da yapabilirsiniz [/out (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/out-compiler-option). Bu özellik programlı olarak erişmek için bkz: <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.  
  
 **Varsayılan ad alanı**  
 Projeye eklenen dosyalar için temel ad alanını belirtir.  
  
 Bkz: [ad alanı](/dotnet/csharp/language-reference/keywords/namespace) kodunuzda ad alanları oluşturma hakkında daha fazla bilgi için.  
  
 Bu özellik programlı olarak erişmek için bkz: <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.  
  
 **Hedef çerçevesi**  
 .NET Framework sürümünü belirtir, uygulama hedefler. Bu seçenek bilgisayarınızda yüklü sürümlerini .NET Framework'ün bağlı olarak farklı değerlere sahip olabilir.  
  
 Varsayılan olarak, seçtiğiniz hedef Framework'ü aynı değer **yeni proje** iletişim kutusu.  
  
> [!NOTE]
>  Listelenen önkoşul [Önkoşullar iletişim kutusu](../../ide/reference/prerequisites-dialog-box.md) ilk kez iletişim kutusunu açtığınızda otomatik olarak ayarlanır. Projenin hedef çerçevesi daha sonra değiştirirseniz, yeni hedef Framework'ü el ile eşleşecek şekilde önkoşulları gerekecektir.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../../ide/how-to-target-a-version-of-the-dotnet-framework.md) ve [Visual Studio çoklu sürüm desteğine genel bakış](../../ide/visual-studio-multi-targeting-overview.md).  
  
 **Uygulama türü**  
 Derlenecek uygulamanın türünü belirtir. Windows 8.x uygulamaları için belirttiğiniz **Windows mağazası uygulaması**, **sınıf kitaplığı**, veya **WinMD dosyası**. Diğer birçok uygulama türleri için belirttiğiniz **Windows uygulaması**, **konsol uygulaması**, **sınıf kitaplığı**, **Windows hizmeti**, veya **Web kontrol Kitaplığı**.  
  
 Bir web uygulaması projesi için belirtmelisiniz **sınıf kitaplığı**.  
  
 Belirtirseniz **WinMD dosyası** seçeneği türleri tüm Windows çalışma zamanı programlama dili öngörülen. Proje çıktı WinMD dosyası olarak paketleme tarafından uygulamanın birden çok dilde kod ve gibi yazdıysanız çalışmanız koda sahip tüm aynı dilde. Windows çalışma zamanı kitaplıkları da dahil olmak üzere, hedef çözümleri için bu seçeneği belirleyebilirsiniz [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] uygulamalar. Daha fazla bilgi için bkz: [C# ve Visual Basic Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).  
  
> [!NOTE]
>  Windows çalışma zamanı, böylece bunları hangi dil kullanır yerel nesneler olarak görünürler türleri yansıtabilirsiniz. Örneğin, isteğe bağlı olarak Windows çalışma zamanı ile etkileşim JavaScript uygulamaları JavaScript nesne kümesi kullanın ve C# uygulamalarının kitaplığı .NET nesneleri bir koleksiyon olarak kullanın. Proje çıktı WinMD dosyası olarak paketleyerek Windows çalışma zamanı kullanan aynı teknolojisi yararlanabilir.  
  
 Hakkında daha fazla bilgi için **uygulama türü** özelliği, bkz: [/target (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/target-compiler-option). Bu özellik program aracılığıyla erişme hakkında daha fazla bilgi için bkz: <xref:VSLangProj.ProjectProperties.OutputType%2A>.  
  
 **Derleme bilgileri**  
 Bu düğmeye tıkladığınızda görüntüler [derleme bilgileri iletişim kutusu](../../ide/reference/assembly-information-dialog-box.md).  
  
 **Başlangıç nesnesi**  
 Uygulama yüklendiğinde çağrılacak giriş noktası tanımlar. Bu, uygulamanızın veya çok ana formuna ya da genellikle ayarlanır `Main` yordamı, uygulama başladığında çalıştırmanız gerekir. Sınıf kitaplıkları bir giriş noktası olmadığı için tek seçenektir bu özellik için **(ayarlanmamış)**.  
  
 Varsayılan olarak, WPF tarayıcı uygulaması projesinde, bu seçenek olan **(ayarlanmamış)**. Diğer seçenek *Projectname*. uygulama. Proje bu tür, uygulama başlatıldığında bir UI kaynak yüklemek için URI başlangıç ayarlamanız gerekir. Bunu yapmak için projenize Application.xaml dosyasını açın ve ayarlama `StartupUri` Window1.xaml gibi projenizi .xaml dosyasında özelliğine. Kabul edilebilir kök öğe listesi için bkz: <xref:System.Windows.Application.StartupUri%2A>. Tanımlamak de bir `public static void Main()` projede sınıfındaki yöntemi. Bu sınıf, görünür **Başlangıç nesnesi** olarak listesinde *ProjectName.ClassName*. Bu gibi durumlarda, sınıf sonra Başlangıç nesnesi olarak seçebilirsiniz.  
  
 Bkz: [/Main (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/main-compiler-option) daha fazla bilgi için. Bu özellik programlı olarak erişmek için bkz: <xref:VSLangProj.ProjectProperties.StartupObject%2A>.  
  
## <a name="resources"></a>Kaynaklar  
 Aşağıdaki seçenekler, uygulama için genel ayarlarını yapılandırmak etkinleştirin.  
  
 **Simge ve bildirim**  
 Varsayılan olarak, bu radyo düğmesi seçilir ve **simgesi** ve **bildirim** seçenekleri etkinleşir. Bu, kendi simgesini seçin ya da farklı bildirim üretme seçenekleri seçmenizi sağlar. Bu radyo düğmesi projesi için kaynak dosyası sağlama sürece seçili bırakın.  
  
 **Simgesi**  
 Program simgesi olarak kullanmak istediğiniz .ico dosyasını ayarlar. Varolan grafiği için göz atmak için üç nokta düğmesini tıklatın veya istediğiniz dosyanın adını yazın. Bkz: [/win32icon (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option) daha fazla bilgi için. Bu özellik programlı olarak erişmek için bkz: <xref:VSLangProj.ProjectProperties.ApplicationIcon%2A>.  
  
 **Bildirimi**  
 Windows Vista kullanıcı hesabı denetimi (UAC) altında uygulamayı çalıştırdığında, bildirim üretme seçeneğini seçer. Bu seçenek aşağıdaki değerlere sahip olabilir:  
  
-   **Varsayılan ayarlarla bildirimi katıştırmak**. Windows güvenlik bilgileri uygulamanın yürütülebilir dosyada katıştırmak için olan belirten Vista'da, Visual Studio faaliyet zamanki destekleyen `requestedExecutionLevel` olması `AsInvoker`. Varsayılan seçenek budur.  
  
-   **Bildirim olmadan uygulama oluşturma**. Bu yöntem olarak bilinen *sanallaştırma*. Önceki uygulamalarla uyumluluk için bu seçeneği kullanın.  
  
-   **Properties\app.manifest**. Bu seçenek ClickOnce veya Kayıtsız COM tarafından dağıtılan uygulamalar için gereklidir ClickOnce dağıtımı kullanarak bir uygulama yayımlarsanız **bildirim** için bu seçeneği otomatik olarak ayarlanır.  
  
**Kaynak dosyası**  
Projesi için kaynak dosyası sağlarken bu radyo düğmesini seçin. Bu seçeneğin devre dışı bırakır **simgesi** ve **bildirim** seçenekleri.  
  
Bir yol adı girin veya Gözat düğmesini kullanın (**...** ) Win32 kaynak dosyası projeye eklemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Uygulama özelliklerini yönetme](../../ide/application-properties.md)  
[Office çözümlerinde kod yazma](/office-dev/office-dev/writing-code-in-office-solutions)