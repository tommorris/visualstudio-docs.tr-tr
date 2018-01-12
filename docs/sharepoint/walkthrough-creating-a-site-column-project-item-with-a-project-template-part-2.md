---
title: "İzlenecek yol: Proje şablonu ile bir Site sütunu proje öğesi oluşturma, bölüm 2 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], creating template wizards
- SharePoint project items, creating template wizards
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: f0472688f9f36d2b14c89cc904bf6ce4badd6ca6
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2"></a>İzlenecek yol: bir proje şablonu, bölüm 2 ile bir Site sütunu proje öğesi oluşturma
  Özel bir SharePoint proje öğesi türü tanımlama ve Visual Studio Proje şablonu ilişkilendirmek sonra şablon için bir sihirbaz sağlamak isteyebilirsiniz. Proje öğesi içeren yeni bir proje oluşturmak için şablonunuzu kullanılırken kullanıcılardan bilgi toplamak için sihirbazı kullanabilirsiniz. Topladığınız bilgileri, proje öğesi başlatmak için kullanılabilir.  
  
 Bu kılavuzda, örnekte gösterildiği Site sütunu proje şablonu için bir sihirbaz ekleyecek [izlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md). Bir kullanıcı bir Site sütunu proje oluşturduğunda, sihirbazın site sütunu (örneğin, kendi temel türü ve grubun) hakkında bilgi toplar ve bu bilgileri yeni proje Elements.xml dosyasında ekler.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Proje şablonu ile ilişkilendirilen özel bir SharePoint proje öğesi türü için bir sihirbaz oluşturuluyor.  
  
-   Özel sihirbaz Visual Studio'da SharePoint projeleri için yerleşik sihirbazlar benzer UI tanımlama.  
  
-   İki oluşturma *SharePoint komutları* Sihirbazı çalışırken yerel SharePoint sitesine çağırmak için kullanılır. SharePoint, SharePoint sunucusu nesne modelinde API'leri çağırmak için Visual Studio uzantıları tarafından kullanılan yöntemleri komutlardır. Daha fazla bilgi için bkz: [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
-   SharePoint Proje Sihirbazı'nda topladığınız veri dosyalarıyla başlatmak için değiştirilebilir parametreler kullanma.  
  
-   Yeni bir .snk dosyası her yeni Site sütunu proje örnek oluşturuluyor. Bu dosya, SharePoint çözümü derleme genel derleme önbelleğine dağıtılabilir böylece çıkış proje imzalamak için kullanılır.  
  
-   Hata ayıklama ve Sihirbazı'nı test etme.  
  
