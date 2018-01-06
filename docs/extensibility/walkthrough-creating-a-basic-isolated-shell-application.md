---
redirect_url: shell/walkthrough-creating-a-basic-isolated-shell-application
title: "İzlenecek yol: temel bir oluşturma yalıtılmış Kabuk uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, walkthroughs
- Shell [Visual Studio], walkthroughs
- walkthroughs [Visual Studio], isolated shell-based application
ms.assetid: 8b12e223-aae3-4c23-813d-ede1125f5f69
caps.latest.revision: "54"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 28a555f2ab6e907a54cfb88d57ee09f5f47771ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-basic-isolated-shell-application"></a>İzlenecek yol: bir temel yalıtılmış Kabuk uygulaması oluşturma
Bu kılavuz, yalıtılmış Kabuk çözümünü oluşturun, Yardım hakkında araç penceresi özelleştirmek ve yalıtılmış Kabuk yükleyen bir Kurulum programı oluşturun gösterilmektedir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md). Yalıtılmış Kabuk dağıtmak için de Visual Studio Kabuğu (Yalýtýlmýþ) yeniden dağıtılabilir paketi kullanmanız gerekir.  
  
## <a name="creating-an-isolated-shell-solution"></a>Yalıtılmış Kabuk çözümünü oluşturma  
 Bu bölümde Visual Studio Shell yalıtılmış proje şablonu bir yalıtılmış Kabuk çözüm oluşturmak için nasıl kullanılacağını gösterir. Çözüm, aşağıdaki projeleri içerir:  
  
-   *SolutionName*. AboutBoxPackage proje görünümü Yardımı/hakkında kutusunda özelleştirmenizi sağlar.  
  
-   ShellExtensionsVSIX proje yalıtılmış Kabuk uygulama'nin farklı bileşenleri tanımlayan source.extension.vsixmanifest dosyası içerir.  
  
-   *SolutionName* projesi yalıtılmış Kabuk uygulamayı çağıran yürütülebilir dosyası oluşturur. Bu proje özelleşt görünümü için ve yalıtılmış Kabuk uygulama davranışını verir Kabuk özelleştirmesi klasör içerir.  
  
-   *SolutionName* etkin menü komutları ve yerelleştirilebilir dizeler tanımlayan bir uydu derleme üreten UI projesi.  
  
#### <a name="to-create-a-basic-isolated-shell-solution"></a>Bir temel yalıtılmış Kabuk çözüm oluşturmak için  
  
1.  Visual Studio'yu açın ve yeni bir proje oluşturun.  
  
2.  İçinde **yeni proje** penceresinde genişletin **diğer proje türleri** ve ardından **genişletilebilirlik**. Seçin **Visual Studio Shell yalıtılmış** proje şablonu.  
  
3.  Proje adı `MyVSShellStub` ve konumu belirtin. Olduğundan emin olun **çözüm için dizin oluştur** denetlenir ve ardından **Tamam**.  
  
     Yeni bir çözüm görünür **Çözüm Gezgini**.  
  
4.  Çözümü derlemek ve yalıtılmış Kabuk uygulama hata ayıklamayı Başlat.  
  
     Visual Studio yalıtılmış Kabuk görüntülenir. Başlık çubuğu okur **MyVSShellStub**. Başlık çubuğu simgesi \MyVSShellStub\Resource Files\ApplicationIcon.ico oluşturulur.  
  
## <a name="customizing-the-application-name-and-icon"></a>Uygulama adı ve simge özelleştirme  
 Başlık çubuğunda şirketiniz ve kendi logo adını kullanarak uygulamanızı marka isteyebilirsiniz. Aşağıdaki adımlar adı ve paket tanımlama dosyası, MyVSShellStub.Application.pkgdef değiştirerek özel uygulama başlık çubuğunda görüntülenen simge nasıl değiştirileceğini gösterir.  
  
#### <a name="to-customize-the-application-name-and-icon"></a>Uygulama adı ve simge özelleştirmek için  
  
1.  MyVSShellStub projesinde \Shell Customization\MyVSShellStub.Application.pkgdef açın.  
  
