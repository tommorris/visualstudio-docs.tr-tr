---
title: 'İzlenecek yol: SharePoint projeleri için özel bir dağıtım adımı oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint commands
- SharePoint development in Visual Studio, extending deployment
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a9052136a58b0c6cd3246b7c7b61c89bf637a8cf
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects"></a>İzlenecek Yol: SharePoint Projeleri için Özel bir Dağıtım Adımı Oluşturma
  Bir SharePoint projesi dağıttığınızda, Visual Studio belirli bir sıraya göre bir dizi dağıtım adımı yürütür. Visual Studio birçok yerleşik dağıtım adımlarını içerir, ancak Ayrıca kendi oluşturabilirsiniz.  
  
 Bu kılavuzda, SharePoint çalıştıran bir sunucuda çözümlerini yükseltme için özel bir dağıtım adımı oluşturur. Visual Studio birçok görev, bu tür geri çekilen veya çözümleri eklemek için yerleşik dağıtım adımlarını içerir, ancak çözümlerini yükseltme için bir dağıtım adımı içermez. Bir SharePoint çözümünü dağıttığınızda (zaten dağıtılırsa) varsayılan olarak, Visual Studio çözümü ilk çeker. ve tüm çözümü yeniden dağıtır. Yerleşik dağıtım adımları hakkında daha fazla bilgi için bkz: [dağıtma, yayımlama ve yükseltme SharePoint çözüm paketlerini](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md).  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Visual Studio uzantısı oluşturma iki ana görevleri gerçekleştirir:  
  
    -   Uzantı SharePoint çözümlerini yükseltme için özel bir dağıtım adımı tanımlar.  
  
    -   Uzantısı için belirli bir projenin yürütülen dağıtım adımları bir dizi yeni bir dağıtım yapılandırmasını tanımlayan bir proje uzantısı oluşturur. Yeni dağıtım yapılandırma özel dağıtım adımı ve birkaç yerleşik dağıtım adımları içerir.  
  
-   Uzantı derlemesi çağırır iki özel SharePoint komutu oluşturma. SharePoint komutları API'leri için SharePoint sunucusu nesne modelinde kullanmak için uzantı derlemeleri tarafından çağrılan yöntemler şunlardır. Daha fazla bilgi için bkz: [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
-   Derlemeler her ikisi de dağıtmak için Visual Studio Uzantısı (VSIX) paketi oluşturma.  
  