> [!NOTE]  
>  Tamamlanan projeleri, kod ve bu kılavuz aşağıdaki konumdan diğer dosyalarını içeren bir örnek indirebilirsiniz: [http://go.microsoft.com/fwlink/?LinkId=191369](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda gerçekleştirmek için önce SiteColumnProjectItem çözüm tamamlayarak oluşturmalısınız [izlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).  
  
 Ayrıca bu yönlendirmeyi tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Windows, SharePoint ve Visual Studio sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK'sı. Bu kılavuzda kullanılır **VSIX proje** Şablonu proje öğesi dağıtmak için VSIX paket oluşturmak için SDK. Daha fazla bilgi için bkz: [genişletme Visual Studio'da SharePoint Araçları](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Aşağıdaki kavramlar bilgisi yararlı, ancak gerekli değildir, izlenecek yolu tamamlamak için:  
  
-   Sihirbazlar için Visual Studio Proje ve öğe şablonları. Daha fazla bilgi için bkz: [nasıl yapılır: Proje şablonlarıyla kullanma sihirbazları](../extensibility/how-to-use-wizards-with-project-templates.md) ve <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> arabirimi.  
  
-   SharePoint site sütunları. Daha fazla bilgi için bkz: [sütunları](http://go.microsoft.com/fwlink/?LinkId=183547).  
  
##  <a name="wizardcomponents"></a>Sihirbaz bileşenlerini anlama  
 Bu kılavuzda gösterilen Sihirbazı çeşitli bileşenleri içerir. Aşağıdaki tabloda, bu bileşenlerin açıklanmaktadır.  
  
|Bileşen|Açıklama|  
|---------------|-----------------|  
|Uygulama Sihirbazı|Adlı bir sınıf budur `SiteColumnProjectWizard`, hangi uygulayan <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> arabirimi. Bu arabirim Sihirbazı başlar ve tamamlandıktan sonra Sihirbazı sırasında belirli zamanlarda çalıştırdığında, Visual Studio çağıran yöntemleri tanımlar.|  
|Sihirbaz kullanıcı Arabirimi|Adlı bir WPF tabanlı pencere budur `WizardWindow`. Bu pencere adlı iki kullanıcı denetimleri içeren `Page1` ve `Page2`. Bu kullanıcı denetimleri Sihirbazı'nın iki sayfaları temsil eder.<br /><br /> Bu kılavuzda <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> sihirbaz uygulamasını yöntemi UI Sihirbazı görüntülenir.|  
|Veri modeli Sihirbazı|Adlı bir ara sınıf budur `SiteColumnWizardModel`, sihirbaz UI ve sihirbaz uygulamasını arasındaki bir katman sağlar. Bu örnek, sihirbaz uygulamasını ve sihirbazın UI birbirinden soyut yardımcı olması için bu sınıfı kullanır; Bu sınıf, gerekli bir bileşen tüm sihirbazları değil.<br /><br /> Bu kılavuzda, sihirbaz uygulamasını başarılı bir `SiteColumnWizardModel` UI Sihirbazı görüntülediğinde Sihirbazı penceresine nesne. Sihirbaz kullanıcı Arabirimi kullanıcı Arabiriminde, denetimlerinin değerlerini kaydetmek için ve giriş site URL'si geçerli olup olmadığını doğrulama gibi görevleri gerçekleştirmek için bu nesnenin yöntemleri kullanır. Kullanıcı sihirbazı tamamlandığında, sihirbaz uygulamasını kullanan `SiteColumnWizardModel` kullanıcı arabirimini son durumunu belirlemek için nesne.|  
|Proje imzalama Yöneticisi|Bu adlı bir yardımcı sınıf olan `ProjectSigningManager`, hangi Sihirbazı uygulaması tarafından her yeni proje örnek yeni bir key.snk dosyası oluşturmak için kullanılır.|  
|SharePoint komutları|Bu sihirbaz çalışırken yerel SharePoint sitesine çağırmak için sihirbaz veri modeli tarafından kullanılan yöntemleridir. SharePoint komutları .NET Framework 3.5 hedeflemesi gerekir çünkü bu komutları sihirbaz kodu kalanından farklı bir derlemede uygulanır.|  
  
## <a name="creating-the-projects"></a>Proje oluşturma  
 Bu izlenecek yolu tamamlamak için oluşturduğunuz SiteColumnProjectItem çözüm birkaç proje eklemeniz gerekir [izlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md):  
  
-   Bir WPF projesi. U uygulayacaksınız <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> arabirim ve kullanıcı Arabirimi Sihirbazı bu projede tanımlayın.  
  
-   SharePoint komutları tanımlayan bir sınıf kitaplığı proje. Bu proje.NET Framework 3.5 hedeflemesi gerekir.  
  
 İzlenecek yol projeleri oluşturarak başlayın.  
  
#### <a name="to-create-the-wpf-project"></a>WPF projesini oluşturmak için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], SiteColumnProjectItem çözümü açın.  
  
2.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SiteColumnProjectItem** çözüm düğümünü seçin **Ekle**ve ardından **yeni proje**.  
  
3.  Üstündeki **Yeni Proje Ekle** iletişim kutusunda, olduğundan emin olun **.NET Framework 4.5** .NET Framework sürümleri listesinde seçilir.  
  
4.  Genişletme **Visual C#** düğümü veya **Visual Basic** düğümü ve seçin **Windows** düğümü.  
  
5.  Proje şablonları listesinden seçip **WPF kullanıcı denetimi Kitaplığı**, proje adı **ProjectTemplateWizard**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **ProjectTemplateWizard** çözüme proje ve varsayılan da UserControl1.XAML'i dosyasını açar.  
  
6.  Da UserControl1.XAML'i dosyasını projeden silin.  
  
#### <a name="to-create-the-sharepoint-commands-project"></a>SharePoint komutları projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, SiteColumnProjectItem çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  Üstündeki **Yeni Proje Ekle** iletişim kutusunda, seçin **.NET Framework 3.5** .NET Framework sürümleri listesinde.  
  
3.  Genişletin **Visual C#** düğümü veya **Visual Basic** düğümünü ve ardından **Windows** düğümü.  
  
4.  Seçin **sınıf kitaplığı** proje şablonu, proje adı **SharePointCommands**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **SharePointCommands** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
5.  Class1 kod dosyasının projeden silin.  
  
## <a name="configuring-the-projects"></a>Projeleri yapılandırma  
 Sihirbaz oluşturmadan önce biraz kod dosyaları ve projeler derleme başvurularını eklemeniz gerekir.  
  
#### <a name="to-configure-the-wizard-project"></a>Sihirbaz projesini yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ProjectTemplateWizard** proje düğümünü ve ardından **özellikleri**.  
  
2.  İçinde **Proje Tasarımcısı**, seçin **uygulama** bir Visual C# projesi için sekme veya **derleme** Visual Basic projesinde sekmesi.  
  
3.  Hedef çerçevesini .NET Framework 4.5 değil .NET Framework 4.5 istemci profili ayarlandığından emin olun.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
4.  Kısayol menüsünü açın **ProjectTemplateWizard** seçin, proje **Ekle**ve ardından **yeni öğe**.  
  
5.  Seçin **penceresi (WPF)** öğesi, öğenin adı **WizardWindow**ve ardından **Ekle** düğmesi.  
  
6.  İki eklemek **kullanıcı denetimi (WPF)** proje öğeleri ve bunları **Page1** ve **Page2**.  
  
7.  Projeye dört kod dosyaları ekleyin ve bunları aşağıdaki adlar verin:  
  
    -   SiteColumnProjectWizard  
  
    -   SiteColumnWizardModel  
  
    -   ProjectSigningManager  
  
    -   CommandIds  
  
8.  Kısayol menüsünü açın **ProjectTemplateWizard** proje düğümünü ve ardından **Başvuru Ekle**.  
  
9. Genişletme **derlemeler** düğümü seçin **uzantıları** düğümü ve aşağıdaki derlemeler yanındaki onay kutularını seçin:  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.OLE.Interop  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.Shell.Interop.10.0  
  
    -   Microsoft.VisualStudio.Shell.Interop.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
10. Seçin **Tamam** derlemeler projeye eklemek için düğmesi.  
  
11. İçinde **Çözüm Gezgini**altında **başvuruları** için klasör **ProjectTemplateWizard** seçin, proje **EnvDTE**.  
  
12. İçinde **özellikleri** penceresinde değerini değiştirme **birlikte çalışma türlerini katıştır** özelliğine **False**.  
  
13. Visual Basic projesinde geliştiriyorsanız ProjectTemplateWizard ad alanı, projeye kullanarak içeri **Proje Tasarımcısı**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: ekleme veya içeri aktarılan ad alanları &#40; Kaldır Visual Basic &#41; ](../ide/how-to-add-or-remove-imported-namespaces-visual-basic.md).  
  
#### <a name="to-configure-the-sharepointcommands-project"></a>SharePointCommands projeyi yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, seçin **SharePointCommands** proje düğümüne.  
  
2.  Menü çubuğunda seçin **proje**, **varolan öğeyi Ekle**.  
  
3.  İçinde **varolan öğeyi Ekle** iletişim kutusu, ProjectTemplateWizard projesi için kod dosyaları içeren klasöre gidin ve ardından **CommandIds** kod dosyası.  
  
4.  Oku seçin **Ekle** düğmesine tıklayın ve ardından **bağlantı olarak Ekle** seçeneği menüsünde görüntülenir.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]kod dosyasına ekler **SharePointCommands** projesi bir bağlantı olarak. Kod dosyası bulunan **ProjectTemplateWizard** proje ancak dosyasındaki kodu aynı zamanda derlenmiş içinde **SharePointCommands** projesi.  
  
5.  İçinde **SharePointCommands** projesi, komutları adlı başka bir kod dosyası ekleyin.  
  
6.  SharePointCommands projesini seçin ve ardından, menü çubuğunda, **proje**, **Başvuru Ekle**.  
  
7.  Genişletme **derlemeler** düğümü seçin **uzantıları** düğümü ve aşağıdaki derlemeler yanındaki onay kutularını seçin:  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
8.  Seçin **Tamam** derlemeler projeye eklemek için düğmesi.  
  
## <a name="creating-the-wizard-model-signing-manager-and-sharepoint-command-ids"></a>Yöneticisi ve SharePoint komut kimlikleri imzalama Sihirbazı Model oluşturma  
 Aşağıdaki bileşenler örnekte uygulamak için ProjectTemplateWizard projeye kodu ekleyin:  
  
-   SharePoint komut kimlikleri. Bu dizeler Sihirbazı'nı kullanan SharePoint komutları tanımlayın. Bu kılavuzda daha sonra komutları uygulamak için SharePointCommands projesi için kod ekleyeceksiniz.  
  
-   Sihirbaz veri modeli.  
  
-   Proje imzalama Yöneticisi.  
  
 Bu bileşenler hakkında daha fazla bilgi için bkz: [Sihirbazı bileşenlerini anlama](#wizardcomponents).  
  
#### <a name="to-define-the-sharepoint-command-ids"></a>SharePoint komut kimlikleri tanımlamak için  
  
1.  ProjectTemplateWizard proje CommandIds kod dosyasını açın ve ardından bu dosyanın tüm içeriğini aşağıdaki kodla değiştirin.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#5](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/commandids.cs#5)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#5](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/commandids.vb#5)]  
  
#### <a name="to-create-the-wizard-model"></a>Sihirbaz modeli oluşturmak için  
  
1.  SiteColumnWizardModel kod dosyasını açın ve bu dosyanın tüm içeriğini aşağıdaki kodla değiştirin.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#6](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/sitecolumnwizardmodel.vb#6)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#6](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/sitecolumnwizardmodel.cs#6)]  
  
#### <a name="to-create-the-project-signing-manager"></a>Proje imzalama Yöneticisi oluşturmak için  
  
1.  ProjectSigningManager kod dosyasını açın ve ardından bu dosyanın tüm içeriğini aşağıdaki kodla değiştirin.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#8](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/projectsigningmanager.vb#8)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#8](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/projectsigningmanager.cs#8)]  
  
## <a name="creating-the-wizard-ui"></a>Sihirbaz kullanıcı Arabirimi oluşturma  
 UI Sihirbazı penceresinin ve sihirbaz sayfaları için kullanıcı Arabirimi sağlayan iki kullanıcı denetimini tanımlamak için XAML ekleyin ve pencere ve kullanıcı denetimleri davranışını tanımlamak için kodu ekleyin. Visual Studio'da SharePoint projeleri için yerleşik Sihirbazı, Oluşturma Sihirbazı'nı benzer.  
  
> [!NOTE]  
>  XAML veya kod projenize ekledikten sonra aşağıdaki adımlarda bazı derleme hataları projenizi sahip olur. Sonraki adımlarda kodu eklediğinizde, bu hataları kaybolur.  
  
#### <a name="to-create-the-wizard-window-ui"></a>Sihirbazdan kullanıcı Arabirimi oluşturmak için  
  
1.  ProjectTemplateWizard projesinde WizardWindow.xaml dosya için kısayol menüsünü açın ve ardından **açmak** Tasarımcısı'nda penceresini açın.  
  
2.  Tasarımcı XAML görünümünde geçerli XAML aşağıdaki XAML ile değiştirin. XAML bir başlık içeren bir kullanıcı Arabirimi tanımlayan bir <xref:System.Windows.Controls.Grid> , sihirbazın sonraki sayfalarında içeren ve gezinti düğmeleri penceresinin alt kısmında.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#10](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml#10)]  
  
    > [!NOTE]  
    >  Bu XAML'de oluşturulan pencerenin türetilir <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> temel sınıfı. Visual Studio için özel bir WPF iletişim kutusu eklediğinizde, iletişim kutusu diğer Visual Studio iletişim kutuları ile tutarlı stil sağlamak için ve aksi durumda oluşabilecek modal iletişim sorunlarını önlemek için bu sınıftan türetilen öneririz. Daha fazla bilgi için bkz: [oluşturma ve yönetme kalıcı iletişim kutuları](/visualstudio/extensibility/creating-and-managing-modal-dialog-boxes).  
  
3.  Visual Basic projesinde geliştiriyorsanız kaldırmak `ProjectTemplateWizard` ad alanından `WizardWindow` sınıf adında `x:Class` özniteliği `Window` öğesi. XAML ilk satırda öğedir. İşiniz bittiğinde, ilk satırın aşağıdaki örnekteki gibi görünmelidir.  
  
    ```  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  WizardWindow.xaml dosyası için arka plan kodu dosyasını açın.  
  
5.  Bu dosyanın içeriğini dışında Değiştir `using` bildirimlerini dosyanın üst kısmındaki, aşağıdaki kod ile.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#4](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml.vb#4)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#4](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/wizardwindow.xaml.cs#4)]  
  
#### <a name="to-create-the-first-wizard-page-ui"></a>İlk sihirbaz sayfası kullanıcı Arabirimi oluşturmak için  
  
1.  ProjectTemplateWizard projesindeki Page1.xaml dosya için kısayol menüsünü açın ve ardından **açmak** kullanıcı denetimi Tasarımcısı'nda açmak için.  
  
2.  Tasarımcı XAML görünümünde geçerli XAML aşağıdaki XAML ile değiştirin. XAML hata ayıklama için kullanmak istedikleri yerel siteleri URL'sini girebilecekleri bir metin kutusu içeren bir kullanıcı Arabirimi tanımlar. Kullanıcı Arabirimi ile kullanıcılar proje korumalı olup olmadığını belirtebileceğiniz seçenek düğmeleri de içerir.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#11](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/page1.xaml#11)]  
  
3.  Visual Basic projesinde geliştiriyorsanız kaldırmak `ProjectTemplateWizard` ad alanından `Page1` sınıf adında `x:Class` özniteliği `UserControl` öğesi. XAML ilk satırda budur. İşiniz bittiğinde, ilk satırı aşağıdaki gibi görünmelidir.  
  
    ```  
    <UserControl x:Class="Page1"  
    ```  
  
4.  Dışında Page1.xaml dosyasının içeriğini değiştirin `using` ile aşağıdaki kodu dosyanın üst bildirimleri.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#2](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/page1.xaml.vb#2)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#2](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/page1.xaml.cs#2)]  
  
#### <a name="to-create-the-second-wizard-page-ui"></a>İkinci sihirbaz sayfası kullanıcı Arabirimi oluşturmak için  
  
1.  ProjectTemplateWizard projesinde Page2.xaml dosya için kısayol menüsünü açın ve ardından **açmak**.  
  
     Kullanıcı denetimi Tasarımcısı'nda açılır.  
  
2.  XAML Görünümü'nde geçerli XAML aşağıdaki XAML ile değiştirin. XAML site sütunu, altında çalışacağı galeride site sütunu görüntülemek yerleşik veya özel bir grup belirtmek için açılan kutu ve site sütununun adını belirtmek için bir metin kutusu temel türünü seçmek için aşağı açılan listesini içeren bir kullanıcı Arabirimi tanımlar.  
  
     [!code-xml[SPExtensibility.ProjectItem.SiteColumn#12](../sharepoint/codesnippet/Xaml/sitecolumnprojectitem/projecttemplatewizard/page2.xaml#12)]  
  
3.  Visual Basic projesinde geliştiriyorsanız kaldırmak `ProjectTemplateWizard` ad alanından `Page2` sınıf adında `x:Class` özniteliği `UserControl` öğesi. XAML ilk satırda budur. İşiniz bittiğinde, ilk satırı aşağıdaki gibi görünmelidir.  
  
    ```  
    <UserControl x:Class="Page2"  
    ```  
  
4.  Dışında Page2.xaml dosyası için arka plan kod dosyasının içeriğini değiştirin `using` ile aşağıdaki kodu dosyanın üst bildirimleri.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#3](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/page2.xaml.vb#3)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#3](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/page2.xaml.cs#3)]  
  
## <a name="implementing-the-wizard"></a>Uygulama Sihirbazı  
 Sihirbaz ana işlevselliğini uygulayarak tanımlama <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> arabirimi. Bu arabirim Sihirbazı başlar ve tamamlandıktan sonra Sihirbazı sırasında belirli zamanlarda çalıştırdığında, Visual Studio çağıran yöntemleri tanımlar.  
  
#### <a name="to-implement-the-wizard"></a>Sihirbazı'nı uygulamak için  
  
1.  ProjectTemplateWizard projesinde SiteColumnProjectWizard kod dosyasını açın.  
  
2.  Bu dosyanın tüm içeriğini aşağıdaki kodla değiştirin.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#7](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projecttemplatewizard/sitecolumnprojectwizard.vb#7)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#7](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projecttemplatewizard/sitecolumnprojectwizard.cs#7)]  
  
## <a name="creating-the-sharepoint-commands"></a>SharePoint komutları oluşturma  
 SharePoint sunucusu nesne modeline çağrılan iki özel komutlar oluşturun. Bir komutu kullanıcının Sihirbazı'nda türleri site URL'si geçerli olup olmadığını belirler. Kullanıcılar kendi yeni site sütunu için temel olarak kullanmak için hangi birini seçebilmeniz için diğer komutu tüm alan türleri belirtilen SharePoint sitesinden alır.  
  
#### <a name="to-define-the-sharepoint-commands"></a>SharePoint komutları tanımlamak için  
  
1.  İçinde **SharePointCommands** projesi, komutları kod dosyasını açın.  
  
2.  Bu dosyanın tüm içeriğini aşağıdaki kodla değiştirin.  
  
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#9](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/sharepointcommands/commands.vb#9)]
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#9](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/sharepointcommands/commands.cs#9)]  
  
## <a name="checkpoint"></a>Denetim noktası  
 Bu noktada kılavuzda Sihirbazı'nın tüm kod projesinde sunulmuştur. Hatasız derlendiğinden emin olmak için projeyi oluşturun.  
  
#### <a name="to-build-your-project"></a>Projenizi yapılandırmak için  
  
1.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
## <a name="removing-the-keysnk-file-from-the-project-template"></a>Proje şablonu key.snk dosya kaldırılıyor  
 İçinde [izlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md), her bir Site sütunu proje örneği imzalamak için kullanılan bir key.snk dosyası oluşturduğunuz proje şablonu içerir. Sihirbaz şimdi her proje için yeni bir key.snk dosyası oluşturduğundan bu key.snk dosya artık gerekli değildir. Proje şablonu key.snk dosya kaldırın ve bu dosyaya başvuruları kaldırın.  
  
#### <a name="to-remove-the-keysnk-file-from-the-project-template"></a>Proje şablonu key.snk dosyayı kaldırmak için  
  
1.  İçinde **Çözüm Gezgini**altında **SiteColumnProjectTemplate** düğümü için kısayol menüsünü açın **key.snk** dosya ve ardından **Sil**.  
  
2.  Görüntülenen onay iletişim kutusunda seçin **Tamam** düğmesi.  
  
3.  Altında **SiteColumnProjectTemplate** düğümü, SiteColumnProjectTemplate.vstemplate dosyasını açın ve ardından aşağıdaki öğeyi buradan kaldırın.  
  
    ```  
    <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
    ```  
  
4.  Dosyayı kaydedin ve kapatın.  
  
5.  Altında **SiteColumnProjectTemplate** düğümü, ProjectTemplate.csproj veya ProjectTemplate.vbproj dosyasını açın ve ardından aşağıdaki kaldırın `PropertyGroup` onu öğesinden.  
  
    ```  
    <PropertyGroup>  
      <SignAssembly>true</SignAssembly>  
      <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
    </PropertyGroup>  
    ```  
  
6.  Aşağıdaki kaldırmak `None` öğesi.  
  
    ```  
    <None Include="key.snk" />  
    ```  
  
7.  Dosyayı kaydedin ve kapatın.  
  
## <a name="associating-the-wizard-with-the-project-template"></a>Sihirbazı proje şablonu ile ilişkilendirme  
 Sihirbaz uyguladıysanız, Sihirbazı ile ilişkilendirmeniz gerekir **Site sütunu** proje şablonu. Bunu yapmak için tamamlamanız gereken üç yordamı vardır:  
  
1.  Sihirbazı derlemeyi tanımlayıcı adla oturum açın.  
  
2.  Sihirbazı derleme için ortak anahtar belirteci alın.  
  
3.  .Vstemplate dosyasında Sihirbazı derlemesine başvuru ekleyin **Site sütunu** proje şablonu.  
  
#### <a name="to-sign-the-wizard-assembly-with-a-strong-name"></a>Sihirbaz derlemeyi tanımlayıcı adla imzalamak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ProjectTemplateWizard** proje ve ardından **özellikleri**.  
  
2.  Üzerinde **imzalama** sekmesine **derlemeyi imzalamak** onay kutusu.  
  
3.  İçinde **güçlü ad anahtar dosyası seçin** listesinde, seçin  **\<yeni... >**.  
  
4.  İçinde **güçlü ad anahtarı oluştur** iletişim kutusunda, yeni anahtar dosyası için bir ad temizleyin girin **my anahtar dosyasını bir parola ile koruyun** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
5.  Kısayol menüsünü açın **ProjectTemplateWizard** proje ve ardından **yapı** ProjectTemplateWizard.dll dosyası oluşturmak için.  
  
#### <a name="to-get-the-public-key-token-for-the-wizard-assembly"></a>Sihirbazı derleme için ortak anahtar belirteci almak için  
  
1.  Üzerinde **Başlat menüsü**, seçin **tüm programlar**, seçin **Microsoft Visual Studio**, seçin **Visual Studio Araçları**ve ardından seçin **Geliştirici komut istemi**.  
  
     Visual Studio komut istemi penceresi açılır.  
  
2.  Aşağıdaki komutu çalıştırın değiştirme *PathToWizardAssembly* geliştirme bilgisayarınızda ProjectTemplateWizard projesi için yerleşik ProjectTemplateWizard.dll derleme tam yoluna sahip:  
  
    ```  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     Ortak anahtar belirteci ProjectTemplateWizard.dll derleme için Visual Studio komut istemi penceresine yazılır.  
  
3.  Visual Studio komut istemi penceresini açık tutun. Sonraki yordam sırasında ortak anahtar belirteci gerekir.  
  
#### <a name="to-add-a-reference-to-the-wizard-assembly-in-the-vstemplate-file"></a>.Vstemplate dosyasında Sihirbazı derlemesine başvuru eklemek için  
  
1.  İçinde **Çözüm Gezgini**, genişletin **SiteColumnProjectTemplate** proje düğümünü ve SiteColumnProjectTemplate.vstemplate dosyasını açın.  
  
2.  Dosyanın sonuna yakın aşağıdakileri ekleyin `WizardExtension` öğesi arasında `</TemplateContent>` ve `</VSTemplate>` etiketler. Değiştir *belirtecinizi* değerini `PublicKeyToken` özniteliği önceki yordamda edinilen ortak anahtar belirteci ile.  
  
    ```  
    <WizardExtension>  
      <Assembly>ProjectTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=your token</Assembly>  
      <FullClassName>ProjectTemplateWizard.SiteColumnProjectWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     Hakkında daha fazla bilgi için `WizardExtension` öğesi, bkz: [WizardExtension öğesi &#40; Visual Studio şablonları &#41; ](/visualstudio/extensibility/wizardextension-element-visual-studio-templates).  
  
3.  Dosyayı kaydedin ve kapatın.  
  
## <a name="adding-replaceable-parameters-to-the-elementsxml-file-in-the-project-template"></a>Proje şablonu Elements.xml dosyasında değiştirilebilir parametreler ekleme  
 Birkaç değiştirilebilir parametreler SiteColumnProjectTemplate projesinde Elements.xml dosyasına ekleyin. Bu parametreler olarak başlatılır `RunStarted` yönteminde `SiteColumnProjectWizard` daha önce tanımlanan sınıfı. Bir kullanıcı bir Site sütunu proje oluşturduğunda, Visual Studio yeni proje Elements.xml dosyasında bu parametreler Sihirbazı'nda belirtilen değerlerle otomatik olarak değiştirir.  
  
 Bir parametredir başlayıp dolar işareti ($) karakteri ile biten bir belirteçtir. Kendi değiştirilebilir parametreler tanımlamanın yanı sıra, tanımlanır ve SharePoint Proje sistem tarafından başlatılan yerleşik parametreleri kullanabilirsiniz. Daha fazla bilgi için bkz: [değiştirilebilir parametreler](../sharepoint/replaceable-parameters.md).  
  
#### <a name="to-add-replaceable-parameters-to-the-elementsxml-file"></a>Değiştirilebilir parametreler Elements.xml dosyasına eklemek için  
  
1.  SiteColumnProjectTemplate projesinde Elements.xml dosyasının içeriğini aşağıdaki XML ile değiştirin.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <Field ID="{$guid5$}"   
             Name="$fieldname$"   
             DisplayName="$fieldname$"   
             Type="$selectedfieldtype$"   
             Group="$selectedgrouptype$">  
      </Field>  
    </Elements>  
    ```  
  
     Yeni XML değerlerini değiştirir `Name`, `DisplayName`, `Type`, ve `Group` öznitelikleri için özel değiştirilebilir parametreler.  
  
2.  Dosyayı kaydedin ve kapatın.  
  
## <a name="adding-the-wizard-to-the-vsix-package"></a>VSIX Paketi Sihirbazı'nı ekleme  
 Sihirbazı'nı Site sütunu proje şablonu içeren VSIX paketi ile dağıtmak için VSIX proje source.extension.vsixmanifest dosyasında Sihirbazı proje ve SharePoint komutları proje başvuruları ekleyin.  
  
#### <a name="to-add-the-wizard-to-the-vsix-package"></a>VSIX Paketi Sihirbazı'nı eklemek için  
  
1.  İçinde **Çözüm Gezgini**, **SiteColumnProjectItem** proje, kısayol menüsünü açın **source.extension.vsixmanifest** dosya ve ardından **Açık**.  
  
     Visual Studio bildirim düzenleyicisinde dosyasını açar.  
  
2.  Üzerinde **varlıklar** sekmesini Düzenleyicisi, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
3.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.Assembly**.  
  
4.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
5.  İçinde **proje** listesinde, seçin **ProjectTemplateWizard**ve ardından **Tamam** düğmesi.  
  
6.  Üzerinde **varlıklar** sekmesini Düzenleyicisi, seçin **yeni** yeniden düğmesine tıklayın.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
7.  İçinde **türü** listesinde, girin **SharePoint.Commands.v4**.  
  
8.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
9. İçinde **proje** listesinde, seçin **SharePointCommands** proje ve ardından **Tamam** düğmesi.  
  
10. Menü çubuğunda seçin **yapı**, **yapı çözümü**ve çözümünüzün hatasız oluşturulduğunu doğrulayın.  
  
## <a name="testing-the-wizard"></a>Sihirbazı'nı test etme  
 Artık Sihirbazı'nı test etmek hazırsınız. İlk olarak, Visual Studio'nun deneysel örneği SiteColumnProjectItem çözümde hata ayıklamayı Başlat. Ardından, Visual Studio deneysel örneğinde Site sütunu Proje Sihirbazı'nı test edin. Son olarak, yapı ve site sütunu beklendiği gibi çalıştığını doğrulamak için projesini çalıştırın.  
  
#### <a name="to-start-debugging-the-solution"></a>Çözüm hata ayıklamayı başlatmak için  
  
1.  Yönetici kimlik bilgileriyle Visual Studio'yu yeniden başlatın ve ardından SiteColumnProjectItem çözümü açın.  
  
2.  ProjectTemplateWizard projesinde SiteColumnProjectWizard kod dosyasını açın ve daha sonra bir kesme noktası kod ilk satırı ekleyin `RunStarted` yöntemi.  
  
3.  Menü çubuğunda seçin **hata ayıklama**, **özel durumları**.  
  
4.  İçinde **özel durumları** iletişim kutusunda, olduğundan emin olun **sayıcı** ve **kullanıcı işlenmemiş** onay kutularını **ortak dil çalışma zamanı özel durumları**temizlenir ve ardından **Tamam** düğmesi.  
  
5.  Seçerek hata ayıklamayı Başlat **F5** anahtar veya menü çubuğu seçme **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
     Visual Studio %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Site Column\1.0 uzantıyı yükleyen ve Visual Studio Deneysel bir örneğini başlatır. Proje öğesi Visual Studio'nun bu örneği test edeceksiniz.  
  
#### <a name="to-test-the-wizard-in-visual-studio"></a>Visual Studio'da Sihirbazı'nı test etme  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **dosya**, **yeni**, **proje**.  
  
2.  Genişletin **Visual C#** düğümü veya **Visual Basic** düğümünü (bağlı olarak, proje şablonu destekleyen dil), **SharePoint** düğümünü ve ardından seçin **2010** düğümü.  
  
3.  Proje şablonları listesinden seçip **Site sütunu**, proje adı **SiteColumnWizardTest**ve ardından **Tamam** düğmesi.  
  
4.  Visual Studio'nun diğer örnek kodda, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `RunStarted` yöntemi.  
  
5.  Seçerek projenin hata ayıklamasını devam **F5** anahtar veya menü çubuğu seçme **hata ayıklama**, **devam**.  
  
6.  İçinde **SharePoint Özelleştirme Sihirbazı'nı**hata ayıklama için kullanmak istediğiniz sitenin URL'sini girin ve ardından **sonraki** düğmesi.  
  
7.  İkinci sayfasındaki **SharePoint Özelleştirme Sihirbazı'nı**, aşağıdaki seçimleri yapın:  
  
    -   İçinde **türü** listesinde, seçin **Boolean**.  
  
    -   İçinde **grup** listesinde, seçin **özel Hayır sütunları**.  
  
    -   İçinde **adı** kutusuna **My Hayır sütun**ve ardından **son** düğmesi.  
  
     İçinde **Çözüm Gezgini**, yeni bir proje görünür ve adlı bir proje öğesi içeren **alan1**, ve Visual Studio düzenleyicisinde projenin Elements.xml dosyasını açar.  
  
8.  Elements.XML Sihirbazı'nda belirtilen değerleri içerdiğini doğrulayın.  
  
#### <a name="to-test-the-site-column-in-sharepoint"></a>SharePoint site sütunu sınamak için  
  
1.  Visual Studio deneysel örneğinde F5 tuşuna seçin.  
  
     Site sütunu paketlenir ve SharePoint'e dağıtılan sitenin **Site URL'si** projesinin özelliği belirtir. Web tarayıcısı bu sitenin varsayılan sayfasını açar.  
  
    > [!NOTE]  
    >  Varsa **komut dosyası hata ayıklama devre dışı** seçin iletişim kutusu görüntülenirse, **Evet** projede hataları ayıklamak devam düğmesine.  
  
2.  Üzerinde **Site eylemleri** menüsünde seçin **Site Ayarları**.  
  
3.  Site Ayarları sayfasında altında **galerileri**, seçin **Site sütunları** bağlantı.  
  
4.  Site sütunları listesinde doğrulayın bir **özel Hayır sütunları** adlı bir sütun içeren grubu **My Hayır sütun**ve web tarayıcısı kapatın.  
  
## <a name="cleaning-up-the-development-computer"></a>Geliştirme bilgisayarı temizleme  
 Proje öğesi testi tamamladıktan sonra proje şablonu Visual Studio Deneysel örnekten kaldırın.  
  
#### <a name="to-clean-up-the-development-computer"></a>Geliştirme bilgisayarı temizlemek için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantıları listesinden seçip **Site sütunu**ve ardından **kaldırma** düğmesi.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** uzantısı kaldırın ve ardından istediğinizi onaylamak için düğmesini **şimdi yeniden Başlat** kaldırma işleminin tamamlanması için düğmesi.  
  
4.  Visual Studio'nun deneysel örneği ve CustomActionProjectItem çözüm açıksa örneği kapatın.  
  
     Nasıl dağıtılacağı hakkında bilgi için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantıları bkz [sevkiyat Visual Studio uzantıları](/visualstudio/extensibility/shipping-visual-studio-extensions).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint Proje öğeleri için öğe şablonları ve proje şablonları oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Visual Studio Şablon Şeması Başvurusu](/visualstudio/extensibility/visual-studio-template-schema-reference)   
 [Nasıl Yapılır: Sihirbazları Proje Şablonlarıyla Kullanma](../extensibility/how-to-use-wizards-with-project-templates.md)  
  
  