2.  Değişiklik `AppName` öğesi değerine **"AppName" = "Fabrikam müzik Editor"**  
  
3.  Uygulama simgesi değiştirmek için farklı bir simge \MyVSShellStub\MyVSShellStub\MyVSShellStub\ dizinine kopyalayın. Varolan ApplicationIcon.ico dosyasını ApplicationIcon1.ico için yeniden adlandırın. Yeni dosya ApplicationIcon.ico için yeniden adlandırın.  
  
4.  Çözümü derlemek ve hata ayıklamayı Başlat. Yalıtılmış Kabuk IDE görünür. Başlık çubuğu sözcükleri yanında, yeni simgesine sahip **Fabrikam müzik Düzenleyicisi**.  
  
## <a name="customizing-the-default-web-browser-home-page"></a>Varsayılan Web tarayıcısı giriş sayfasını özelleştirme  
 Bu bölümde, varsayılan giriş sayfasının değiştirmek gösterilmiştir **Web tarayıcısı** paket tanımlama dosyasını değiştirerek penceresi.  
  
#### <a name="to-customize-the-default-web-browser-home-page"></a>Varsayılan Web tarayıcısı giriş sayfasını özelleştirme  
  
1.  MyVSShellStub.Application.pkgdef dosyasında değişiklik `DefaultHomePage` "http://www.microsoft.com" için öğe değeri.  
  
2.  MyVSShellStub projeyi yeniden oluşturun.  
  
3.  Çözümü derlemek ve hata ayıklamayı Başlat.  
  
4.  İçinde **Görünüm > Diğer pencereler**, tıklatın **Web tarayıcısı**. **Web tarayıcısı** penceresi, Microsoft Corporation'ın Giriş sayfasını görüntüler.  
  
## <a name="removing-the-print-command"></a>Yazdırma komutu kaldırma  
 Yalıtılmış Kabuk UI projesinde .vsct dosyasında bildirimler biçiminde bir dizi oluşur `<Define name=No_` *öğesi*`>`, burada *öğesi* standart Visual Studio menüler biridir ve komutları.  
  
 Bir bildirim uncommented ise, o menü veya komut yalıtılmış Kabuğu'ndan dışlandı. Buna karşılık, bir bildirimi bırakılmışsa menü veya komut yalıtılmış Kabuğu'nda bulunur.  
  
 Aşağıdaki adımlarda, yazdırma komutu .vsct dosyanızda açıklamadan çıkarın.  
  
#### <a name="to-remove-the-print-command"></a>Yazdırma komutu kaldırmak için  
  
1.  Doğrulayın **yazdırma** komutu görünür **dosya** yalıtılmış Kabuk uygulama menüsü.  
  
2.  MyVSShellStubUI projesinde \Resource Files\MyVSShellStubUI.vsct düzenlemek için açın.  
  
3.  Bu satırı açıklamadan çıkarın:  
  
    ```  
    <!-- <Define name="No_PrintChildrenCommand"/> -->  
    ```  
  
4.  Bu yazdırma komutu kaldırır.  
  
5.  Yalıtılmış Kabuk uygulama hata ayıklamayı Başlat. Doğrulayın **Dosya > Yazdırma** komuttur kaldırılmıştır.  
  
## <a name="removing-features-from-the-isolated-shell"></a>Özellikler yalıtılmış Kabuğu'ndan kaldırma  
 Visual Studio ile özel yalıtılmış Kabuk uygulamanızda bu özellikleri istemiyorsanız .pkgundef dosyasını düzenleyerek yüklenen paketler bazıları kaldırabilirsiniz. $RootKey$ \Packages kayıt defteri anahtarı alt anahtarları birinde paketi belirtin.  
  
> [!NOTE]
>  Visual Studio GUID'ler özellikleri bulmak için bkz: [paketi GUID, Visual Studio özellikleri](../extensibility/package-guids-of-visual-studio-features.md).  
  
 Aşağıdaki yordamda XML kaldırmak yalıtılmış Kabuk düzenleyicisinden gösterilmiştir.  
  
