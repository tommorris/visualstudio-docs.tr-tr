---
title: "İzlenecek yol: bir özel eylem proje öğesi ile bir öğe şablonu, bölüm 2 oluşturma | Microsoft Docs"
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
ms.assetid: 2d8165d3-4af9-4a5e-bdba-8b2a06b1dc8d
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b12a52101feebcfac08c7672834d9d7c65d41c55
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2"></a>İzlenecek yol: Öğe Şablonu, Bölüm 2 ile Özel bir Eylem Proje Öğesi Oluşturma
  Özel bir SharePoint proje öğesi türü tanımlama ve Visual Studio öğe şablonunda ilişkilendirmek sonra şablon için bir sihirbaz sağlamak isteyebilirsiniz. Yeni bir proje öğesi örneğini bir projeye eklemek için şablon kullanılırken kullanıcılardan bilgi toplamak için sihirbazı kullanabilirsiniz. Topladığınız bilgileri, proje öğesi başlatmak için kullanılabilir.  
  
 Bu kılavuzda, örnekte gösterildiği özel eylem proje öğesi için bir sihirbaz ekleyecek [izlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md). Bir kullanıcı bir SharePoint projesine bir özel eylem proje öğesi eklediğinde, Sihirbazı'nı özel eylemi (örneğin, konumunu ve son kullanıcının seçtiğinde gitmek için URL'sini) hakkında bilgi toplar ve bu bilgileri Elements.xml dosyasına yeni ekler Proje öğesi.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Bir öğe şablonuyla ilişkili özel bir SharePoint proje öğesi türü için bir sihirbaz oluşturuluyor.  
  
-   Özel sihirbaz Visual Studio'da SharePoint Proje öğeleri için yerleşik sihirbazlar benzer UI tanımlama.  
  
-   SharePoint Proje Sihirbazı'nda topladığınız veri dosyalarıyla başlatmak için değiştirilebilir parametreler kullanma.  
  
-   Hata ayıklama ve Sihirbazı'nı test etme.  
  