-   Yeni dağıtım adımı test etme.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Windows, SharePoint ve Visual Studio sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK'sı. Bu kılavuzda kullanılır **VSIX proje** SDK'sındaki uzantısını dağıtmak için VSIX paket oluşturmak için şablon. Daha fazla bilgi için bkz: [genişletme Visual Studio'da SharePoint Araçları](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Aşağıdaki kavramlar bilgisi yararlı, ancak gerekli değildir, izlenecek yolu tamamlamak için:  
  
-   Sunucu nesne modeli için SharePoint kullanma. Daha fazla bilgi için bkz: [SharePoint Foundation Sunucu tarafı nesne modelini kullanarak](http://go.microsoft.com/fwlink/?LinkId=177796).  
  
-   SharePoint çözümleri. Daha fazla bilgi için bkz: [çözümlerine genel bakış](http://go.microsoft.com/fwlink/?LinkId=169422).  
  
-   SharePoint çözümlerini yükseltme. Daha fazla bilgi için bkz: [bir çözümü yükseltme](http://go.microsoft.com/fwlink/?LinkId=177802).  
  
## <a name="creating-the-projects"></a>Proje oluşturma  
 Bu izlenecek yolu tamamlamak için üç projeleri oluşturmanız gerekir:  
  
-   Uzantı dağıtmak için VSIX paketi oluşturmak için bir VSIX proje.  
  
-   Uzantı arabirimini uygulayan bir sınıf kitaplığı projesi. Bu proje .NET Framework 4.5 hedeflemesi gerekir.  
  
-   Özel SharePoint komutları tanımlayan bir sınıf kitaplığı proje. Bu proje .NET Framework 3.5 hedeflemesi gerekir.  
  
 İzlenecek yol projeleri oluşturarak başlayın.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
3.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **genişletilebilirlik** düğümü.  
  
    > [!NOTE]  
    >  **Genişletilebilirlik** düğümdür yalnızca Visual Studio SDK'sı yüklerseniz kullanılabilir. Daha fazla bilgi için bu konudaki Önkoşullar bölümüne bakın.  
  
4.  İletişim kutusunun üstündeki seçin **.NET Framework 4.5** .NET Framework sürümleri listesinde.  
  
5.  Seçin **VSIX proje** şablonu, proje adı **UpgradeDeploymentStep**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **UpgradeDeploymentStep** için proje **Çözüm Gezgini**.  
  
#### <a name="to-create-the-extension-project"></a>Uzantı projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, UpgradeDeploymentStep çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **Windows** düğümü.  
  
3.  İletişim kutusunun üstündeki seçin **.NET Framework 4.5** .NET Framework sürümleri listesinde.  
  
4.  Seçin **sınıf kitaplığı** proje şablonu, proje adı **DeploymentStepExtension**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **DeploymentStepExtension** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
5.  Class1 kod dosyasının projeden silin.  
  
#### <a name="to-create-the-sharepoint-command-project"></a>SharePoint komutu projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, UpgradeDeploymentStep çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic**ve ardından **Windows** düğümü.  
  
3.  İletişim kutusunun üstündeki seçin **.NET Framework 3.5** .NET Framework sürümleri listesinde.  
  
4.  Seçin **sınıf kitaplığı** proje şablonu, proje adı **SharePointCommands**ve ardından **Tamam** düğmesi.  
  
     Visual Studio ekler **SharePointCommands** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
5.  Class1 kod dosyasının projeden silin.  
  
## <a name="configuring-the-projects"></a>Projeleri yapılandırma  
 Özel dağıtım adımı oluşturmak için kod yazmadan önce ve derleme başvurularını kod dosyaları ekleyin ve projeleri yapılandırmanız gerekir.  
  
#### <a name="to-configure-the-deploymentstepextension-project"></a>DeploymentStepExtension projeyi yapılandırmak için  
  
1.  İçinde **DeploymentStepExtension** projesi, aşağıdaki adlara sahip iki kod dosyaları ekleyin:  
  
    -   UpgradeStep  
  
    -   DeploymentConfigurationExtension  
  
2.  DeploymentStepExtension proje kısayol menüsünü açın ve ardından **Başvuru Ekle**.  
  
3.  Üzerinde **Framework** sekmesinde, System.ComponentModel.Composition derlemesi için onay kutusunu seçin.  
  
4.  Üzerinde **uzantıları** sekmesinde Microsoft.VisualStudio.SharePoint derlemesi için onay kutusunu seçin ve ardından **Tamam** düğmesi.  
  
#### <a name="to-configure-the-sharepointcommands-project"></a>SharePointCommands projeyi yapılandırmak için  
  
1.  İçinde **SharePointCommands** projesi, komutları adlı bir kod dosyasına ekleyin.  
  
2.  İçinde **Çözüm Gezgini**, kısayol menüsünü açmak **SharePointCommands** proje düğümünü ve ardından **Başvuru Ekle**.  
  
3.  Üzerinde **uzantıları** sekmesinde, aşağıdaki derlemeler için onay kutularını seçin ve ardından tıklatın **Tamam** düğmesi  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
## <a name="defining-the-custom-deployment-step"></a>Özel dağıtım adımı tanımlama  
 Yükseltme dağıtım adımı tanımlayan bir sınıf oluşturun. Sınıf Implements dağıtım adımı tanımlamak için <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep> arabirimi. Özel bir dağıtım adımı tanımlamak istediğiniz zaman bu arabirimi uygular.  
  
#### <a name="to-define-the-custom-deployment-step"></a>Özel dağıtım adımı tanımlamak için  
  
1.  İçinde **DeploymentStepExtension** proje, UpgradeStep kod dosyasını açın ve ardından aşağıdaki kodu yapıştırın.  
  
    > [!NOTE]  
    >  Ne zaman bu kodu ekleyin, proje bazı derleme hataları sahip olur, ancak hemen alınacaktır sonra daha sonraki adımlarda kodu ekleyin.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#1](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/deploymentstepextension/upgradestep.cs#1)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#1](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/deploymentstepextension/upgradestep.vb#1)]  
  
## <a name="creating-a-deployment-configuration-that-includes-the-custom-deployment-step"></a>Özel dağıtım adımı içeren bir dağıtım yapılandırması oluşturma  
 Birkaç yerleşik dağıtım adımlarını ve yeni yükseltme dağıtımı adım içerir yeni dağıtım yapılandırması için bir proje uzantısı oluşturma. Bu uzantı oluşturarak SharePoint projeleri yükseltme dağıtımı adımını kullanmak için SharePoint geliştiriciler yardımcı olur.  
  
 Sınıf uygulayan bir dağıtım yapılandırma oluşturmak üzere <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> arabirimi. Bir SharePoint proje uzantısı oluşturmak istediğinizde bu arabirimi uygular.  
  
#### <a name="to-create-the-deployment-configuration"></a>Dağıtım yapılandırması oluşturmak için  
  
1.  İçinde **DeploymentStepExtension** proje, DeploymentConfigurationExtension kod dosyasını açın ve ardından aşağıdaki kodu yapıştırın.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#2](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/deploymentstepextension/deploymentconfigurationextension.cs#2)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#2](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/deploymentstepextension/deploymentconfigurationextension.vb#2)]  
  
## <a name="creating-the-custom-sharepoint-commands"></a>Özel SharePoint komutları oluşturma  
 SharePoint sunucusu nesne modeline çağrılan iki özel komutlar oluşturun. Bir komut bir çözümü zaten dağıtılmış olup olmadığını belirler; diğer komut bir çözüm yükseltir.  
  
#### <a name="to-define-the-sharepoint-commands"></a>SharePoint komutları tanımlamak için  
  
1.  İçinde **SharePointCommands** proje, komutları kod dosyasını açın ve ardından aşağıdaki kodu yapıştırın.  
  
     [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#4](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/SharePointCommands/Commands.cs#4)]
     [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#4](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/sharepointcommands/commands.vb#4)]  
  
## <a name="checkpoint"></a>Denetim noktası  
 Bu noktada izlenecek özel dağıtım adımı ve SharePoint komutları için tüm kod var. Şimdi projeleri Hatasız derleme emin olmak için bunları oluşturun.  
  
#### <a name="to-build-the-projects"></a>Projeleri derlemek için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **DeploymentStepExtension** proje ve ardından **yapı**.  
  
2.  Kısayol menüsünü açın **SharePointCommands** proje ve ardından **yapı**.  
  
## <a name="creating-a-vsix-package-to-deploy-the-extension"></a>Uzantıyı dağıtmak için VSIX paket oluşturma  
 Uzantıyı dağıtmak için VSIX paketi oluşturmak için çözümünüz VSIX proje kullanın. İlk olarak VSIX paketi VSIX proje source.extension.vsixmanifest dosyasını değiştirerek yapılandırın. Çözümü derledikten sonra VSIX paketi oluşturun.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Yapılandırmak ve VSIX paketi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**altında **UpgradeDeploymentStep** proje, kısayol menüsünü açın **source.extension.vsixmanifest** dosya ve seçin **Açık**.  
  
     Visual Studio bildirim düzenleyicisinde dosyasını açar. Source.extension.vsixmanifest dosyanın tüm VSIX paketi gerektirir extension.vsixmanifest dosya temelini oluşturur. Bu dosya hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  İçinde **ürün adı** kutusuna **yükseltme dağıtımı adım SharePoint projeleri için**.  
  
3.  İçinde **Yazar** kutusuna **Contoso**.  
  
4.  İçinde **açıklama** kutusuna **SharePoint projelerinde kullanılabilir bir özel yükseltme dağıtım adımı sağlar**.  
  
5.  İçinde **varlıklar** sekmesini Düzenleyicisi, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
6.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `MefComponent` extension.vsixmanifest dosyasındaki öğesi. Bu öğe VSIX paketi bir uzantı bütünleştirilmiş kodun adını belirtir. Daha fazla bilgi için bkz: [MEFComponent öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
8.  İçinde **proje** listesinde, seçin **DeploymentStepExtension**ve ardından **Tamam** düğmesi.  
  
9. Bildirim düzenleyicisinde seçin **yeni** yeniden düğmesine tıklayın.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
10. İçinde **türü** listesinde, girin **SharePoint.Commands.v4**.  
  
    > [!NOTE]  
    >  Bu öğe, Visual Studio Uzantısı'nda dahil etmek istediğiniz özel bir uzantı belirtir. Daha fazla bilgi için bkz: [varlık öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737).  
  
11. İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
12. İçinde **proje** listesinde, seçin **SharePointCommands**ve ardından **Tamam** düğmesi.  
  
13. Menü çubuğunda seçin **yapı**, **yapı çözümü**ve ardından çözüm hatasız derlendiğinden emin olun.  
  
14. Yapı çıktı klasörüne UpgradeDeploymentStep projesi için şimdi UpgradeDeploymentStep.vsix dosya içerdiğinden emin olun.  
  
     Varsayılan olarak, yapı çıktı klasördür... Proje dosyasını içeren klasörü altındaki \bin\Debug klasörünü.  
  
## <a name="preparing-to-test-the-upgrade-deployment-step"></a>Yükseltme dağıtımı adım Test etmek hazırlanıyor  
 Yükseltme dağıtımı adım test etmek için örnek bir çözüm SharePoint sitesine dağıtmanız gerekir. Visual Studio'nun deneysel örneği uzantı hata ayıklamayı Başlat Bir liste tanımı ve dağıtım adımı test etmek için kullanılacak listesi örneği oluşturun ve bunları SharePoint sitesine dağıtabilirsiniz. Ardından, liste tanımını ve liste örneği değiştirin ve bunları nasıl varsayılan dağıtım işlemi SharePoint sitesinde çözümleri yazacak göstermek için yeniden dağıtın.  
  
 Daha sonra bu kılavuzda, liste tanımını ve liste örneği değiştireceksiniz ve ardından bunları SharePoint sitesinde yükseltmeniz.  
  
#### <a name="to-start-debugging-the-extension"></a>Hata ayıklama uzantısı başlatmak için  
  
1.  Yönetici kimlik bilgileriyle Visual Studio'yu yeniden başlatın ve ardından UpgradeDeploymentStep çözümü açın.  
  
2.  DeploymentStepExtension projesinde UpgradeStep kod dosyasını açın ve daha sonra bir kesme noktası kod ilk satırı ekleyin `CanExecute` ve `Execute` yöntemleri.  
  
3.  F5 tuşuna seçerek veya menü çubuğundaki hata ayıklama, seçme Başlat **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
4.  Visual Studio için SharePoint Projects\1.0 %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Upgrade dağıtım adımı uzantıyı yükleyen ve Visual Studio Deneysel bir örneğini başlatır. Visual Studio bu örneğinde yükseltme dağıtımı adım test edeceksiniz.  
  
#### <a name="to-create-a-sharepoint-project-with-a-list-definition-and-a-list-instance"></a>Bir SharePoint proje listesi tanımını ve bir liste örneği oluşturmak için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **dosya**, **yeni**, **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** düğümü veya **Visual Basic** düğümü genişletin **SharePoint** düğümü ve ardından seçin **2010** düğümü.  
  
3.  İletişim kutusunun üstündeki olduğundan emin olun **.NET Framework 3.5** .NET Framework sürümleri listesinde görüntülenir.  
  
     Projeler için [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] ve [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] .NET Framework'ün bu sürümünü gerektirir.  
  
4.  Proje şablonları listesinden seçip **SharePoint 2010 proje**, proje adı **EmployeesListDefinition**ve ardından **Tamam** düğmesi.  
  
5.  İçinde **SharePoint Özelleştirme Sihirbazı'nı**, hata ayıklama için kullanmak istediğiniz sitenin URL'sini girin.  
  
6.  Altında **bu SharePoint çözüm için güven düzeyini nedir**, seçin **Grup çözümü olarak dağıtma** seçenek düğmesi.  
  
    > [!NOTE]  
    >  Yükseltme dağıtımı adım korumalı çözümler desteklemiyor.  
  
7.  Seçin **son** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] EmployeesListDefinition projesi oluşturur.  
  
8.  EmployeesListDefinition proje için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni öğe**.  
  
9. İçinde **Yeni Öğe Ekle - EmployeesListDefinition** iletişim kutusunda, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
10. Seçin **listesi** öğe şablonu, öğe adı **çalışanlar listesi**ve ardından **Ekle** düğmesi.  
  
     SharePoint Özelleştirme Sihirbazı görünür  
  
11. Üzerinde **seçin listesi ayarları** sayfasında aşağıdaki ayarları doğrulayın ve ardından **son** düğmesi:  
  
    1.  **Çalışanlar listesi** görünür **hangi adı için listenizi görüntülemek istiyor musunuz?** kutusu.  
  
    2.  **Göre özelleştirilebilir bir liste oluşturur:** seçenek düğmesi seçilidir.  
  
    3.  **Varsayılan (boş)** seçilir **göre özelleştirilebilir bir liste oluşturur:** listesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Çalışanlar liste öğesi bir başlık sütunu ve boş bir örnek oluşturur ve Liste Tasarımcısı'nı açar.  
  
12. Liste Tasarımcısı'nda üzerinde **sütunları** sekmesinde, seçin **yeni veya var olan sütun adı yazın** satır ve ardından aşağıdaki sütunlarda ekleyin **sütun görünen adı** listesi:  
  
    1.  İlk adı  
  
    2.  Şirket  
  
    3.  İş Telefonu  
  
    4.  E-posta  
  
13. Tüm dosyaları kaydetmek ve liste Designer'ı kapatın.  
  
14. İçinde **Çözüm Gezgini**, genişletin **çalışanlar listesi** düğümünü genişletin ve ardından **çalışanlar listesi örneği** alt düğümü.  
  
15. Elements.xml dosyasında bu dosyada XML varsayılan aşağıdaki XML ile değiştirin. Bu XML listesine adını değiştirir **çalışanlar** ve Jim Hance adlandırılmış bir çalışanın bilgilerini ekler.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <ListInstance Title="Employees"  
                    OnQuickLaunch="TRUE"  
                    TemplateType="10000"  
                    Url="Lists/Employees"  
                    Description="Simple list to test upgrade deployment step">  
        <Data>  
          <Rows>  
            <Row>  
              <Field Name="Title">Hance</Field>  
              <Field Name="FirstName">Jim</Field>  
              <Field Name="Company">Contoso</Field>  
              <Field Name="Business Phone">555-555-5555</Field>  
              <Field Name="E-Mail">jim@contoso.com</Field>  
            </Row>  
          </Rows>  
        </Data>  
      </ListInstance>  
    </Elements>  
    ```  
  
16. Elements.xml dosyasını kaydedip kapatın.  
  
17. EmployeesListDefinition proje için kısayol menüsünü açın ve ardından **açık** veya **özellikleri**.  
  
     Özellikler Tasarımcısı'nı açar.  
  
18. Üzerinde **SharePoint** sekmesi, Temizle **otomatik-hata ayıklama sonra geri çekmek** onay kutusunu işaretleyin ve sonra Özellikler kaydedin.  
  
#### <a name="to-deploy-the-list-definition-and-list-instance"></a>Liste tanımını ve liste örneği dağıtmak için  
  
1.  İçinde **Çözüm Gezgini**, seçin **EmployeesListDefinition** proje düğümüne.  
  
2.  İçinde **özellikleri** penceresinde olduğundan emin olun **etkin Dağıtım Yapılandırması** özelliği ayarlanmış **varsayılan**.  
  
3.  F5 tuşuna seçin veya menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
4.  Proje başarıyla oluşturulur, web tarayıcısı SharePoint sitesine açıldığını doğrulayın, **listeler** Hızlı Başlatma çubuğu öğesinde yeni içeriyor **çalışanlar** listesi ve  **Çalışanlar** listesi Jim Hance için giriş içerir.  
  
5.  Web tarayıcısını kapatın.  
  
#### <a name="to-modify-the-list-definition-and-list-instance-and-redeploy-them"></a>Liste tanımını ve liste örneği değiştirmek ve bunları yeniden dağıtmak için  
  
1.  Bir alt öğesi olan Elements.xml dosya EmployeesListDefinition projeyi açın **çalışan listesi örneği** proje öğesi.  
  
2.  Kaldırma `Data` öğesi ve alt giriş Jim Hance için listeden kaldırın.  
  
     İşiniz bittiğinde, dosyanın aşağıdaki XML içermelidir.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <ListInstance Title="Employees"  
                    OnQuickLaunch="TRUE"  
                    TemplateType="10000"  
                    Url="Lists/Employees"  
                    Description="Simple list to test upgrade deployment step">  
      </ListInstance>  
    </Elements>  
    ```  
  
3.  Elements.xml dosyasını kaydedip kapatın.  
  
4.  Kısayol menüsünü açın **çalışanlar listesi** öğesi proje ve ardından **açık** veya **özellikleri**.  
  
5.  Liste Tasarımcısı'nda seçin **görünümleri** sekmesi.  
  
6.  İçinde **seçili sütunların** listesinde, seçin **ekleri**ve ardından < bu sütunu taşımak için anahtar **kullanılabilir sütunlar** listesi.  
  
7.  Taşımak için önceki adımı yineleyin **iş telefonu** sütundan **seçili sütunların** listesinin **kullanılabilir sütunlar** listesi.  
  
     Bu eylem bu alanlar varsayılan görünümden kaldırır **çalışanlar** SharePoint sitesinde listesi.  
  
8.  F5 tuşuna seçerek veya menü çubuğundaki hata ayıklama, seçme Başlat **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
9. Doğrulayın **dağıtım çakışmaları** iletişim kutusu görüntülenir.  
  
     (Liste örneği) bir çözümü dağıtmak Visual Studio çalıştığında, bu iletişim kutusu için bu çözüm zaten dağıtılmış bir SharePoint sitesine görüntülenir. Bu kılavuzda daha sonra yükseltme dağıtımı adım yürüttüğünüzde bu iletişim kutusunda görüntülenmez.  
  
10. İçinde **dağıtım çakışmaları** iletişim kutusunda, seçin **otomatik olarak çözümlemek** seçenek düğmesi.  
  
     Visual Studio SharePoint sitesinde listesi örneği siler, liste öğesi projesinde dağıtır ve sonra SharePoint sitesine açar.  
  
11. İçinde **listeler** bölüm Hızlı Başlatma çubuğu seçmek **çalışanlar** listesine ve ardından aşağıdaki ayrıntıları doğrulayın:  
  
    -   **Ekleri** ve **ev telefonu** sütunları bu liste görünümünde görünmez.  
  
    -   Liste boş olduğu. Kullanıldığında, **varsayılan** çözümü yeniden dağıtmak için Dağıtım Yapılandırması **çalışanlar** listesi projenizdeki yeni boş listeyle değişti.  
  
## <a name="testing-the-deployment-step"></a>Dağıtım adımı test etme  
 Artık yükseltme dağıtımı adım test etmek hazırsınız. İlk olarak, SharePoint listesi örneği için bir öğe ekleyin. Liste tanımını ve liste örneği değiştirmek, SharePoint sitesinde yükseltme ve yükseltme dağıtımı adım yeni öğenin üzerine değildir onaylayın.  
  
#### <a name="to-manually-add-an-item-to-the-list"></a>El ile bir öğeyi listeye eklemek için  
  
1.  SharePoint sitesinde, şeritte altında **liste Araçları** sekmesinde, seçin **öğeleri** sekmesi.  
  
2.  İçinde **yeni** grubunda, seçin **yeni öğe**.  
  
     Alternatif olarak, seçtiğiniz **Yeni Öğe Ekle** öğesi listede bağlantıyı.  
  
3.  İçinde **çalışanlar - yeni öğe** penceresi, **başlık** kutusuna **tesis Yöneticisi**.  
  
4.  İçinde **ad** kutusuna **herkesi**.  
  
5.  İçinde **şirket** kutusuna **Contoso**.  
  
6.  Seçin **kaydetmek** düğmesini, yeni öğe listede göründüğünden emin olun ve ardından web tarayıcısını kapatın.  
  
     Bu kılavuzda daha sonra bu listenin içeriği yükseltme dağıtımı adım üzerine değildir doğrulamak için bu öğeyi kullanır.  
  
#### <a name="to-test-the-upgrade-deployment-step"></a>Yükseltme dağıtımı adım test etmek için  
  
1.  Visual Studio deneysel örneğinde içinde **Çözüm Gezgini**, kısayol menüsünü açın **EmployeesListDefinition** proje düğümünü ve ardından **özellikleri**.  
  
     Özellikler Düzenleyicisi/Tasarımcısı'nı açar.  
  
2.  Üzerinde **SharePoint** sekmesinde, ayarlamak **etkin Dağıtım Yapılandırması** özelliğine **yükseltme**.  
  
     Bu özel dağıtım yapılandırması yeni yükseltme dağıtımı adım içerir.  
  
3.  Kısayol menüsünü açın **çalışanlar listesi** öğesi proje ve ardından **özellikleri** veya **açık**.  
  
     Özellikler Düzenleyicisi/Tasarımcısı'nı açar.  
  
4.  Üzerinde **görünümleri** sekmesinde, seçin **e-posta** sütun ve ardından **<** bu sütunundan taşımak için anahtar **seçili sütunların**listesinin **kullanılabilir sütunlar** listesi.  
  
     Bu eylem bu alanlar varsayılan görünümden kaldırır **çalışanlar** SharePoint sitesinde listesi.  
  
5.  F5 tuşuna seçerek veya menü çubuğundaki hata ayıklama, seçme Başlat **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
6.  Visual Studio'nun diğer örnek kodda, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `CanExecute` yöntemi.  
  
7.  F5 tuşuna yeniden seçin veya menü çubuğunda seçin **hata ayıklama**, **devam**.  
  
8.  Kod, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `Execute` yöntemi.  
  
9. F5 tuşuna seçin veya menü çubuğunda seçin **hata ayıklama**, **devam** son kez.  
  
     Web tarayıcısı, SharePoint sitesini açar.  
  
10. İçinde **listeler** bölüm Hızlı Başlat alanının seçin **çalışanlar** listesine ve ardından aşağıdaki ayrıntıları doğrulayın:  
  
    -   Daha önce (herkesi için tesis Yöneticisi) el ile eklenen hala listesinde öğesidir.  
  
    -   **İş telefonu** ve **e-posta adresi** sütunları bu liste görünümünde görünmez.  
  
     **Yükseltme** dağıtım yapılandırmasını değiştirir varolan **çalışanlar** SharePoint sitesinde listesi örneği. Kullandıysanız **varsayılan** yerine dağıtım yapılandırması **yükseltme** yapılandırması, bir dağıtım çakışma karşılaştığınız. Visual Studio çözmek çakışma değiştirerek **çalışanlar** listesi ve öğe herkesi, tesis Yöneticisi için silinecektir.  
  
## <a name="cleaning-up-the-development-computer"></a>Geliştirme bilgisayarı temizleme  
 Yükseltme dağıtımı adım testi tamamladıktan sonra liste tanımını ve liste örneği SharePoint sitesinden kaldırın ve Visual Studio'dan dağıtım adımı uzantısı kaldırın.  
  
#### <a name="to-remove-the-list-instance-from-the-sharepoint-site"></a>Liste örneği SharePoint sitesinden kaldırmak için  
  
1.  Açık **çalışanlar** listesi zaten açık değilse SharePoint sitesinde listeleyin.  
  
2.  SharePoint sitesinde Şeritte seçin **liste Araçları** sekmesini ve ardından **listesi** sekmesi.  
  
3.  İçinde **ayarları** grubunda, seçin **listesi ayarları** öğesi.  
  
4.  Altında **izinler ve Yönetim**, seçin **bu listeyi Sil** komutu, seçin **Tamam** listesi Geri Dönüşüm Kutusu'na göndermek ve web kapatın istediğinizi onaylamak için Tarayıcı.  
  
#### <a name="to-remove-the-list-definition-from-the-sharepoint-site"></a>Liste tanımını SharePoint sitesinden kaldırmak için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **yapı**, **Geri Al**.  
  
     Visual Studio listesi tanımını SharePoint sitesinden geri çeker.  
  
#### <a name="to-uninstall-the-extension"></a>Uzantıyı kaldırmak için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantıları listesinden seçip **yükseltme dağıtımı adım SharePoint projeleri için**ve ardından **kaldırma** komutu.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** uzantısı kaldırın ve ardından istediğinizi onaylamak için **şimdi yeniden Başlat** kaldırma işleminin tamamlanması için.  
  
4.  Visual Studio (deneysel örneği ve Visual Studio UpgradeDeploymentStep çözüm açıksa örneğini) hem örneklerini kapatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Paketleme ve Dağıtımını Genişletme](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
  