#### <a name="to-remove-the-xml-editor"></a>XML Düzenleyicisi'ni kaldırmak için  
  
1.  MyVSShellStub proje Kabuk özelleştirmesi klasöründeki MyVSShellStub.pkgundef dosyasını açın.  
  
2.  Aşağıdaki satırı açıklamadan çıkarın:  
  
     [$RootKey$ \Packages\\{87569308-4813-40a0-9cd0-d7a30838ca3f}]  
  
3.  Çözümü yeniden derleyin ve yalıtılmış Kabuk hata ayıklamayı Başlat. Örneğin, \MyVSShellStub\MyVSShellStub\MyVSShellStubUI\MyVSShellStubUI.vsct bir XML dosyasını açın. Dosyasındaki XML anahtar sözcükleri değil renklendirilmiştir doğrulayın ve bu yazarak "<" bir satıra XML araç ipuçları getirmiyor.  
  
## <a name="customizing-the-helpabout-box"></a>Yardım'ı özelleştirme/kutusu hakkında  
 Yardım özelleştirebilirsiniz/kutusu hakkında yalıtılmış Kabuk proje şablonu bir parçası olarak oluşturulur.  
  
#### <a name="to-customize-the-company-name"></a>Şirket adı özelleştirmek için  
  
1.  Şirket adı, telif hakkı bilgileri, ürün sürümü ve ürün açıklaması MyVSShellStub.AboutBoxPackage projesinde \Properties\AssemblyInfo.cs dosyasında bulunamadı. Bu dosyayı açın.  
  
2.  Değişiklik `AssemblyCompany` değeri **Fabrikam**, `AssemblyProduct` ve `AssemblyTitle` değerler **Fabrikam müzik Düzenleyicisi**ve `AssemblyCopyright` değeri **telif hakkı © Fabrikam 2015**:  
  
    ```  
    [assembly: AssemblyTitle("Fabrikam Music Editor")]  
    [assembly: AssemblyDescription("")]  
    [assembly: AssemblyConfiguration("")]  
    [assembly: AssemblyCompany("Fabrikam")]  
    [assembly: AssemblyProduct("Fabrikam Music Editor")]  
    [assembly: AssemblyCopyright("Copyright © Fabrikam 2015")] [assembly: AssemblyCompany("Fabrikam")]  
    [assembly: AssemblyProduct("Fabrikam Music Editor ")]  
    [assembly: AssemblyCopyright("Copyright © Fabrikam 2015")]  
    ```  
  
3.  Ürün açıklaması eklemek, değiştirmek `AssemblyDescription` değeri **Fabrikam müzik Düzenleyicisi açıklaması.**:  
  
    ```  
    [assembly: AssemblyDescription("The description of Fabrikam Music editor.")]  
    ```  
  
4.  Hata Ayıklamayı Başlat ve yalıtılmış Kabuk uygulamasında açın **Yardım > hakkında** kutusu. Değiştirilen dizeleri görmeniz gerekir. Yardım'ın / kutusu hakkında başlık aynıdır `AssemblyTitle` AssemblyInfo.cs değeri.  
  
5.  Özelliklerini **Yardımı/hakkında** kutunun kendisi MyVSShellStub.AboutBoxPackage\AboutBox.xaml dosyasında bulunamadı. Yardım'ın / kutusu hakkında genişliği değiştirmek için Git `AboutDialogStyle` engelleme ve ayarlama `Width` 200 özelliğine:  
  
    ```  
    <Style x:Key="AboutDialogStyle" TargetType="Window">  
        <Setter Property="Height" Value="Auto" />  
        <Setter Property="Width" Value="200" />  
        <Setter Property="ShowInTaskbar" Value="False" />  
        <Setter Property="ResizeMode" Value="NoResize" />  
        <Setter Property="WindowStyle" Value="SingleBorderWindow" />  
        <Setter Property="SizeToContent" Value="Height" />  
    </Style>  
    ```  
  
6.  Çözümü yeniden derleyin ve yalıtılmış Kabuk hata ayıklamayı Başlat. Yardımı/hakkında kutusunu yaklaşık kare olmalıdır.  
  