> [!NOTE]  
>  Tamamlanan projeleri, kod ve bu kılavuz aşağıdaki konumdan diğer dosyalarını içeren bir örnek indirebilirsiniz: [SharePoint araçları genişletilebilirliği talimatlar için proje dosyalarını](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda gerçekleştirmek için önce CustomActionProjectItem çözüm tamamlayarak oluşturmalısınız [izlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  
  
 Ayrıca bu yönlendirmeyi tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Windows, SharePoint ve Visual Studio sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK'sı. Bu kılavuzda kullanılır **VSIX proje** Şablonu proje öğesi dağıtmak için VSIX paket oluşturmak için SDK. Daha fazla bilgi için bkz: [genişletme Visual Studio'da SharePoint Araçları](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Aşağıdaki kavramlar bilgisi yararlı, ancak gerekli değildir, izlenecek yolu tamamlamak için:  
  
-   Sihirbazlar için Visual Studio Proje ve öğe şablonları. Daha fazla bilgi için bkz: [nasıl yapılır: Proje şablonlarıyla kullanma sihirbazları](../extensibility/how-to-use-wizards-with-project-templates.md) ve <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> arabirimi.  
  
-   Özel eylemler SharePoint. Daha fazla bilgi için bkz: [özel eylem](http://go.microsoft.com/fwlink/?LinkId=177800).  
  
## <a name="creating-the-wizard-project"></a>Sihirbaz projesi oluşturma  
 Bu izlenecek yolu tamamlamak için bir proje oluşturduğunuz CustomActionProjectItem çözüme eklemelisiniz [izlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md). U uygulayacaksınız <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> arabirim ve kullanıcı Arabirimi Sihirbazı bu projede tanımlayın.  
  
#### <a name="to-create-the-wizard-project"></a>Sihirbazı proje oluşturmak için  
  
1.  Visual Studio'da CustomActionProjectItem çözümü açın  
  
2.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
3.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **Windows** düğümü.  
  
4.  Üstündeki **yeni proje** iletişim kutusunda, olduğundan emin olun **.NET Framework 4.5** .NET Framework sürümleri listesinde seçilir.  
  
5.  Seçin **WPF kullanıcı denetimi Kitaplığı** proje şablonu, proje adı **ItemTemplateWizard**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **ItemTemplateWizard** çözüme proje.  
  
6.  UserControl1 öğeyi projeden silin.  
  
## <a name="configuring-the-wizard-project"></a>Sihirbaz projesini yapılandırma  
 Sihirbaz oluşturmadan önce bir Windows Presentation Foundation (WPF) penceresi, kod dosyası ve derleme referanslarını projeye eklemeniz gerekir.  
  
#### <a name="to-configure-the-wizard-project"></a>Sihirbaz projesini yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünden açmak **ItemTemplateWizard** proje düğümünü ve ardından **özellikleri**.  
  
2.  İçinde **Proje Tasarımcısı**, hedef çerçevesini .NET Framework 4.5 ayarlandığından emin olun.  
  
     Visual C# projeleri için bu değeri üzerinde ayarlayabilirsiniz **uygulama** sekmesi. Visual Basic projeleri için bu değer ayarlayabilirsiniz **derleme** sekmesi. Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
3.  İçinde **ItemTemplateWizard** proje, ekleme bir **penceresi (WPF)** öğesi proje ve öğe adı **WizardWindow**.  
  
4.  CustomActionWizard ve dizeleri adlı iki kod dosyaları ekleyin.  
  
5.  Kısayol menüsünü açın **ItemTemplateWizard** proje ve ardından **Başvuru Ekle**.  
  
6.  İçinde **başvuru Yöneticisi - ItemTemplateWizard** iletişim kutusunda **derlemeleri** düğümü seçin **uzantıları** düğümü.  
  
7.  Aşağıdaki derlemeler yanındaki onay kutularını seçin ve ardından **Tamam** düğmesi:  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
8.  İçinde **Çözüm Gezgini**, **başvuruları** ItemTemplateWizard proje için klasörü seçin **EnvDTE** başvuru.  
  
9. İçinde **özellikleri** penceresinde değerini değiştirme **birlikte çalışma türlerini katıştır** özelliğine **False**.  
  
## <a name="defining-the-default-location-and-id-strings-for-custom-actions"></a>Özel Eylemler için varsayılan konum ve kimlik dizeleri tanımlama  
 Her özel bir konum ve belirtilen kimliği eyleminin `GroupID` ve `Location` özniteliklerini `CustomAction` Elements.xml dosyasındaki öğesi. Bu adımda, bazı ItemTemplateWizard proje içinde bu özniteliklerin için geçerli dizeleri tanımlayın. Bu kılavuzu tamamladıktan sonra kullanıcılar Sihirbazı'nda bir konum ve kimlik belirttiğinizde bu dizeler özel eylem proje öğesi Elements.xml dosyasına yazılır.  
  
 Kolaylık olması için bu örnek yalnızca bir alt kimlikleri ve kullanılabilir varsayılan konumları destekler. Tam listesi için bkz: [varsayılan özel eylem konumları ve kimlikleri](http://go.microsoft.com/fwlink/?LinkId=181964).  
  
#### <a name="to-define-the-default-location-and-id-strings"></a>Varsayılan konum ve kimlik dizeleri tanımlamak için  
  
1.  açın.  
  
2.  İçinde **ItemTemplateWizard** projesi, dizeleri kod dosyasındaki kodu aşağıdaki kodla değiştirin.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#6](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/strings.cs#6)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#6](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/strings.vb#6)]  
  
## <a name="creating-the-wizard-ui"></a>Sihirbaz kullanıcı Arabirimi oluşturma  
 Sihirbaz UI tanımlamak için XAML ekleyin ve bazı denetimler sihirbazda kimliği dizelere bağlamak için biraz kod ekleyin. Visual Studio'da SharePoint projeleri için yerleşik Sihirbazı, Oluşturma Sihirbazı'nı benzer.  
  
#### <a name="to-create-the-wizard-ui"></a>Sihirbaz kullanıcı Arabirimi oluşturmak için  
  
1.  İçinde **ItemTemplateWizard** proje, kısayol menüsünü açın **WizardWindow.xaml** dosya ve ardından **açmak** Tasarımcısı'nda penceresini açın.  
  
2.  XAML Görünümü'nde geçerli XAML aşağıdaki XAML ile değiştirin. XAML başlık içerir, özel eylem ve pencerenin altındaki gezinti düğmeleri davranışını belirlemek için denetler bir kullanıcı Arabirimi tanımlar.  
  
    > [!NOTE]  
    >  Bu kod ekledikten sonra projenizin bazı derleme hataları sahip olur. Sonraki adımlarda kodu eklediğinizde, bu hataları kaybolur.  
  
     [!code-xml[SPExtensibility.ProjectItem.CustomAction#9](../sharepoint/codesnippet/Xaml/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml#9)]  
  
    > [!NOTE]  
    >  Bu XAML'de oluşturulan pencerenin türetilir <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> temel sınıfı. Visual Studio için özel bir WPF iletişim kutusu eklediğinizde, Visual Studio'da diğer iletişim kutuları ile tutarlı stil sağlamak için ve kalıcı iletişim kutuları ile oluşabilecek sorunları önlemek için bu sınıf, iletişim kutusu türetin öneririz. Daha fazla bilgi için bkz: [oluşturma ve yönetme kalıcı iletişim kutuları](/visualstudio/extensibility/creating-and-managing-modal-dialog-boxes).  
  
3.  Visual Basic projesinde geliştiriyorsanız kaldırmak `ItemTemplateWizard` ad alanından `WizardWindow` sınıf adında `x:Class` özniteliği `Window` öğesi. XAML ilk satırda öğedir. İşiniz bittiğinde, ilk satırın aşağıdaki kodu benzemelidir:  
  
    ```  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  WizardWindow.xaml dosyası için arka plan kod dosyasına geçerli kodu aşağıdaki kodla değiştirin.  
  
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#7](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml.vb#7)]
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#7](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/wizardwindow.xaml.cs#7)]  
  
## <a name="implementing-the-wizard"></a>Uygulama Sihirbazı  
 Sihirbaz işlevselliğini uygulayarak tanımlama <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> arabirimi.  
  
#### <a name="to-implement-the-wizard"></a>Sihirbazı'nı uygulamak için  
  
1.  İçinde **ItemTemplateWizard** proje, açık **CustomActionWizard** kod dosyası ve ardından bu dosya geçerli kodu aşağıdaki kodla değiştirin:  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#8](../sharepoint/codesnippet/CSharp/customactionprojectitem/itemtemplatewizard/customactionwizard.cs#8)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#8](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/itemtemplatewizard/customactionwizard.vb#8)]  
  
## <a name="checkpoint"></a>Denetim noktası  
 Bu noktada kılavuzda Sihirbazı'nın tüm kod projesinde sunulmuştur. Hatasız derlendiğinden emin olmak için projeyi oluşturun.  
  
#### <a name="to-build-your-project"></a>Projenizi yapılandırmak için  
  
1.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
## <a name="associating-the-wizard-with-the-item-template"></a>Sihirbaz öğe şablonu ile ilişkilendirme  
 Sihirbaz uyguladıysanız, kendisiyle ilişkilendirmelisiniz **özel eylem** üç ana adımları tamamlayarak öğe şablonu:  
  
1.  Sihirbazı derlemeyi tanımlayıcı adla oturum açın.  
  
2.  Sihirbazı derleme için ortak anahtar belirteci alın.  
  
3.  .Vstemplate dosyasında Sihirbazı derlemesine başvuru ekleyin **özel eylem** öğe şablonu.  
  
#### <a name="to-sign-the-wizard-assembly-with-a-strong-name"></a>Sihirbaz derlemeyi tanımlayıcı adla imzalamak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünden açmak **ItemTemplateWizard** proje düğümünü ve ardından **özellikleri**.  
  
2.  Üzerinde **imzalama** sekmesine **derlemeyi imzalamak** onay kutusu.  
  
3.  İçinde **güçlü ad anahtar dosyası seçin** listesinde, seçin  **\<yeni... >**.  
  
4.  İçinde **güçlü ad anahtarı oluştur** iletişim kutusunda, bir ad temizleyin girin **my anahtar dosyasını bir parola ile koruyun** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
5.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
#### <a name="to-get-the-public-key-token-for-the-wizard-assembly"></a>Sihirbazı derleme için ortak anahtar belirteci almak için  
  
1.  Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırarak komutu, değiştirme *PathToWizardAssembly* geliştirme ItemTemplateWizard projede yerleşik ItemTemplateWizard.dll bütünleştirilmiş kod tam yoluna sahip bilgisayar.  
  
    ```  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     Ortak anahtar belirteci ItemTemplateWizard.dll derleme için Visual Studio komut istemi penceresine yazılır.  
  
2.  Visual Studio komut istemi penceresini açık tutun. Bir sonraki yordamı tamamlamak için ortak anahtar belirteci gerekir.  
  
#### <a name="to-add-a-reference-to-the-wizard-assembly-in-the-vstemplate-file"></a>.Vstemplate dosyasında Sihirbazı derlemesine başvuru eklemek için  
  
1.  İçinde **Çözüm Gezgini**, genişletin **ItemTemplate** proje düğümünü ve ItemTemplate.vstemplate dosyasını açın.  
  
2.  Dosyanın sonuna yakın aşağıdakileri ekleyin `WizardExtension` öğesi arasında `</TemplateContent>` ve `</VSTemplate>` etiketler. Değiştir *YourToken* değerini `PublicKeyToken` özniteliği önceki yordamda edinilen ortak anahtar belirteci ile.  
  
    ```  
    <WizardExtension>  
      <Assembly>ItemTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=YourToken</Assembly>  
      <FullClassName>ItemTemplateWizard.CustomActionWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     Hakkında daha fazla bilgi için `WizardExtension` öğesi, bkz: [WizardExtension öğesi &#40; Visual Studio şablonları &#41; ](/visualstudio/extensibility/wizardextension-element-visual-studio-templates).  
  
3.  Dosyayı kaydedin ve kapatın.  
  
## <a name="adding-replaceable-parameters-to-the-elementsxml-file-in-the-item-template"></a>Değiştirilebilir parametreler öğesi şablonunda Elements.xml dosyasına ekleme  
 Birkaç değiştirilebilir parametreler ItemTemplate projesinde Elements.xml dosyasına ekleyin. Bu parametreler olarak başlatılır `PopulateReplacementDictionary` yönteminde `CustomActionWizard` daha önce tanımlanan sınıfı. Bir kullanıcı bir proje için bir özel eylem proje öğesi eklediğinde, Visual Studio yeni proje öğesi Elements.xml dosyasında bu parametreler Sihirbazı'nda belirtilen değerlerle otomatik olarak değiştirir.  
  
 Bir parametredir başlatır ve dolar işareti ($) karakteri ile biten bir belirteçtir. Kendi değiştirilebilir parametreler tanımlamanın yanı sıra, SharePoint Proje sisteminin tanımlar ve başlatır yerleşik parametrelerini kullanabilirsiniz. Daha fazla bilgi için bkz: [değiştirilebilir parametreler](../sharepoint/replaceable-parameters.md).  
  
#### <a name="to-add-replaceable-parameters-to-the-elementsxml-file"></a>Değiştirilebilir parametreler Elements.xml dosyasına eklemek için  
  
1.  ItemTemplate projesinde Elements.xml dosyasının içeriğini aşağıdaki XML ile değiştirin.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Elements Id="$guid8$" xmlns="http://schemas.microsoft.com/sharepoint/">  
      <CustomAction Id="$IdValue$"  
                    GroupId="$GroupIdValue$"  
                    Location="$LocationValue$"  
                    Sequence="1000"  
                    Title="$TitleValue$"  
                    Description="$DescriptionValue$" >  
        <UrlAction Url="$UrlValue$"/>  
      </CustomAction>  
    </Elements>  
    ```  
  
     Yeni XML değerlerini değiştirir `Id`, `GroupId`, `Location`, `Description`, ve `Url` öznitelikleri değiştirilebilir parametreler.  
  
2.  Dosyayı kaydedin ve kapatın.  
  
## <a name="adding-the-wizard-to-the-vsix-package"></a>VSIX Paketi Sihirbazı'nı ekleme  
 Böylece proje öğesi içeren VSIX paketi ile dağıtılan VSIX proje source.extension.vsixmanifest dosyasında Sihirbazı projesine bir başvuru ekleyin.  
  
#### <a name="to-add-the-wizard-to-the-vsix-package"></a>VSIX Paketi Sihirbazı'nı eklemek için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünden açmak **source.extension.vsixmanifest** dosya CustomActionProjectItem projesinde ve ardından **açmak** açmak için bildirim Düzenleyicisi'nde dosya.  
  
2.  Bildirim düzenleyicisinde seçin **varlıklar** sekmesini ve ardından **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
3.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.Assembly**.  
  
4.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
5.  İçinde **proje** listesinde, seçin **ItemTemplateWizard**ve ardından **Tamam** düğmesi.  
  
6.  Menü çubuğunda seçin **yapı**, **yapı çözümü**ve ardından çözüm hatasız derlendiğinden emin olun.  
  
## <a name="testing-the-wizard"></a>Sihirbazı'nı test etme  
 Artık Sihirbazı'nı test etmek hazırsınız. İlk olarak, Visual Studio'nun deneysel örneği CustomActionProjectItem çözümde hata ayıklamak başlatın. Ardından Visual Studio'nun deneysel örneği SharePoint projede özel eylem proje öğesi Sihirbazı'nı test edin. Son olarak, yapı ve özel eylemin beklendiği gibi çalıştığını doğrulamak için SharePoint Proje çalıştırın.  
  
#### <a name="to-start-to-debug-the-solution"></a>Çözüm hata ayıklamak başlatmak için  
  
1.  Yönetici kimlik bilgileriyle Visual Studio'yu yeniden başlatın ve ardından CustomActionProjectItem çözümü açın.  
  
2.  ItemTemplateWizard projesinde CustomActionWizard kod dosyasını açın ve daha sonra bir kesme noktası kod ilk satırı ekleyin `RunStarted` yöntemi.  
  
3.  Menü çubuğunda seçin **hata ayıklama**, **özel durumları**.  
  
4.  İçinde **özel durumları** iletişim kutusunda, olduğundan emin olun **sayıcı** ve **kullanıcı işlenmemiş** onay kutularını **ortak dil çalışma zamanı özel durumları**temizlenir ve ardından **Tamam** düğmesi.  
  
5.  F5 tuşuna seçerek veya, menü çubuğundaki hata ayıklama, seçme Başlat **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
     Visual Studio %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Custom eylem proje Item\1.0 uzantıyı yükleyen ve Visual Studio Deneysel bir örneğini başlatır. Proje öğesi Visual Studio'nun bu örneği test edeceksiniz.  
  
#### <a name="to-test-the-wizard-in-visual-studio"></a>Visual Studio'da Sihirbazı'nı test etme  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **dosya**, **yeni**, **proje**.  
  
2.  Genişletin **Visual C#** veya **Visual Basic** (bağlı olarak öğesi şablonunuzu destekleyen dil), düğümünü **SharePoint** düğümü ve ardından **2010** düğümü.  
  
3.  Proje şablonları listesinden seçip **SharePoint 2010 proje**, proje adı **CustomActionWizardTest**ve ardından **Tamam** düğmesi.  
  
4.  İçinde **SharePoint Özelleştirme Sihirbazı'nı**hata ayıklama için kullanmak istediğiniz sitenin URL'sini girin ve ardından **son** düğmesi.  
  
5.  İçinde **Çözüm Gezgini**, proje düğümüne için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni öğe**.  
  
6.  İçinde **Yeni Öğe Ekle - CustomItemWizardTest** iletişim kutusunda, genişletin **SharePoint** düğümünü genişletin ve ardından **2010** düğümü.  
  
7.  Proje öğeleri listesinden seçip **özel eylem** öğesini ve ardından **Ekle** düğmesi.  
  
8.  Visual Studio'nun diğer örnek kodda, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `RunStarted` yöntemi.  
  
9. F5 tuşuna seçerek veya çubuğu, seçme menüsünde projenin hata ayıklamasını devam **hata ayıklama**, **devam**.  
  
     SharePoint Özelleştirme Sihirbazı görünür.  
  
10. Altında **konumu**, seçin **listesini düzenle** seçenek düğmesi.  
  
11. İçinde **Grup Kimliği** listesinde, seçin **iletişim**.  
  
12. İçinde **başlık** kutusuna **SharePoint Geliştirici Merkezi**.  
  
13. İçinde **açıklama** kutusuna **SharePoint Geliştirici Merkezi Web sitesi açılırsa**.  
  
14. İçinde **URL** kutusuna **http://msdn.microsoft.com/sharepoint/default.aspx**ve ardından **son** düğmesi.  
  
     Visual Studio adlı bir öğe ekler **CustomAction1** proje ve Elements.xml dosya Düzenleyicisi'nde açar. Elements.XML Sihirbazı'nda belirtilen değerleri içerdiğini doğrulayın.  
  
#### <a name="to-test-the-custom-action-in-sharepoint"></a>Özel eylem SharePoint'te test etmek için  
  
1.  Visual Studio'nun deneysel örneği, F5 tuşuna seçin veya menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
     Özel eylem paketlenir ve tarafından belirtilen SharePoint sitesi dağıtılan **Site URL'si** projeyi ve web tarayıcısı özelliği bu sitenin varsayılan sayfasını açar.  
  
    > [!NOTE]  
    >  Varsa **komut dosyası hata ayıklama devre dışı** seçin iletişim kutusu görüntülenirse, **Evet** düğmesi.  
  
2.  SharePoint sitesi listeleri alanında seçin **görevleri** bağlantı.  
  
     **Görevleri - tüm** sayfası görüntülenir.  
  
3.  Üzerinde **liste Araçları** sekmesini Şeritinde seçin **listesi** sekmesini ve ardından **ayarları** grubunda, seçin **listesi ayarları**.  
  
     **Listesi ayarları** sayfası görüntülenir.  
  
4.  Altında **iletişim** sayfanın üstünde başlığını seçin **SharePoint Geliştirici Merkezi** bağlantı, tarayıcı Web sitesi http://msdn.microsoft.com/sharepoint/ açıldığını doğrulayın default.aspx ve ardından Kapat tarayıcı.  
  
## <a name="cleaning-up-the-development-computer"></a>Geliştirme bilgisayarı temizleme  
 Proje öğesi testi tamamladıktan sonra proje öğesi şablonu Visual Studio Deneysel örnekten kaldırın.  
  
#### <a name="to-clean-up-the-development-computer"></a>Geliştirme bilgisayarı temizlemek için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantıları listesinden seçip **özel eylem proje öğesi** uzantısı ve ardından **kaldırma** düğmesi.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** uzantısı kaldırın ve ardından istediğinizi onaylamak için düğmesini **şimdi yeniden Başlat** kaldırma işleminin tamamlanması için düğmesi.  
  
4.  Visual Studio (deneysel örneği ve Visual Studio CustomActionProjectItem çözüm açıksa örneğini) hem örneklerini kapatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint Proje öğeleri için öğe şablonları ve proje şablonları oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Visual Studio Şablon Şeması Başvurusu](/visualstudio/extensibility/visual-studio-template-schema-reference)   
 [Nasıl yapılır: sihirbazları proje şablonlarıyla kullanma](../extensibility/how-to-use-wizards-with-project-templates.md)   
 [Varsayılan özel eylem konumlarını ve kimlikler](http://go.microsoft.com/fwlink/?LinkId=181964)  
  
  