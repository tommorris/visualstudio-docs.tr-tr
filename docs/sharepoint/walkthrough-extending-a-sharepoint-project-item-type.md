---
title: 'İzlenecek yol: bir SharePoint proje öğesi türünü genişletme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b7d0604e0e80fcb0fa14c65bd57669f60e68fd11
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118271"
---
# <a name="walkthrough-extend-a-sharepoint-project-item-type"></a>İzlenecek yol: bir SharePoint proje öğesi türünü genişletme
  Kullanabileceğiniz **iş verileri bağlantı modeli** SharePoint'te iş verileri bağlantı (BDC) hizmeti için bir model oluşturmak için proje öğesi. Bu proje öğesi kullanarak bir model oluşturduğunuzda varsayılan olarak, veri modelinde kullanıcılara görüntülenmez. Ayrıca kullanıcıların verileri görmesine izin ver SharePoint'te dış liste oluşturmanız gerekir.  
  
 Bu kılavuzda, bir uzantı için oluşturacağınız **iş verileri bağlantı modeli** proje öğesi. Geliştiriciler uzantısını verileri BDC modeli görüntüler kendi projesinde dış liste oluşturmak için kullanabilirsiniz. Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Visual Studio uzantısı oluşturma iki ana görevleri gerçekleştirir:  
  
    -   Bir BDC modeli verileri görüntüleyen dış liste oluşturur. Uzantısı oluşturmak için SharePoint Proje sisteminin nesne modelini kullanan bir *Elements.xml* listesi tanımlayan dosyası. Böylece BDC modeli ile birlikte dağıtılan projeye de dosyası ekler.  
  
    -   Bir kısayol menü öğesine ekler **iş verileri bağlantı modeli** proje öğelerinde **Çözüm Gezgini**. Geliştiriciler BDC modeli için dış liste oluşturmak için bu menü öğesi tıklatabilirsiniz.  
  
-   Uzantı derlemesi dağıtmak için Visual Studio Uzantısı (VSIX) paketi oluşturma.  
  
