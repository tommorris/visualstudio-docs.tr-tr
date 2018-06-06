---
title: 'Nasıl yapılır: görsel stiller etkinken WPF uygulaması yayımlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
ms.assetid: 73b22b02-fc75-42aa-82d3-51fdcaf8e5c8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0111226fdd3de300265f69930b7e9e56f90876c8
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34816022"
---
# <a name="how-to-publish-a-wpf-application-with-visual-styles-enabled"></a>Nasıl yapılır: Görsel Stiller Etkinken WPF Uygulaması Yayımlama
Görsel stiller kullanıcı tarafından seçilen tema göre değiştirmek için ortak denetimlerin görünümünü sağlar. Bu nedenle el ile etkinleştirmeniz gerekir varsayılan olarak, Windows Presentation Foundation (WPF) uygulamaları için görsel stiller etkin değildir. Ancak, WPF uygulaması için görsel stiller etkinleştirme ve çözüm yayımlamaya bir hataya neden olur. Bu konu, bu hatayı ve görsel stiller etkinken WPF uygulaması yayımlama işlemi çözümlemeye açıklar. Görsel stiller hakkında daha fazla bilgi için bkz: [görsel stilleri genel bakış](http://msdn.microsoft.com/5b5d7bb6-684f-478d-bf5f-b8d18bbcff2e). Hata iletisi hakkında daha fazla bilgi için bkz: [ClickOnce Dağıtımları içinde belirli hataları giderme](../deployment/troubleshooting-specific-errors-in-clickonce-deployments.md).  
  
 Hatayı çözün ve Çözümü yayımlamak için aşağıdaki görevleri gerçekleştirmeniz gerekir:  
  
-   [Görsel stiller etkinken Çözümü yayımlamak](#BKMK_publishsolwovs).  
  
-   [Bir bildirim dosyası oluşturmak](#BKMK_CreateManifest).  
  
-   [Bildirim dosyası yayımlanmış çözüm yürütülebilir dosyasına katıştırma](#BKMK_embedmanifest).  
  
-   [Uygulama ve dağıtım bildirimlerini imzalama](#BKMK_signappdeplyman).  
  
 Sonra son kullanıcıların uygulamayı yüklemek istediğiniz konuma yayımlanan dosyalarını taşıyabilirsiniz.  
  
##  <a name="BKMK_publishsolwovs"></a> Görsel stiller etkinken çözümü yayımlama  
  
1.  Projenizi görsel stiller etkinken olmadığından emin olun. İlk olarak, projenizin bildirim dosyası için aşağıdaki XML denetleyin. XML varsa, daha sonra XML açıklama etiketi ile alın.  
  
     Görsel stilleri varsayılan olarak etkin değildir.  
  
    ```xml  
    <dependency>    <dependentAssembly>      <assemblyIdentity          type="win32"          name="Microsoft.Windows.Common-Controls"          version="6.0.0.0"          processorArchitecture="*"          publicKeyToken="6595b64144ccf1df"          language="*"        />    </dependentAssembly>  </dependency>  
    ```  
  
     Aşağıdaki yordamlar, projeyle ilişkili bildirim dosyası açmak nasıl gösterir.  
  
    ###### <a name="to-open-the-manifest-file-in-a-visual-basic-project"></a>Visual Basic projesinde bildirim dosyasını açmak için  
  
    1.  Menü çubuğunda seçin **proje**, * ProjectName ***özellikleri**, burada *ProjectName* WPF projenizi adıdır.  
  
         Özellik sayfaları WPF projeniz için görünür.  
  
    2.  Üzerinde **uygulama** sekmesinde, seçin **görünüm Windows ayarlarını**.  
  
         App.manifest dosyası açılır **Kod düzenleyicisinde**.  
  
    ###### <a name="to-open-the-manifest-file-in-a-c-project"></a>Bir C# projesinde bildirim dosyasını açmak için  
  
    1.  Menü çubuğunda seçin **proje**, * ProjectName ***özellikleri**, burada *ProjectName* WPF projenizi adıdır.  
  
         Özellik sayfaları WPF projeniz için görünür.  
  
    2.  Üzerinde **uygulama** sekmesinde, bildirim alanında görünen adını not edin. Projenizi ile ilişkili bildirim adıdır.  
  
        > [!NOTE]
        >  Varsa **Embed bildirimi varsayılan ayarlarla** veya **uygulama bildirimi olmadan oluşturma** görsel stiller etkin değil bildirim alanında görüntülenir. Bildirim alanında bir bildirim dosyasının adı görüntülenir, bu yordamdaki bir sonraki adıma devam edin.  
  
    3.  İçinde **Çözüm Gezgini**, seçin **tüm dosyaları göster** ().  
  
         Bu düğme, hariç tutulmuş ve normalde gizli olanlar dahil olmak üzere tüm proje öğeleri gösterir. Bildirim dosyası bir proje öğesi görünür.  
  
2.  Derleme ve çözümünüzü yayımlayın. Çözüm yayımlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
##  <a name="BKMK_CreateManifest"></a> Bildirim dosyası oluştur  
  
1.  Aşağıdaki XML Notepad dosyaya yapıştırın.  
  
     Bu XML görsel stiller destekleyen denetimleri içeren bütünleştirilmiş kodun açıklar.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?><asmv1:assembly manifestVersion="1.0"                xmlns="urn:schemas-microsoft-com:asm.v1"                xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"                xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"                xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  <dependency>    <dependentAssembly>      <assemblyIdentity        type="win32"        name="Microsoft.Windows.Common-Controls"        version="6.0.0.0"        processorArchitecture="*"        publicKeyToken="6595b64144ccf1df"        language="*"        />    </dependentAssembly>  </dependency></asmv1:assembly>  
    ```  
  
2.  Not Defteri'nde tıklatın **dosya**ve ardından **Kaydet**.  
  
3.  İçinde **Kaydet** iletişim kutusunda **farklı türde Kaydet** aşağı açılan listesinden, **tüm dosyaları**.  
  
4.  İçinde **dosya adı** kutusuna, dosya adı ve ilave **.manifest** dosya adının sonuna. Örneğin: **themes.manifest**.  
  
5.  Seçin **klasörlere Gözat** düğmesi, herhangi bir klasör seçin ve ardından **kaydetmek**.  
  
    > [!NOTE]
    >  Kalan yordamlar bu dosyasının adı olduğunu varsayar **themes.manifest** ve dosyayı bilgisayarınızda C:\temp dizinine kaydedilir.  
  
##  <a name="BKMK_embedmanifest"></a> Bildirim dosyası yayımlanmış çözüm yürütülebilir dosyasına katıştırma  
  
1.  Açık **Visual Studio komut istemi**.  
  
     Nasıl açılacağı hakkında daha fazla bilgi için **Visual Studio komut istemi**, bkz: [komut istemlerini](/dotnet/framework/tools/developer-command-prompt-for-vs).  
  
    > [!NOTE]
    >  Geri kalan adımları çözümünüzü hakkında aşağıdaki varsayımlar olun:  
    >   
    >  -   Çözüm adı **MyWPFProject**.  
    > -   Çözüm aşağıdaki dizinde bulunur: `%UserProfile%\Documents\Visual Studio 2010\Projects\`.  
    >   
    >      Çözüm şu dizine yayımlanır: `%UserProfile%\Documents\Visual Studio 2010\Projects\publish`.  
    > -   Yayımlanan uygulama dosyaların en son sürümünü şu dizinde bulunur: `%UserProfile%\Documents\Visual Studio 2010\Projects\publish\Application Files\WPFApp_1_0_0_0`  
    >   
    >  Adı veya yukarıda açıklanan dizin konumları kullanmak zorunda değil. Yukarıda açıklanan konumları ve adını yalnızca çözümünüzü yayımlamak için gerekli olan adımları göstermek için kullanılır.  
  
2.  Komut isteminde yolu yayımlanan uygulama dosyaların en son sürümünü içeren dizine geçin. Aşağıdaki örnek, bu adımı gösterir.  
  
    ```  
cd "%UserProfile%\Documents\Visual Studio 2010\Projects\MyWPFProject\publish\Application Files\WPFApp_1_0_0_0"  
    ```  
  
3.  Komut isteminde, uygulamanızın yürütülebilir dosyaya bildirim dosyası eklemek için aşağıdaki komutu çalıştırın.  
  
    ```
    mt -manifest c:\temp\themes.manifest -outputresource:MyWPFApp.exe.deploy  
    ```  
  
##  <a name="BKMK_signappdeplyman"></a> Uygulama ve dağıtım bildirimlerini imzalama  
  
1.  Komut isteminde kaldırmak için aşağıdaki komutu çalıştırın `.deploy` yürütülebilir dosya geçerli dizinde uzantı.  
  
    ```  
    ren MyWPFApp.exe.deploy MyWPFApp.exe  
    ```  
  
    > [!NOTE]
    >  Bu örnekte yalnızca o dosya olduğu varsayılır `.deploy` dosya uzantısı. Bu dizinde sahip tüm dosyaları yeniden adlandırma emin olun `.deploy` dosya uzantısı.  
  
2.  Komut isteminde uygulama bildiriminizi imzalamak için aşağıdaki komutu çalıştırın.  
  
    ```  
    mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx  
    ```  
  
    > [!NOTE]
    >  Bu örnek kullanarak bildirim oturum varsayar `.pfx` projenin dosya. Bildirim imzalama değil, atlayabilirsiniz `-cf` Bu örnekte kullanılan parametre. Parola gerektiren bir sertifika ile bildirimini kaydoluyorsanız belirtin `-password` seçeneği (`For example: mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx - password Password`).  
  
3.  Komut isteminde eklemek için aşağıdaki komutu çalıştırın `.deploy` bu yordamın önceki adımda yeniden adlandırılmış dosya adı uzantısı.  
  
    ```  
    ren MyWPFApp.exe MyWPFApp.exe.deploy  
    ```  
  
    > [!NOTE]
    >  Bu örnekte, yalnızca bir dosya varsayılır sahip bir `.deploy` dosya uzantısı. Daha önce sahip olduğunuz Bu dizindeki tüm dosyaları yeniden adlandırmak emin olun `.deploy` dosya adı uzantısı.  
  
4.  Komut isteminde dağıtım bildirimini imzalamak için aşağıdaki komutu çalıştırın.  
  
    ```  
    mage -u ..\..\MyWPFApp.application -appm MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx  
    ```  
  
    > [!NOTE]
    >  Bu örnek kullanarak bildirim oturum varsayar `.pfx` projenin dosya. Bildirim imzalama değil, atlayabilirsiniz `-cf` Bu örnekte kullanılan parametre. Parola gerektiren bir sertifika ile bildirimini kaydoluyorsanız belirtin `-password` seçeneği, bu örnekte olduğu gibi:`For example: mage -u MyWPFApp.exe.manifest -cf ..\..\..\MyWPFApp_TemporaryKey.pfx - password Password`.  
  
 Bu adımları gerçekleştirdikten sonra son kullanıcıların uygulamayı yüklemek istediğiniz konuma yayımlanan dosyalarını taşıyabilirsiniz. Çözüm genellikle güncelleştirmek istiyorsanız, bu komutlar bir komut dosyasına taşıyın ve her zaman yeni bir sürüm yayımlayın komut dosyasını çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Dağıtımları içinde belirli hataları giderme](../deployment/troubleshooting-specific-errors-in-clickonce-deployments.md)   
 [Görsel stiller genel bakış](http://msdn.microsoft.com/5b5d7bb6-684f-478d-bf5f-b8d18bbcff2e)   
 [Görsel stiller etkinleştirme](https://msdn.microsoft.com/library/bb773175.aspx)   
 [Komut İstemleri](/dotnet/framework/tools/developer-command-prompt-for-vs)