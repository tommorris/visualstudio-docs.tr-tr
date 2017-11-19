---
title: "İzlenecek yol: öğe şablonu ile bir özel eylem proje öğesi oluşturma, bölüm 1 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, creating custom templates
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
ms.assetid: 41ed9c1c-4239-4d80-934b-975fde744288
caps.latest.revision: "152"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ddab05340b898a1a9a1868c7e537e6b53cc013b4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1"></a>İzlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma
  Visual Studio'da SharePoint Proje sistem öğesi türleri kendi projesi oluşturarak genişletebilirsiniz. Bu kılavuzda, bir SharePoint sitesinde özel bir eylem oluşturmak için bir SharePoint projesine eklenen bir proje öğesi oluşturur. Özel eylem menü öğesine ekler **Site eylemleri** SharePoint sitesinin menüsü.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Yeni bir SharePoint proje öğesi özel bir eylemin türünü tanımlayan bir Visual Studio uzantısı oluşturma. Yeni proje öğesi türünü, birkaç özel özellikleri uygulayan:  
  
    -   Visual Studio'da özel eylemi için bir tasarımcı görüntüleme gibi proje öğesi ile ilgili ek görevler için bir başlangıç noktası olarak hizmet veren bir kısayol menüsü.  
  
    -   Bir geliştirici belirli özelliklerini proje öğesi ve onu içeren projeye değiştiğinde çalışan kod  
  
    -   Proje öğesi yanındaki görünür özel bir simgesi **Çözüm Gezgini**.  
  
-   Proje öğesi için bir Visual Studio öğe şablonu oluşturma.  
  
-   Proje öğesi şablonu ve uzantı derlemesi dağıtmak üzere Visual Studio Uzantısı (VSIX) paket oluşturma.  
  
-   Hata ayıklama ve test proje öğesi.  
  
 Tek başına bir kılavuz budur. Bu kılavuzu tamamladıktan sonra proje öğesi öğe şablonu için bir sihirbaz ekleyerek geliştirebilirsiniz. Daha fazla bilgi için bkz: [izlenecek yol: bir öğe şablonu, bölüm 2 ile özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md).  
  