-   Testi uzantısı.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Microsoft Windows, SharePoint ve Visual Studio sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!include[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Bu kılavuzda kullanılır **VSIX proje** Şablonu proje öğesi dağıtmak için VSIX paket oluşturmak için SDK. Daha fazla bilgi için bkz: [Visual Studio'da SharePoint araçları genişletmek](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Aşağıdaki kavramlar bilgisi yararlı, ancak gerekli değildir, izlenecek yolu tamamlamak için:  
  
-   BDC hizmetinde [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]. Daha fazla bilgi için bkz: [BDC mimarisi](http://go.microsoft.com/fwlink/?LinkId=177798).  
  
-   BDC modeli için XML şeması. Daha fazla bilgi için bkz: [BDC modeli altyapı](http://go.microsoft.com/fwlink/?LinkId=177799).  
  
## <a name="create-the-projects"></a>Projeleri oluşturma
 Bu izlenecek yolu tamamlamak için iki proje oluşturmanız gerekir:  
  
-   Proje öğesi uzantısı dağıtmak için VSIX paketi oluşturmak için bir VSIX proje.  
  
-   Proje öğesi uzantısı uygulayan bir sınıf kitaplığı proje.  
  
 İzlenecek yol projeleri oluşturarak başlayın.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Menü çubuğunda seçin **dosya** > **yeni** > **proje**.  
  
3.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **genişletilebilirlik** düğümü.  
  
    > [!NOTE]  
    >  **Genişletilebilirlik** düğümdür yalnızca Visual Studio SDK'sı yüklerseniz kullanılabilir. Daha fazla bilgi için bu konudaki Önkoşullar bölümüne bakın.  
  
4.  Listedeki en üstündeki **yeni proje** iletişim kutusunda, seçin **.NET Framework 4.5**.  
  
     SharePoint araç uzantıları .NET Framework'ün bu sürümünde özellikleri gerektirir.  
  
5.  Seçin **VSIX proje** şablonu.  
  
6.  İçinde **adı** kutusuna **GenerateExternalDataLists**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **GenerateExternalDataLists** için proje **Çözüm Gezgini**.  
  
7.  Source.extension.vsixmanifest dosya otomatik olarak açık değilse, GenerateExternalDataLists projesinde kısayol menüsünü açın ve ardından **açın**  
  
8.  Source.extension.vsixmanifest dosya boş olmayan giriş olduğunu doğrulayın (Contoso girin) Yazar alanı için dosyayı kaydedin ve kapatın.  
  
#### <a name="to-create-the-extension-project"></a>Uzantı projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **GenerateExternalDataLists** çözüm düğümünü seçin **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **Yeni Proje Ekle** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **Windows** düğümü.  
  
3.  İletişim kutusunun üstündeki listede seçin **.NET Framework 4.5**.  
  
4.  Proje şablonları listesinden seçip **sınıf kitaplığı**.  
  
5.  İçinde **adı** kutusuna **BdcProjectItemExtension**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **BdcProjectItemExtension** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
6.  Class1 kod dosyasının projeden silin.  
  
## <a name="configure-the-extension-project"></a>Uzantı projesi yapılandırın
 Proje öğesi uzantısı oluşturma için kod yazmadan önce ve uzantı projesi derleme başvurularını kod dosyaları ekleyin.  
  
#### <a name="to-configure-the-project"></a>Projeyi yapılandırmak için  
  
1.  BdcProjectItemExtension projesinde aşağıdaki adlara sahip iki kod dosyaları ekleyin:  
  
    -   ProjectItemExtension  
  
    -   GenerateExternalDataLists  
  
2.  BdcProjectItemExtension projesini seçin ve ardından, menü çubuğunda, **proje** > **Başvuru Ekle**.  
  
3.  Altında **derlemeleri** düğümü seçin **Framework** düğümü ve her biri aşağıdaki derlemeler için onay kutusunu seçin:  
  
    -   System.ComponentModel.Composition  
  
    -   WindowsBase  
  
4.  Altında **derlemeleri** düğümü seçin **uzantıları** düğümünü ve ardından onay kutusunu şu derleme için:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  Seçin **Tamam** düğmesi.  
  
## <a name="define-the-project-item-extension"></a>Proje öğesi uzantısı tanımlayın
 Uzantısı tanımlayan bir sınıf oluşturma **iş verileri bağlantı modeli** proje öğesi. Sınıf Implements uzantısı tanımlamak için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> arabirimi. Varolan bir proje öğesi türünü genişletme istediğinizde bu arabirimi uygular.  
  
#### <a name="to-define-the-project-item-extension"></a>Proje öğesi uzantısı tanımlamak için  
  
1.  Aşağıdaki kod ProjectItemExtension kod dosyasına yapıştırın.  
  
    > [!NOTE]  
    >  Bu kod ekledikten sonra projeyi bazı derleme hataları sahip olur. Sonraki adımlarda kodu eklediğinizde, bu hataları kaybolur.  
  
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../sharepoint/codesnippet/CSharp/generateexternaldatalists/bdcprojectitemextension/projectitemextension.cs#1)]
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../sharepoint/codesnippet/VisualBasic/generateexternaldatalists/bdcprojectitemextension/projectitemextension.vb#1)]  
  
## <a name="create-the-external-data-lists"></a>Dış veri listeleri oluşturma
 Kısmi tanımlaması Ekle `GenerateExternalDataListsExtension` her varlık için bir dış veri listesi BDC modeli oluşturur sınıfı. Dış veri listesi oluşturmak için bu kodu ilk BDC modeli varlık verilerde BDC modeli dosyası XML verilerinde ayrıştırarak okur. Ardından, BDC modeli üzerine kurulmuştur ve bu liste örneği projeye ekler bir liste örneği oluşturur.  
  
#### <a name="to-create-the-external-data-lists"></a>Dış veri listeleri oluşturmak için  
  
1.  Aşağıdaki kod GenerateExternalDataLists kod dosyasına yapıştırın.  
  
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../sharepoint/codesnippet/VisualBasic/generateexternaldatalists/bdcprojectitemextension/generateexternaldatalists.vb#2)]
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../sharepoint/codesnippet/CSharp/generateexternaldatalists/bdcprojectitemextension/generateexternaldatalists.cs#2)]  
  
## <a name="checkpoint"></a>Denetim noktası  
 Bu noktada kılavuzda tüm proje öğesi uzantısı artık projede kodudur. Proje hatasız derlendiğinden emin olmak için çözümü oluşturun.  
  
#### <a name="to-build-the-solution"></a>Çözümü derlemek için  
  
1.  Menü çubuğunda seçin **yapı** > **yapı çözümü**.  
  
## <a name="create-a-vsix-package-to-deploy-the-project-item-extension"></a>Proje öğesi uzantısı dağıtmak için VSIX paket oluşturma
 Uzantıyı dağıtmak için VSIX paketi oluşturmak için çözümünüz VSIX proje kullanın. İlk olarak VSIX paketi VSIX projeye dahil source.extension.vsixmanifest dosyasını değiştirerek yapılandırın. Çözümü derledikten sonra VSIX paketi oluşturun.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Yapılandırmak ve VSIX paketi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**GenerateExternalDataLists projesinde source.extension.vsixmanifest dosya için kısayol menüsünü açın ve ardından **açmak**.  
  
     Visual Studio bildirim düzenleyicisinde dosyasını açar. Extension.vsixmanifest dosya için temel göre tüm VSIX paketi gerekli source.extension.vsixmanifest dosyasıdır. Bu dosya hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  İçinde **ürün adı** kutusuna **dış veri listesi Oluşturucusu**.  
  
3.  İçinde **Yazar** kutusuna **Contoso**.  
  
4.  İçinde **açıklama** kutusuna **dış veri listeleri oluşturmak için kullanılan iş verileri bağlantı modeli proje öğeleri için bir uzantı**.  
  
5.  Üzerinde **varlıklar** sekmesini Düzenleyicisi, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
6.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `MefComponent` extension.vsixmanifest dosyasındaki öğesi. Bu öğe VSIX paketi bir uzantı bütünleştirilmiş kodun adını belirtir. Daha fazla bilgi için bkz: [MEFComponent öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
8.  İçinde **proje** listesinde, seçin **BdcProjectItemExtension**ve ardından **Tamam** düğmesi.  
  
9. Menü çubuğunda seçin **yapı** > **yapı çözümü**.  
  
10. Proje derlenir ve hatasız oluşturulduğunu doğrulayın.  
  
11. Yapı çıktı klasörüne GenerateExternalDataLists projesi için şimdi GenerateExternalDataLists.vsix dosya içerdiğinden emin olun.  
  
     Varsayılan olarak, yapı çıktı klasördür... Proje dosyasını içeren klasörü altındaki \bin\Debug klasörünü.  
  
## <a name="test-the-project-item-extension"></a>Proje öğesi uzantısı test
 Şimdi proje öğesi uzantısı test etmek hazırsınız. İlk olarak, Visual Studio'nun deneysel örneği uzantısı projesinde hata ayıklamayı Başlat. Ardından, bir BDC modeli için dış liste oluşturmak için Visual Studio'nun deneysel örneği uzantı kullanın. Son olarak, beklendiği gibi çalıştığını doğrulamak için SharePoint sitesinde dış listesini açın.  
  
#### <a name="to-start-debugging-the-extension"></a>Hata ayıklama uzantısı başlatmak için  
  
1.  Gerekirse, yönetici kimlik bilgileriyle Visual Studio'yu yeniden başlatın ve GenerateExternalDataLists çözümü açın.  
  
2.  BdcProjectItemExtension projesinde ProjectItemExtension kod dosyasını açın ve daha sonra bir kesme noktası kod satırı ekleyin `Initialize` yöntemi.  
  
3.  GenerateExternalDataLists kod dosyasını açın ve daha sonra bir kesme noktası kod ilk satırı ekleyin `GenerateExternalDataLists_Execute` yöntemi.  
  
4.  Seçerek hata ayıklamayı Başlat **F5** anahtar veya menü çubuğu seçme **hata ayıklama** > **hata ayıklamayı Başlat**.  
  
     Visual Studio %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\External veri listesi Generator\1.0 uzantıyı yükleyen ve Visual Studio Deneysel bir örneğini başlatır. Proje öğesi Visual Studio'nun bu örnekte test edeceğiz.  
  
#### <a name="to-test-the-extension"></a>Uzantı sınamak için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **dosya** > **yeni** > **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **şablonları** düğümünü genişletin **Visual C#** düğümü, genişletin **SharePoint** düğümü ve ardından seçin **2010**.  
  
3.  İletişim kutusunun üstündeki listesinde olduğundan emin olun **.NET Framework 3.5** seçilir. Projeler için [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] .NET Framework'ün bu sürümünü gerektirir.  
  
4.  Proje şablonları listesinden seçip **SharePoint 2010 proje**.  
  
5.  İçinde **adı** kutusuna **SharePointProjectTestBDC**ve ardından **Tamam** düğmesi.  
  
6.  SharePoint Özelleştirme Sihirbazı'nda hata ayıklama için kullanmak, seçmek istediğiniz sitenin URL'sini girin **Grup çözümü olarak dağıtma**ve ardından **son**düğmesi.  
  
7.  SharePointProjectTestBDC proje için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni öğe**.  
  
8.  İçinde **eklemek NewItem - SharePointProjectTestBDC** iletişim kutusunda, yüklü dil düğümünü genişletin, **SharePoint** düğümü.  
  
9. Seçin **2010** düğümünü ve ardından **iş verileri bağlantı modeli (yalnızca Grup çözümünün)** şablonu.  
  
10. İçinde **adı** kutusuna **TestBDCModel**ve ardından **Ekle** düğmesi.  
  
11. Visual Studio'nun diğer örnek kodda, kümesinde kesme noktası durdurduğunu doğrulayın `Initialize` ProjectItemExtension kod dosyasının yöntemi.  
  
12. Visual Studio durdurulmuş örneğini seçin **F5** anahtar veya menü çubuğunda seçin **hata ayıklama** > **devam** projede hataları ayıklamak devam etmek için.  
  
13. Visual Studio Deneysel örneğini seçin **F5** anahtar veya menü çubuğunda seçin **hata ayıklama** > **hata ayıklamayı Başlat** oluşturmak, dağıtmak ve çalıştırmak **TestBDCModel** projesi.  
  
     Varsayılan sayfanın hata ayıklama için belirtilen SharePoint sitesi için web tarayıcısı açılır.  
  
14. Doğrulayın **listeler** hızlı başlat alanında bölümünde projedeki varsayılan BDC modeli dayalı bir liste henüz içermiyor. SharePoint kullanıcı arabirimini kullanarak veya proje öğesi uzantısı kullanarak bir dış veri listesi önce oluşturmanız gerekir.  
  
15. Web tarayıcısını kapatın.  
  
16. TestBDCModel proje açtığı Visual Studio örneğinde için kısayol menüsünü açın **TestBDCModel** düğümünde **Çözüm Gezgini**ve ardından **dış veri oluştur Liste**.  
  
17. Visual Studio'nun diğer örnek kodda, kümesinde kesme noktası durdurduğunu doğrulayın `GenerateExternalDataLists_Execute` yöntemi. Seçin **F5** anahtar veya menü çubuğunda seçin **hata ayıklama** > **devam** projede hataları ayıklamak devam etmek için.  
  
18. Visual Studio'nun deneysel örneği adlı bir liste örneği ekler **Entity1DataList** TestBDCModel proje ve örnek de oluşturur adlı bir özellik **Feature2** listesi örneği.  
  
19. Seçin **F5** anahtar veya menü çubuğunda seçin **hata ayıklama** > **hata ayıklamayı Başlat** oluşturmak için dağıtmak ve TestBDCModel projesini çalıştırın.  
  
     Hata ayıklama için kullanılan SharePoint sitesinin varsayılan sayfasına web tarayıcısı açılır.  
  
20. İçinde **listeler** bölüm Hızlı Başlat alanının seçin **Entity1DataList** listesi.  
  
21. Listenin Identifier1 ve ileti Identifier1 değerinin 0 ve Hello World iletisi değerine sahip bir öğe ek olarak adlandırılan sütunları içerdiğini doğrulayın.  
  
     **İş verileri bağlantı modeli** proje şablonu tüm bu verileri sağlayan varsayılan BDC modeli oluşturur.  
  
22. Web tarayıcısını kapatın.  
  
## <a name="clean-up-the-development-computer"></a>Geliştirme bilgisayarı temizleme
 Proje öğesi uzantısı test ettikten sonra BDC modeli ve dış liste SharePoint sitesinden ve proje öğesi uzantısı Visual Studio'dan kaldırın.  
  
#### <a name="to-remove-the-external-data-list-from-the-sharepoint-site"></a>Dış veri listesi SharePoint sitesinden kaldırmak için  
  
1.  SharePoint sitesi Hızlı Başlat bölümünde seçin **Entity1DataList** listesi.  
  
2.  SharePoint sitesinde Şeritte seçin **listesi** sekmesi.  
  
3.  Üzerinde **listesi** sekmesinde **ayarları** grubunda, seçin **listesi ayarları**.  
  
4.  Altında **izinler ve Yönetim**, seçin **bu listeyi Sil**ve ardından **Tamam** listesi Geri Dönüşüm Kutusu'na göndermek istediğinizi onaylamak için.  
  
5.  Web tarayıcısını kapatın.  
  
#### <a name="to-remove-the-bdc-model-from-the-sharepoint-site"></a>BDC modeli SharePoint sitesinden kaldırmak için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **yapı** > **Geri Al**.  
  
     Visual Studio BDC modeli SharePoint sitesinden ortadan kaldırır.  
  
#### <a name="to-remove-the-project-item-extension-from-visual-studio"></a>Proje öğesi uzantısı Visual Studio'dan kaldırmak için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **Araçları** > **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantıları listesinden seçip **dış veri listesi Oluşturucusu**ve ardından **kaldırma** düğmesi.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** , uzantıyı kaldırmak istediğinizi onaylamak için.  
  
4.  Seçin **şimdi yeniden Başlat** kaldırma işleminin tamamlanması için.  
  
5.  Visual Studio (deneysel örneği ve GenerateExternalDataLists çözüm açıksa örneği) hem örneklerini kapatın.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md)   
 [İş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [İş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  
