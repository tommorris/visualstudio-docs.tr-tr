---
title: Visual Studio'da SharePoint araçları için hata ayıklama uzantıları | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying extensions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7c49e12b7357cc8f3aa6ce9f7cbdcd02294cc253
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-extensions-for-the-sharepoint-tools-in-visual-studio"></a>Visual Studio'da SharePoint Araçları için Hata Ayıklama Uzantıları
  Bir SharePoint araçları uzantısı dağıtmak için Oluştur bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantı derlemesi ve uzantısıyla dağıtmak istediğiniz diğer dosyaları içeren uzantısı (VSIX) paketi. VSIX paketi açık paketleme kuralları (OPC) standart izleyen sıkıştırılmış bir dosyadır. VSIX paket .vsix uzantısına sahiptir.  
  
 VSIX paketi oluşturduktan sonra diğer kullanıcıların uzantınızı yüklemek için .vsix dosyasını çalıştırabilirsiniz. Bir kullanıcı uzantınızı yüklendiğinde, tüm dosyaları %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0\Extensions klasörüne yüklenir. Uzantıyı dağıtmak için VSIX paketi yükleyebilirsiniz [Visual Studio Galerisi](http://go.microsoft.com/fwlink/?LinkID=123847) Web sitesi veya dağıtmak paket müşterileriniz için başka bir yöntemle bir ağ paylaşımına veya başka bir Web sitesinin paketinin barındırma gibi bazı.  
  
 VSIX paketleri oluşturma ve bunları dağıtma hakkında daha fazla bilgi için [Visual Studio Galerisi](http://go.microsoft.com/fwlink/?LinkID=123847), bkz: [sevkiyat Visual Studio uzantıları](/visualstudio/extensibility/shipping-visual-studio-extensions).  
  
 VSIX paketi kullanarak oluşturabileceğiniz **VSIX proje** Visual Studio veya şablonda oluşturabilirsiniz VSIX paketi el ile.  
  
## <a name="using-vsix-projects-to-create-vsix-packages"></a>VSIX paket oluşturmak için VSIX projeleri kullanma  
 Kullanabileceğiniz **VSIX proje** Visual Studio SharePoint araç uzantılarının VSIX paket oluşturmak için SDK tarafından sağlanan şablonu. VSIX proje kullanarak VSIX paketi el ile oluşturma üzerinde çeşitli avantajlar sunar:  
  
-   Projeyi derlerken visual Studio VSIX paketi otomatik olarak oluşturur. Paketi dağıtım dosyaları eklemeyi ve paketi için [Content_Types] .xml dosyası oluşturma gibi görevleri sizin için yapılır.  
  
-   Uzantı projesi ve proje şablonları ve öğe şablonları gibi diğer dosyaları yapı çıktısını VSIX paketinde dahil etmek için VSIX proje yapılandırabilirsiniz.  
  
 VSIX proje kullanma hakkında daha fazla bilgi için bkz: [VSIX proje şablonu](/visualstudio/extensibility/vsix-project-template).  
  
### <a name="organizing-your-projects"></a>Projelerinizi düzenleme  
 Varsayılan olarak, VSIX projeleri yalnızca VSIX paket, değil derlemeleri oluşturur. Bu nedenle, genellikle bir SharePoint araçları uzantısı bir VSIX proje ile kullanılmaz. Genellikle en az iki projelerle çalışmak:  
  
-   Bir VSIX proje.  
  
-   Uzantınızı uygulayan bir sınıf kitaplığı proje.  
  
 Ek projelerle Ayrıca belirli ve uzantı türlerini çalışabilir:  
  
-   Uzantı tarafından kullanılan herhangi bir SharePoint komut uygulayan bir sınıf kitaplığı projesi. Bu senaryo izlenecek yol için bkz: [izlenecek yol: Görüntü Web bölümleri için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md).  
  
-   Uzantınızı yeni bir SharePoint proje öğesi türünü tanımlıyorsa oluşturan bir öğe şablonu veya proje şablonu, bir öğe şablonu veya proje şablonu projesi. Bu senaryo izlenecek yol için bkz: [izlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  
  
-   Bir şablon uzantınızı içeriyorsa, özel sihirbaz bir öğe şablonu veya proje şablonu uygulayan bir sınıf kitaplığı projesi. Bu senaryo izlenecek yol için bkz: [izlenecek yol: bir öğe şablonu, bölüm 2 ile özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md).  
  
 Tüm projeleri aynı Visual Studio çözümünde eklerseniz, Sınıf Kitaplığı projelerinde derleme çıktısı dahil etmek için VSIX proje source.extension.vsixmanifest dosyasında değiştirebilirsiniz.  
  
### <a name="editing-the-vsix-manifest"></a>VSIX bildirimini düzenleme  
 Uzantı dahil etmek istediğiniz tüm öğelerin girişlerini dahil etmek için VSIX proje source.extension.vsixmanifest dosyasını düzenlemeniz gerekir. Kendi kısayol menüsünden source.extension.vsixmanifest dosyayı açtığınızda, dosya dosyasındaki XML düzenleme için bir kullanıcı Arabirimi sağlayan bir Tasarımcısı'nda görünür. Daha fazla bilgi için bkz: [VSIX bildirim Tasarımcısı](/visualstudio/extensibility/vsix-manifest-designer).  
  
 Aşağıdaki öğeler için source.extension.vsixmanifest dosyası girişleri eklemeniz gerekir:  
  
-   Uzantı derlemesi.  
  
-   Uzantı tarafından kullanılan herhangi bir SharePoint komut uygulayan derleme.  
  
-   Bir proje şablonları veya uzantısı ile ilişkili öğe şablonları.  
  
-   Uzantısı ile ilişkili olan bir şablon için özel bir sihirbaz.  
  
 Aşağıdaki yordamlar, girişleri .vsixmanifest dosyasına bu öğelerin her biri için ekleme işlemi açıklanmaktadır.  
  
##### <a name="to-include-the-extension-assembly"></a>Uzantı derlemeyi dahil etmek için  
  
1.  VSIX proje source.extension.vsixmanifest dosya için kısayol menüsünü açın ve ardından **açmak**.  
  
     Tasarımcıda dosyayı açar  
  
2.  Üzerinde **varlıklar** sekmesini Düzenleyicisi, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
3.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.MefComponent**.  
  
4.  İçinde **kaynak** listesinde, aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Uzantı derlemesi VSIX proje olarak aynı çözüme bir projesi oluşturulur kaldığınızda **geçerli çözümdeki bir proje ile**. İçinde **proje** listesinde, projenin adını seçin.  
  
    -   Uzantı derlemesi projenizi bir dosya olarak eklenirse seçin **filesystem dosyada**. İçinde **yolu** listesinde, uzantısı derleme dosyasının tam yolunu girin veya kullanmak **Gözat** düğmesine bulun ve derleme dosyasını seçin.  
  
5.  Seçin **Tamam** düğmesi.  
  
##### <a name="to-include-a-sharepoint-command-assembly"></a>Bir SharePoint komutu derlemeyi dahil etmek için  
  
1.  VSIX proje source.extension.vsixmanifest dosya için kısayol menüsünü açın ve ardından **açmak** düğmesi.  
  
     Dosya Tasarımcısı'nda açılır.  
  
2.  İçinde **varlıklar** bölüm Düzenleyicisi, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
3.  İçinde **türü** kutusuna **SharePoint.Commands.v4**.  
  
4.  İçinde **kaynak** listesinde, aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   VSIX proje olarak aynı çözüme bulunduğu bir projeden komutu derleme oluşturulduysa seçin **geçerli çözümdeki bir proje ile**. İçinde **proje** listesinde, projenin adını seçin.  
  
    -   Komut derleme projenizi bir dosya olarak eklenirse seçin **filesystem dosyada**. İçinde **yolu** listesinde, uzantısı derleme dosyasının tam yolunu girin veya kullanmak **Gözat** düğmesine bulun ve derleme dosyasını seçin.  
  
5.  Seçin **Tamam** düğmesi.  
  
##### <a name="to-include-a-template-that-you-create"></a>Oluşturduğunuz bir şablonu eklemek için  
  
1.  VSIX proje source.extension.vsixmanifest dosya için kısayol menüsünü açın ve ardından **açmak** düğmesi.  
  
     Dosya Tasarımcısı'nda açılır.  
  
2.  İçinde **varlıklar** bölüm Düzenleyicisi, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
3.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.ProjectTemplate** veya **Microsoft.VisualStudio.ItemTemplate**.  
  
4.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
5.  İçinde **proje** listesinde, projenin adını seçin ve ardından **Tamam** düğmesi.  
  
6.  İçinde **Çözüm Gezgini**proje şablonu veya öğe şablonu projeniz için kısayol menüsünü açın ve ardından **projeyi**.  
  
7.  Proje düğümünün kısayol menüsünün yeniden açın ve ardından **Düzenle***YourTemplateProjectName***.csproj** veya **Düzenle***YourTemplateProjectName***. vbproj**.  
  
8.  Aşağıdaki bulun `VSTemplate` proje öğesi.  
  
    ```  
    <VSTemplate Include="YourTemplateName.vstemplate">  
    ```  
  
9. Bu öğe aşağıdaki XML ile değiştirin.  
  
    ```  
    <VSTemplate Include="YourTemplateName.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` Öğesi ek klasörler altında proje şablonu oluşturulduğu projeyi derlerken yolu belirtir. Burada belirtilen klasörleri yalnızca Müşteriler açtığınızda öğe şablonu kullanılabilir olacağından emin olmak **Yeni Proje Ekle** iletişim kutusunda, genişletin **SharePoint** düğümünü ve ardından **2010**  düğüm.  
  
10. Dosyayı kaydedin ve kapatın.  
  
11. İçinde **Çözüm Gezgini**proje şablonu veya öğe şablonu projesinin kısayol menüsünü açın ve ardından **projeyi yeniden yükle**.  
  
##### <a name="to-include-a-template-that-you-create-manually"></a>El ile oluşturduğunuz bir şablonu eklemek için  
  
1.  VSIX proje şablonu içerecek şekilde projeye yeni bir klasör ekleyin.  
  
2.  Bu yeni klasörü altında aşağıdaki alt klasörleri oluşturun ve sonra şablonu (.zip) dosyasına ekleyin *yerel ayar kimliği* klasör.  
  
     *YourTemplateFolder*  
  
     **SharePoint**  
  
     **SharePoint14**  
  
     *Yerel ayar kimliği*  
  
     *YourTemplateName*.zip  
  
     Örneğin, İngilizce (ABD) yerel destekleyen ContosoCustomAction.zip adlı bir öğe şablonu varsa, tam yolunu ItemTemplates\SharePoint\SharePoint14\1033\ContosoCustomAction.zip olabilir.  
  
3.  İçinde **Çözüm Gezgini**, şablon dosyası seçin (*YourTemplateName*.zip).  
  
4.  İçinde **özellikleri** penceresindeki ayarlayın **yapı eylemi** özelliğine **içerik**.  
  
5.  Source.extension.vsixmanifest dosya için kısayol menüsünü açın ve ardından **açık**.  
  
     Dosya Tasarımcısı'nda açılır.  
  
6.  İçinde **varlıklar** bölüm Düzenleyicisi, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
7.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.ItemTemplate** veya **Microsoft.VisualStudio.ProjectTemplate**.  
  
8.  İçinde **kaynak** listesinde, seçin **filesystem dosyada**.  
  
9. İçinde **yolu** alanında, derlemeye tam yolunu girin (örneğin, **ItemTemplates\SharePoint\SharePoint14\1033\ContosoCustomAction.zip**, veya **Gözat**bulun ve derleme Seç düğmesine ve ardından **Tamam** düğmesi.  
  
##### <a name="to-include-a-wizard-for-a-project-template-or-item-template"></a>Bir proje şablonu veya öğe şablonu için bir sihirbaz eklemek için  
  
1.  VSIX proje source.extension.vsixmanifest dosya için kısayol menüsünü açın ve ardından **açmak**.  
  
     Dosya Tasarımcısı'nda açılır.  
  
2.  İçinde **varlıklar** bölüm Düzenleyicisi, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
3.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.Assembly**.  
  
4.  İçinde **kaynak** listesinde, aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   VSIX proje olarak aynı çözüme bulunduğu bir projeden Sihirbazı derleme oluşturulduysa seçin **geçerli çözümdeki bir proje ile**. İçinde **proje** listesinde, projenin adını seçin.  
  
    -   Sihirbazı derleme dosyası projeniz olarak eklenirse seçin **filesystem dosyada**. İçinde **yolu** kullanın, derleme dosyasının tam yolunu girin veya alanı **Gözat** düğmesine bulun ve derleme seçin.  
  
5.  Seçin **Tamam** düğmesi.  
  
### <a name="related-walkthroughs"></a>İlgili izlenecek yollar  
 Aşağıdaki tabloda VSIX proje SharePoint araç uzantıları farklı türlerde dağıtmak için nasıl kullanılacağını gösteren talimatlara listeler.  
  
|Uzantı türü|İlgili izlenecek yollar|  
|--------------------|--------------------------|  
|Yalnızca uzantı derlemesi içeren uzantısı|[İzlenecek yol: Bir SharePoint Proje Öğesi Türünü Genişletme](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)<br /><br /> [İzlenecek Yol: SharePoint Proje Uzantısı Oluşturma](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)<br /><br /> [İzlenecek yol: Bir Sunucu Gezgini Uzantısında SharePoint İstemcisi Nesne Modelini Çağırma](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)|  
|SharePoint komutları içeren bir uzantısı|[İzlenecek Yol: SharePoint Projeleri için Özel bir Dağıtım Adımı Oluşturma](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)<br /><br /> [İzlenecek yol: Sunucu Gezginini Web Bölümlerini Görüntülemek Üzere Genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)<br /><br /> [İzlenecek yol: Proje Şablonu, Bölüm 2 ile bir Site Sütunu Proje Öğesi Oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)|  
|Visual Studio şablon içeren uzantısı|[İzlenecek yol: Öğe Şablonu, Bölüm 1 ile Özel bir Eylem Proje Öğesi Oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)<br /><br /> [İzlenecek yol: Proje Şablonu, Bölüm 1 ile bir Site Sütunu Proje Öğesi Oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)|  
|İçeren bir şablon Sihirbazı uzantısı|[İzlenecek yol: Öğe Şablonu, Bölüm 2 ile Özel bir Eylem Proje Öğesi Oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)<br /><br /> [İzlenecek yol: Proje Şablonu, Bölüm 2 ile bir Site Sütunu Proje Öğesi Oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)|  
  
## <a name="creating-vsix-packages-manually"></a>VSIX paket el ile oluşturma  
 SharePoint araçları Uzantınız için VSIX paket el ile oluşturmak istiyorsanız, aşağıdaki adımları gerçekleştirin:  
  
1.  Extension.vsixmanifest dosyasını ve [Content_Types] .xml dosyasını yeni bir klasör oluşturun. Daha fazla bilgi için bkz: [VSIX paketi anatomisi](/visualstudio/extensibility/anatomy-of-a-vsix-package).  
  
2.  Windows Gezgini'nde, iki XML dosyasını içeren klasörü sağ tıklatın, göndermek için tıklatın ve ardından sıkıştırılmış klasörü tıklatın. Sonuçta elde edilen .zip dosyasını Filename yükler ve paketinizi yeniden dağıtılabilir dosyasının adı olduğu Filename.vsix için yeniden adlandırın.  
  
3.  Uzantı derlemesi için VSIX paketi ekleyin. Dahili bir SharePoint komutu içeriyorsa, ayrıca VSIX paketi SharePoint komutu uygulayan derleme ekleyin.  
  
4.  Extension.vsixmanifest dosyasını değiştirin:  
  
    -   Ekleme bir `Microsoft.VisualStudio.MefComponent` öğesinin altında `Assets` öğesi olarak ayarlayın ve ardından VSIX paketi uzantınızı uygulayan derlemenin göreli yolu için yeni öğesinin değeri. Daha fazla bilgi için bkz: [MEFComponent öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
    -   Uzantınız için SharePoint sunucusu nesne modeline çağıran bir SharePoint komutu içeriyorsa, ekleme bir `Microsoft.VisualStudio.Assembly` öğesinin altında `Assets` öğesi. VSIX paketi SharePoint komutu uygulayan derlemenin göreli yolu için yeni öğenin değerini ayarlayın. Daha fazla bilgi için bkz: [varlık öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737).  
  
    -   Dahili bir proje şablonu veya öğe şablonu içeriyorsa, ekleme bir `ProjectTemplate` veya `ItemTemplate` öğesinin altında `Assets` öğesi. VSIX paketi şablonunda içeren klasöre göreli yolu için yeni öğenin değerini ayarlayın. Daha fazla bilgi için bkz: [ProjectTemplate öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/87add64c-9dcd-495f-8815-209dab182cb1) ve [ItemTemplate öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/1d489e54-c1c5-4f96-a510-6c2640867ff0).  
  
    -   Dahili bir proje şablonu veya öğe şablonu için özel bir sihirbaz içeriyorsa, ekleme bir `Assembly` öğesinin altında `Assets` öğesi. VSIX paketi derlemenin göreli yolu için yeni öğenin değerini ayarlayın ve ardından `AssemblyName` özniteliği (sürüm, kültür ve ortak anahtar belirteci dahil) tam derleme adı. Daha fazla bilgi için bkz: [Dependency öğesi (VSX şema)](http://msdn.microsoft.com/en-us/1f63f60a-98ad-48ec-8e44-4eba383d3e37).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir SharePoint araçları uzantısı için bir extension.vsixmanifest dosyasının içeriğini gösterir. Uzantı Contoso.ProjectExtension.dll adlı bir derlemede uygulanır. Contoso.ExtensionCommands.dll ve adlı bir klasörü altında bir öğe şablonu adlı bir SharePoint komutu derleme uzantısı içeren **öğe şablonları** VSIX paketi. Bu örnek, derlemeler her ikisi de VSIX paketi extension.vsixmanifest dosyasında ile aynı klasörde olduğunu varsayar.  
  
```  
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">  
  <Metadata>  
    <Identity Id="CustomActionProjectItem.Microsoft.b99efe4d-cef3-4afd-b9af-034ca0c52743" Version="1.0" Language="en-US" Publisher="Microsoft" />  
    <DisplayName>CustomActionProjectItem</DisplayName>  
    <Description>Empty VSIX Project.</Description>  
  </Metadata>  
  <Installation>  
    <InstallationTarget Id="Microsoft.VisualStudio.Pro" Version="11.0" />  
  </Installation>  
  <Dependencies>  
    <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" Version="4.5" />  
  </Dependencies>  
  <Assets>  
    <Asset Type="Microsoft.VisualStudio.ItemTemplate" Path="ItemTemplates" />  
    <Asset Type="Microsoft.VisualStudio.MefComponent" Path="ProjectItemDefinition.dll" />  
  </Assets>  
</PackageManifest>  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Visual Studio'da SharePoint Araçları için Hata Ayıklama Uzantıları](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  