> [!NOTE]  
>  Tamamlanan projeleri, kod ve bu kılavuz aşağıdaki konumdan diğer dosyalarını içeren bir örnek indirebilirsiniz: [http://go.microsoft.com/fwlink/?LinkId=191369](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Microsoft Windows, SharePoint ve Visual Studio sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Bu kılavuzda kullanılır **VSIX proje** Şablonu proje öğesi dağıtmak için VSIX paket oluşturmak için SDK. Daha fazla bilgi için bkz: [genişletme Visual Studio'da SharePoint Araçları](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Aşağıdaki kavramlar bilgisi yararlı, ancak gerekli değildir, izlenecek yolu tamamlamak için:  
  
-   Özel eylemler SharePoint. Daha fazla bilgi için bkz: [özel eylem](http://go.microsoft.com/fwlink/?LinkId=177800).  
  
-   Visual Studio öğe şablonları. Daha fazla bilgi için bkz: [oluşturma proje ve öğe şablonlarını](/visualstudio/ide/creating-project-and-item-templates).  
  
## <a name="creating-the-projects"></a>Proje oluşturma  
 Bu izlenecek yolu tamamlamak için üç projeleri oluşturmanız gerekir:  
  
-   Bir VSIX proje. Bu proje SharePoint proje öğesi dağıtmak için VSIX paketi oluşturur.  
  
-   Bir öğe şablonu projesi. Bu proje bir SharePoint projesine SharePoint proje öğesi eklemek için kullanılan bir öğe şablonu oluşturur.  
  
-   Bir sınıf kitaplığı proje. Bu proje SharePoint proje öğesi davranışını tanımlayan bir Visual Studio uzantısı uygular.  
  
 İzlenecek yol projeleri oluşturarak başlayın.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
3.  Listedeki en üstündeki **yeni proje** iletişim kutusunda, olduğundan emin olun **.NET Framework 4.5** seçilir.  
  
4.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **genişletilebilirlik** düğümü.  
  
    > [!NOTE]  
    >  **Genişletilebilirlik** düğümdür yalnızca Visual Studio SDK'sı yüklerseniz kullanılabilir. Daha fazla bilgi için bu konudaki Önkoşullar bölümüne bakın.  
  
5.  Seçin **VSIX proje** şablonu.  
  
6.  İçinde **adı** kutusuna **CustomActionProjectItem**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **CustomActionProjectItem** için proje **Çözüm Gezgini**.  
  
#### <a name="to-create-the-item-template-project"></a>Öğe şablonu projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  Listedeki en üstündeki **yeni proje** iletişim kutusunda, olduğundan emin olun **.NET Framework 4.5** seçilir.  
  
3.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **genişletilebilirlik** düğümü.  
  
4.  Proje şablonları listesinden seçip **C# öğe şablonu** veya **Visual Basic öğe şablonu** şablonu.  
  
5.  İçinde **adı** kutusuna **ItemTemplate**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **ItemTemplate** çözüme proje.  
  
#### <a name="to-create-the-extension-project"></a>Uzantı projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  Listedeki en üstündeki **yeni proje** iletişim kutusunda, olduğundan emin olun **.NET Framework 4.5** seçilir.  
  
3.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri seçin **Windows** düğümü ve ardından seçin **Sınıf Kitaplığı** proje şablonu.  
  
4.  İçinde **adı** kutusuna **ProjectItemDefinition**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **ProjectItemDefinition** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
5.  Class1 kod dosyasının projeden silin.  
  
## <a name="configuring-the-extension-project"></a>Uzantı projesi yapılandırma  
 SharePoint Proje öğe türüne tanımlamak için kod yazmadan önce ve uzantı projesi derleme başvurularını kod dosyaları eklemeniz gerekir.  
  
#### <a name="to-configure-the-project"></a>Projeyi yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ProjectItemDefinition** projesi, seçin **Ekle**, ardından **yeni öğe**.  
  
2.  Proje öğeleri listesinden seçip **kod dosyası**.  
  
3.  İçinde **adı** kutusunda, bir ad girin **özel** uygun olan dosya adı uzantısı ve ardından **Ekle** düğmesi.  
  
4.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ProjectItemDefinition** proje ve ardından **Başvuru Ekle**.  
  
5.  İçinde **başvuru Yöneticisi - ProjectItemDefinition** iletişim kutusunda, seçin **derlemeleri** düğümünü ve ardından **Framework** düğümü.  
  
6.  Her biri aşağıdaki derlemeler yanındaki onay kutusunu seçin:  
  
    -   System.ComponentModel.Composition  
  
    -   System.Windows.Forms  
  
7.  Seçin **uzantıları** düğümü Microsoft.VisualStudio.Sharepoint derlemenin yanındaki onay kutusunu seçin ve ardından **Tamam** düğmesi.  
  
## <a name="defining-the-new-sharepoint-project-item-type"></a>Yeni SharePoint proje öğesi türü tanımlama  
 Arabirimini uygulayan bir sınıf oluşturun <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> yeni proje öğesi türünü davranışını tanımlamak için arabirim. Yeni bir proje öğesi türünü tanımlamak istediğiniz zaman bu arabirimi uygular.  
  
#### <a name="to-define-the-new-sharepoint-project-item-type"></a>Yeni SharePoint proje öğesi türünü tanımlamak için  
  
1.  ProjectItemDefinition projesinde özel kod dosyasını açın.  
  
2.  Bu dosyasındaki kodu aşağıdaki kodla değiştirin.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#1](../sharepoint/codesnippet/CSharp/customactionprojectitem/projectitemtypedefinition/customaction.cs#1)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#1](../sharepoint/codesnippet/VisualBasic/customactionprojectitem/projectitemdefinition/customaction.vb#1)]  
  
## <a name="creating-an-icon-for-the-project-item-in-solution-explorer"></a>Çözüm Gezgini'nde proje öğesi için bir simge oluşturma  
 Özel bir SharePoint proje öğesi oluşturduğunuzda, görüntü (simge veya bit eşlem) proje öğesi ile ilişkilendirebilirsiniz. Bu görüntü proje öğesinin yanındaki görünür **Çözüm Gezgini**.  
  
 Aşağıdaki yordamda proje öğesi için bir simge oluşturmak ve simge uzantısı derlemede katıştırmak. Bu simge tarafından başvuruluyor <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemIconAttribute> , `CustomActionProjectItemTypeProvider` daha önce oluşturduğunuz sınıfı.  
  
#### <a name="to-create-a-custom-icon-for-the-project-item"></a>Proje öğesi için özel bir simge oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ProjectItemDefinition** seçin, proje **Ekle**ve ardından **yeni öğe...** .  
  
2.  Proje öğeleri listesinden seçip **simge dosyası** öğesi.  
  
    > [!NOTE]  
    >  Visual Basic projelerinde seçmeniz gerekir **genel** görüntülemek için düğümü **simge dosyası** öğesi.  
  
3.  İçinde **adı** kutusuna **CustomAction_SolutionExplorer.ico**ve ardından **Ekle** düğmesi.  
  
     Yeni simgesine açılır **görüntü Düzenleyicisi**.  
  
4.  Simge dosyası 16 x 16 sürümünü algılar ve simge dosyası kaydedin bir tasarım olacak biçimde düzenleyin.  
  
5.  İçinde **Çözüm Gezgini**, seçin **CustomAction_SolutionExplorer.ico**.  
  
6.  İçinde **özellikleri** penceresinde oku seçin **yapı eylemi** özelliği.  
  
7.  Görüntülenen listede seçin **katıştırılmış kaynak**.  
  
## <a name="checkpoint"></a>Denetim noktası  
 Bu noktada kılavuzda tüm proje öğesi artık projede kodudur. Hatasız derlendiğinden emin olun için projeyi oluşturun.  
  
#### <a name="to-build-your-project"></a>Projenizi yapılandırmak için  
  
1.  Kısayol menüsünü açın **ProjectItemDefinition** proje ve seçin **yapı**.  
  
## <a name="creating-a-visual-studio-item-template"></a>Visual Studio öğe şablonu oluşturma  
 Proje öğesi kullanmak diğer geliştiriciler etkinleştirmek için bir proje şablonu veya öğe şablonu oluşturmanız gerekir. Geliştiricilerin bu şablonları Visual Studio'da yeni proje oluşturma veya varolan bir projeye öğe ekleyerek, proje öğesi örneği oluşturmak için kullanın. Bu kılavuzda ItemTemplate proje proje öğesi yapılandırmak için kullanın.  
  
#### <a name="to-create-the-item-template"></a>Öğe şablonu oluşturmak için  
  
1.  Class1 kod dosyasının ItemTemplate projeden silin.  
  
2.  ItemTemplate projesinde ItemTemplate.vstemplate dosyasını açın.  
  
3.  Aşağıdaki XML ile dosyasının içeriğini değiştirin ve sonra dosyasını kaydedin ve kapatın.  
  
    > [!NOTE]  
    >  Visual C# öğesi için bir şablon XML'dir. Visual Basic öğe şablonu oluşturuyorsanız, değerini değiştirin `ProjectType` öğeyle `VisualBasic`.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
      <TemplateData>  
        <DefaultName>CustomAction</DefaultName>  
        <Name>Custom Action</Name>  
        <Description>SharePoint Custom Action by Contoso</Description>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>1000</SortOrder>  
        <Icon>ItemTemplate.ico</Icon>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
      <TemplateContent>  
        <ProjectItem ReplaceParameters="true" TargetFileName="$fileinputname$\Elements.xml">Elements.xml</ProjectItem>  
        <ProjectItem ReplaceParameters="true" TargetFileName="$fileinputname$\SharePointProjectItem.spdata">CustomAction.spdata</ProjectItem>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
     Bu dosya içeriğini ve öğe şablonu davranışını tanımlar. Bu dosya içeriği hakkında daha fazla bilgi için bkz: [Visual Studio şablon şeması başvurusu](/visualstudio/extensibility/visual-studio-template-schema-reference).  
  
4.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ItemTemplate** seçin, proje **Ekle**ve ardından **yeni öğe**.  
  
5.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **metin dosyası** şablonu.  
  
6.  İçinde **adı** kutusuna **CustomAction.spdata**ve ardından **Ekle** düğmesi.  
  
7.  Aşağıdaki XML CustomAction.spdata dosyasına ekleyin ve ardından dosyasını kaydedin ve kapatın.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ProjectItem Type="Contoso.CustomAction" DefaultFile="Elements.xml"   
     xmlns="http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel">  
      <Files>  
        <ProjectItemFile Source="Elements.xml" Target="$fileinputname$\" Type="ElementManifest" />  
      </Files>  
    </ProjectItem>  
    ```  
  
     Bu dosya proje öğesi tarafından bulunan dosyalar hakkında bilgi içerir. `Type` Özniteliği `ProjectItem` öğesi ayarlayın, geçirilir aynı dizeye <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute> proje öğesi açıklamasında ( `CustomActionProjectItemTypeProvider` bu kılavuzda daha önce oluşturduğunuz sınıfı). .Spdata dosyaları içeriği hakkında daha fazla bilgi için bkz: [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md).  
  
8.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ItemTemplate** seçin, proje **Ekle**ve ardından **yeni öğe**.  
  
9. İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **XML dosyası** şablonu.  
  
10. İçinde **adı** kutusuna **Elements.xml**ve ardından **Ekle** düğmesi.  
  
11. Aşağıdaki XML ile Elements.xml dosyasının içeriğini değiştirin ve ardından dosyasını kaydedin ve kapatın.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Elements Id="$guid8$" xmlns="http://schemas.microsoft.com/sharepoint/">  
      <CustomAction Id="Replace this with a GUID or some other unique string"  
                    GroupId="SiteActions"  
                    Location="Microsoft.SharePoint.StandardMenu"  
                    Sequence="1000"  
                    Title="Replace this with your title"  
                    Description="Replace this with your description" >  
        <UrlAction Url="~site/Lists/Tasks/AllItems.aspx"/>  
      </CustomAction>  
    </Elements>  
    ```  
  
     Bu dosya üzerinde bir menü öğesini oluşturan varsayılan özel bir eylemi tanımlar **Site eylemleri** SharePoint sitesinin menüsü. URL bir kullanıcı menü öğesi seçtiğinde, belirtilen `UrlAction` öğesi web tarayıcısında açar. Özel bir eylem tanımlamak için kullanabileceğiniz XML öğeleri hakkında daha fazla bilgi için bkz: [özel eylem tanımları](http://go.microsoft.com/fwlink/?LinkId=177801).  
  
12. İsteğe bağlı olarak, ItemTemplate.ico dosyasını açın ve tanıyabilmesi için bir tasarıma sahiptir şekilde değiştirin. Bu simge proje öğesinin yanındaki görüntüler **Yeni Öğe Ekle** iletişim kutusu.  
  
13. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ItemTemplate** proje ve ardından **projeyi**.  
  
14. Kısayol menüsünü açın **ItemTemplate** yeniden proje ve ardından **Düzenle ItemTemplate.csproj** veya **Düzenle ItemTemplate.vbproj**.  
  
15. Aşağıdaki bulun `VSTemplate` proje öğesi.  
  
    ```  
    <VSTemplate Include="ItemTemplate.vstemplate">  
    ```  
  
16. Bunun yerine `VSTemplate` aşağıdaki XML ve ardından Kaydet ve Kapat dosya öğesiyle.  
  
    ```  
    <VSTemplate Include="ItemTemplate.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` Öğesi ek klasörler altında madde şablonu oluşturulduğu projeyi derlerken yolu belirtir. Burada belirtilen klasörleri yalnızca Müşteriler açtığınızda öğe şablonu kullanılabilir olacağından emin olmak **Yeni Öğe Ekle** iletişim kutusunda, genişletin **SharePoint** düğümünü ve ardından **2010**  düğüm.  
  
17. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ItemTemplate** proje ve ardından **projeyi yeniden yükle**.  
  
## <a name="creating-a-vsix-package-to-deploy-the-project-item"></a>Proje öğesi dağıtmak için VSIX paket oluşturma  
 Uzantıyı dağıtmak için VSIX paketi oluşturmak için çözümünüz VSIX proje kullanın. İlk olarak VSIX paketi VSIX projeye dahil source.extension.vsixmanifest dosyasını değiştirerek yapılandırın. Çözümü derledikten sonra VSIX paketi oluşturun.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Yapılandırmak ve VSIX paketi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **source.extension.vsixmanifest** dosya CustomActionProjectItem projesinde ve ardından **açmak**.  
  
     Visual Studio bildirim düzenleyicisinde dosyasını açar. Source.extension.vsixmanifest dosyanın tüm VSIX paketi gerektirir extension.vsixmanifest dosya temelini oluşturur. Bu dosya hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  İçinde **ürün adı** kutusuna **özel eylem proje öğesi**.  
  
3.  İçinde **Yazar** kutusuna **Contoso**.  
  
4.  İçinde **açıklama** kutusuna **özel bir eylemi temsil eden bir SharePoint proje öğesi**.  
  
5.  Üzerinde **varlıklar** sekmesinde, seçin **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
6.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.ItemTemplate**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `ItemTemplate` extension.vsixmanifest dosyasındaki öğesi. Bu öğe alt proje öğesi şablonu içeren VSIX paketi klasöründe tanımlar. Daha fazla bilgi için bkz: [ItemTemplate öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/1d489e54-c1c5-4f96-a510-6c2640867ff0).  
  
7.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
8.  İçinde **proje** listesinde, seçin **ItemTemplate**ve ardından **Tamam** düğmesi.  
  
9. İçinde **varlıklar** sekmesinde, seçin **yeni** yeniden düğmesine tıklayın.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
10. İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `MefComponent` extension.vsixmanifest dosyasındaki öğesi. Bu öğe VSIX paketi bir uzantı bütünleştirilmiş kodun adını belirtir. Daha fazla bilgi için bkz: [MEFComponent öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
11. İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
12. İçinde **proje** listesinde, seçin **ProjectItemDefinition**.  
  
13. Seçin **Tamam** düğmesi.  
  
14. Menü çubuğunda seçin **yapı**, **yapı çözümü**ve projeyi hatasız derlendiğinden emin olun.  
  
15. CustomActionProjectItem projenin yapı çıktı klasörüne CustomActionProjectItem.vsix dosya içerdiğinden emin olun.  
  
     Varsayılan olarak, yapı çıktı klasördür... CustomActionProjectItem projeyi içeren klasörü altındaki \bin\Debug klasörünü.  
  
## <a name="testing-the-project-item"></a>Proje öğesi test etme  
 Şimdi proje öğesi test etmek hazırsınız. İlk olarak, Visual Studio'nun deneysel örneği CustomActionProjectItem çözümde hata ayıklamayı Başlat. Ardından, test **özel eylem** Visual Studio'nun deneysel örneği SharePoint projede Proje öğesi. Son olarak, yapı ve özel eylemin beklendiği gibi çalıştığını doğrulamak için SharePoint Proje çalıştırın.  
  
#### <a name="to-start-debugging-the-solution"></a>Çözüm hata ayıklamayı başlatmak için  
  
1.  Yönetici kimlik bilgileriyle Visual Studio'yu yeniden başlatın ve ardından CustomActionProjectItem çözümü açın.  
  
2.  Özel kod dosyasını açın ve daha sonra bir kesme noktası kod ilk satırı ekleyin `InitializeType` yöntemi.  
  
3.  Seçin **F5** hata ayıklamayı başlatmak için anahtar.  
  
     Visual Studio %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\Custom eylem proje Item\1.0 uzantıyı yükleyen ve Visual Studio Deneysel bir örneğini başlatır. Proje öğesi Visual Studio'nun bu örneği test edeceksiniz.  
  
#### <a name="to-test-the-project-item-in-visual-studio"></a>Proje öğesi Visual Studio'da Test etmek için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **dosya**, **yeni**, **proje**.  
  
2.  Genişletme **Visual C#** veya **Visual Basic** (öğesi şablonunuzu destekleyen dili bağlı olarak), genişletin **SharePoint**ve ardından **2010**  düğüm.  
  
3.  Proje şablonları listesinden seçip **SharePoint 2010 proje**.  
  
4.  İçinde **adı** kutusuna **CustomActionTest**ve ardından **Tamam** düğmesi.  
  
5.  İçinde **SharePoint Özelleştirme Sihirbazı'nı**hata ayıklama için kullanmak istediğiniz sitenin URL'sini girin ve ardından **son** düğmesi.  
  
6.  İçinde **Çözüm Gezgini**, proje düğümüne için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni öğe**.  
  
7.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **2010** düğümü altında **SharePoint** düğümü.  
  
     Doğrulayın **özel eylem** öğesi proje öğeleri listede görünür.  
  
8.  Seçin **özel eylem** öğesini ve ardından **Ekle** düğmesi.  
  
     Visual Studio adlı bir öğe ekler **CustomAction1** proje ve Elements.xml dosya Düzenleyicisi'nde açar.  
  
9. Visual Studio'nun diğer örnek kodda, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `InitializeType` yöntemi.  
  
10. Seçin **F5** projede hataları ayıklamak devam etmek için anahtarı.  
  
11. Visual Studio deneysel örneğinde içinde **Çözüm Gezgini**, kısayol menüsünü açın **CustomAction1** düğümünü ve ardından **görünüm özel eylem Tasarımcısı**.  
  
12. Bir ileti kutusu görünür ve ardından doğrulamak **Tamam** düğmesi.  
  
     Özel eylem için bir tasarımcı görüntüleme gibi geliştiriciler için ek seçenekler veya komutlar sağlamak için bu kısayol menüsünü kullanabilirsiniz.  
  
13. Menü çubuğunda seçin **Görünüm**, **çıkış**.  
  
     **Çıkış** penceresi açılır.  
  
14. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **CustomAction1** öğesi ve kendi adına değiştirme **MyCustomAction**.  
  
     İçinde **çıkış** penceresi, bir onay iletisi görüntülenir. Bu ileti tarafından yazılan <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemNameChanged> tanımlanan olay işleyicisi `CustomActionProjectItemTypeProvider` sınıfı. Bu olay ve geliştirici proje öğesi değiştirdiğinde özel davranışı uygulamak için diğer proje öğesi olayları işleyebilir.  
  
#### <a name="to-test-the-custom-action-in-sharepoint"></a>Özel eylem SharePoint'te test etmek için  
  
1.  Visual Studio deneysel örneğinde bir alt Elements.xml dosyayı açma **MyCustomAction** proje öğesi.  
  
2.  Elements.xml dosyasında aşağıdaki değişiklikleri yapın ve ardından dosyayı kaydedin:  
  
    -   İçinde `CustomAction` öğe, ayarladığınız `Id` aşağıdaki örnekte gösterildiği gibi bir GUID veya diğer bir benzersiz dize özniteliği:  
  
        ```  
        Id="cd85f6a7-af2e-44ab-885a-0c795b52121a"  
        ```  
  
    -   İçinde `CustomAction` öğe, ayarladığınız `Title` özniteliği aşağıdaki örnekte gösterildiği gibi:  
  
        ```  
        Title="SharePoint Developer Center"  
        ```  
  
    -   İçinde `CustomAction` öğe, ayarladığınız `Description` özniteliği aşağıdaki örnekte gösterildiği gibi:  
  
        ```  
        Description="Opens the SharePoint Developer Center Web site."  
        ```  
  
    -   İçinde `UrlAction` öğe, ayarladığınız `Url` özniteliği aşağıdaki örnekte gösterildiği gibi:  
  
        ```  
        Url="http://msdn.microsoft.com/sharepoint/default.aspx"  
        ```  
  
3.  F5 tuşuna seçin.  
  
     Özel eylem paketlenir ve belirtilen SharePoint sitesi dağıtılan **Site URL'si** projesinin özelliği. Web tarayıcısı bu sitenin varsayılan sayfasını açar.  
  
    > [!NOTE]  
    >  Varsa **komut dosyası hata ayıklama devre dışı** seçin iletişim kutusu görüntülenirse, **Evet** projede hataları ayıklamak devam düğmesine.  
  
4.  Üzerinde **Site eylemleri** menüsünde seçin **SharePoint Geliştirici Merkezi**, tarayıcı Web sitesi http://msdn.microsoft.com/sharepoint/default.aspx açıldığını doğrulayın ve web tarayıcısı kapatın.  
  
## <a name="cleaning-up-the-development-computer"></a>Geliştirme bilgisayarı temizleme  
 Proje öğesi testi tamamladıktan sonra proje öğesi şablonu Visual Studio Deneysel örnekten kaldırın.  
  
#### <a name="to-clean-up-the-development-computer"></a>Geliştirme bilgisayarı temizlemek için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantıları listesinden seçip **özel eylem proje öğesi**ve ardından **kaldırma** düğmesi.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** düğmesi uzantıyı kaldırmak istediğinizi onaylayın.  
  
4.  Seçin **şimdi yeniden Başlat** kaldırma işleminin tamamlanması için düğmesi.  
  
5.  Visual Studio'nun deneysel örneği ve CustomActionProjectItem çözüm açıksa örneği kapatın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuzu tamamladıktan sonra bir sihirbaz öğe şablonu ekleyebilirsiniz. Bir kullanıcı bir SharePoint projesine bir özel eylem proje öğesi eklediğinde, sihirbaz eylem (örneğin, konumunu ve eylem seçildiğinde gitmek için URL'sini) hakkında bilgi toplar ve bu bilgileri yeni proje öğesi Elements.xml dosyasına ekler. Daha fazla bilgi için bkz: [izlenecek yol: bir öğe şablonu, bölüm 2 ile özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: bir öğe şablonu, bölüm 2 ile özel bir eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [Özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint Proje öğeleri için öğe şablonları ve proje şablonları oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md)   
 [Visual Studio Şablon Şeması Başvurusu](/visualstudio/extensibility/visual-studio-template-schema-reference)   
 [Simgeler için görüntü Düzenleyicisi](/cpp/windows/image-editor-for-icons)   
 [Simge veya başka görüntü &#40; görüntü Düzenleyicisi simgeler &#41;oluşturma;](/cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  