## <a name="before-you-deploy-the-isolated-shell-application"></a>Yalıtılmış Kabuk uygulamanızı dağıtmadan önce  
 Yalıtılmış Kabuk uygulamanızı Visual Studio Kabuğu (Yalýtýlmýþ) yeniden dağıtılabilir paketi olan herhangi bir bilgisayara yüklenebilir. Yeniden dağıtılabilir paketi hakkında daha fazla bilgi için bkz: [Visual Studio genişletilebilirlik indirmeleri](http://go.microsoft.com/fwlink/?LinkID=119298) Web sitesi.  
  
## <a name="deploying-the-isolated-shell-application"></a>Yalıtılmış Kabuk uygulamasını dağıtma  
 Yalıtılmış kabuk uygulamanıza bir hedef bilgisayara bir kurulum projesi oluşturarak dağıtın. Bunlardan belirtmeniz gerekir:  
  
-   Hedef bilgisayarda dosya ve klasörleri düzeni.  
  
-   .NET Framework ve Visual Studio çalışma zamanı Kabuk garanti başlatma koşulları hedef bilgisayarda yüklü.  
  
 Aşağıdaki yordamda, bilgisayarınızda InstallShield Limited Edition yüklemeniz gerekir.  
  
#### <a name="to-create-the-setup-project"></a>Kurulum projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümüne sağ tıklayın ve ardından **Yeni Proje Ekle**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **diğer proje türleri** ve ardından **Kurulum ve dağıtım**. InstallShield şablonu seçin. Yeni proje adı `MySetup` ve ardından **Tamam**.  
  
3.  InstallShield Limited Edition zaten yüklediyseniz, sonraki adıma devam edin.  
  
     InstallShield Limited Edition zaten yüklü değilse, InstallShield yükleme sayfası görüntülenir. Karşıdan yükle ve Visual Studio sürümünüzle uyumlu InstallShield sürümünü seçerek bu ürünü yüklemek için yönergeleri izleyin. InstallShield yüklemenizin kaydetmek veya değerlendirme sürümü kullanmak karar vermeniz gerekir. Yüklemeyi tamamladıktan sonra Visual Studio yeniden başlatmanız gerekir.  
  
    > [!IMPORTANT]
    >  Bir InstallShield proje oluşturmadan önce bir yönetici olarak Visual Studio başlatmanız gerekir. Bunu yaparsanız, projeyi derlerken hata alırsınız.  
  
 Sonraki adımlar nasıl Kurulum projesi yapılandırılacağını gösterir.  
  
> [!IMPORTANT]
>  Kurulum projesi yapılandırmadan önce en az bir kez yayın yapılandırma yalıtılmış Kabuk projenizin yerleşik olduğundan emin olun.  
  
#### <a name="to-configure-the-setup-project"></a>Kurulum projesi yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**altında **MySetup** seçin, proje **proje Yardımcısı**. Alt sıradaki **proje Yardımcısı** penceresinde, seçin **uygulama bilgilerini**. Girin **Fabrikam** olarak, şirketinizin adını ve **Fabrikam müzik Düzenleyicisi** uygulamanızın adı olarak. Sağ alt köşesindeki ileri oku seçin **proje Yardımcısı**.  
  
2.  Seçin **Evet** altında **uygulamanızı makineye yüklenmesi için herhangi bir yazılım gerektiriyor mu?** ve ardından **Microsoft .NET Framework 4.5 tam paket**.  
  
3.  Seçin **uygulama dosyalarını** düğmesini penceresinin alt kısmında ve olduğundan emin olun **Fabrikam müzik Düzenleyicisi'ni** klasörü seçilidir.  
  
4.  Seçin **dosyaları Ekle** düğmesi. İçinde **dosyaları Ekle** iletişim kutusunda, aşağıdaki dosyaları ekleyin **MyVSShellStub\Release** klasörü:  
  
    1.  MyVSShellStub.exe.config  
  
    2.  DebuggerProxy.dll  
  
    3.  DebuggerProxy.dll.manifest  
  
    4.  MyVSShellStub.pkgdef  
  
    5.  MyVSShellStub.pkgundef  
  
    6.  MyVSShellStub.winprf  
  
    7.  Splash.bmp  
  
5.  Tıklatın **eklemek proje çıktıları** düğmesini tıklatın ve eklemek **MyVSShellStub/birincil çıkış**. **Tamam**'ı tıklatın.  
  
6.  Sol bölmede altında **hedef bilgisayar**, sağ tıklatın **Fabrikam müzik Düzenleyicisi [INSTALLDİR]** düğüm ekleyin bir **yeni klasör** adlı **uzantıları** .  
  
7.  Sağ **uzantıları** sol bölmedeki düğümünü ve adlı yeni bir klasör ekleyin **uygulama**.  
  
8.  Seçin **uygulama** klasörü ve tıklatın **eklemek proje çıktıları** düğmesine ve ardından birincil çıktıyı MyVSShellStub.AboutBoxPackage projeden seçin.  
  
9. Tıklatın **dosyaları Ekle** düğmesine tıklayın ve \MyVSShellStub\Release\Extensions\Application\ klasöründen aşağıdaki dosyaları ekleyin:  
  
    -   MyVSShellStub.AboutBoxPackage.pkgdef  
  
    -   MyVSShellStub.Application.pkgdef  
  
10. Sağ **Fabrikam müzik Düzenleyicisi [INSTALLDİR]** sol bölmedeki düğümünü ve adlı yeni bir klasör ekleyin **1033**.  
  
11. 1033 klasörü seçin ve ardından **eklemek proje çıktıları** düğmesine tıklayın ve birincil çıktıyı MyVSShellStubUI projeden seçin.  
  
12. Taşıma **uygulama kısayolları** penceresi.  
  
13. Tıklatın **yeni** bir kısayol oluşturmak ve **[Programfılesfolder] \Fabrikam\Fabrikam Music Editor\MyVSShellStub.Primary Output**.  
  
14. Taşıma **yükleme görüşme** bölmesi.  
  
15. Tüm öğeleri kümesine **Hayır**.  
  
16. İçinde **Çözüm Gezgini**, MySetup projeyi açın **Kurulum gereksinimleri tanımlayın ve eylemleri \ gereksinimleri**. **Gereksinimleri** penceresi açılır.  
  
17. Sağ tıklayın **sistem yazılım gereksinimleri** seçip **yeni başlatma koşul Oluştur**. **Sistem Arama Sihirbazı'nı** görüntülenir.  
  
18. İçinde **ne bulmak istediğiniz?** bölmesinde seçin **kayıt defteri girdisini** tıklayın ve açılan liste **sonraki**.  
  
19. İçinde **nasıl aramanız istiyorsunuz?** bölmesinde, **HKEY_LOCAL_MACHINE** kayıt defteri kök olarak. Girin **SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing\14.0\isoshell** 64-bit sistemler için veya **SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell** 32 bit sistemler için ve girin **Yükleme** kayıt defteri değeri olarak. **İleri**'ye tıklayın.  
  
20. İçinde **ne değeriyle yapmak istiyor musunuz?** bölmesinde girin **bu ürün için Visual Studio 2015 yalıtılmış Kabuk yüklenmesi yeniden dağıtılabilir gereklidir.** ' ı tıklatın ve görüntüleme metni olarak **son**.  
  
21. Kurulum projesi oluşturmak için yalıtılmış Kabuk çözümü yeniden derleyin.  
  
     Setup.exe dosyasını aşağıdaki klasörde bulabilirsiniz:  
  
     \MyVSShellStub\MySetup\MySetup\Express\SingleImage\DiskImages\DISK1  
  
## <a name="testing-the-installation-program"></a>Yükleme programı test etme  
 Kurulum sınamak için setup.exe dosyasını farklı bir bilgisayara kopyalayın ve kurulum yürütülebilir dosyayı çalıştırmak. Yalıtılmış Kabuk uygulamayı çalıştıramaz olması gerekir.