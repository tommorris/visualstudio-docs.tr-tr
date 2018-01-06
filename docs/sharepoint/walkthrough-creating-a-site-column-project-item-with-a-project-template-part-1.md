---
title: "İzlenecek yol: Proje şablonu ile bir Site sütunu proje öğesi oluşturma, bölüm 1 | Microsoft Docs"
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
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint projects, creating custom templates
- SharePoint development in Visual Studio, defining new project item types
ms.assetid: b53d48d7-cbf2-45c2-9537-06a6819be397
caps.latest.revision: "60"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 05a0f2a997791564a8358287ff1d632c3ff7bffe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1"></a>İzlenecek yol: Proje Şablonu, Bölüm 1 ile bir Site Sütunu Proje Öğesi Oluşturma
  SharePoint projeleri için bir veya daha fazla SharePoint Proje öğeleri kapsayıcılardır. Visual Studio'da SharePoint Proje sistem kendi SharePoint proje öğesi türleri oluşturarak ve bunları bir proje şablonu ile ilişkilendirme genişletebilirsiniz. Bu kılavuzda, bir site sütunu oluşturmak için bir proje öğesi türü tanımlayacaksınız ve sonra bir site sütunu proje öğesi içeren yeni bir proje oluşturmak için kullanılan bir proje şablonu oluşturur.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Yeni bir site sütunu için SharePoint proje öğesi türünü tanımlayan bir Visual Studio uzantısı oluşturma. Proje öğesi türü görünür basit bir özel özellik içerir **özellikleri** penceresi.  
  
-   Oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] proje öğesi için proje şablonu.  
  
-   Derleme bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] proje şablonu ve uzantı derlemesi dağıtmak için uzantı (VSIX) paketi.  
  
-   Hata ayıklama ve test proje öğesi.  
  
 Tek başına bir kılavuz budur. Bu kılavuzu tamamladıktan sonra proje şablonu için bir sihirbaz ekleyerek proje öğesi geliştirebilirsiniz. Daha fazla bilgi için bkz: [izlenecek yol: bir proje şablonu, bölüm 2 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
> [!NOTE]  
>  Tamamlanan projeleri, kod ve bu kılavuz aşağıdaki konumdan diğer dosyalarını içeren bir örnek indirebilirsiniz: [http://go.microsoft.com/fwlink/?LinkId=191369](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Desteklenen Microsoft Windows SharePoint sürümleri ve [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Bu kılavuzda kullanılır **VSIX proje** Şablonu proje öğesi dağıtmak için VSIX paket oluşturmak için SDK. Daha fazla bilgi için bkz: [genişletme Visual Studio'da SharePoint Araçları](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Bilgi aşağıdaki kavram yararlı, ancak gerekli değildir, izlenecek yolu tamamlamak için:  
  
-   SharePoint site sütunları. Daha fazla bilgi için bkz: [sütunları](http://go.microsoft.com/fwlink/?LinkId=183547).  
  
-   Visual Studio Proje şablonları. Daha fazla bilgi için bkz: [oluşturma proje ve öğe şablonlarını](/visualstudio/ide/creating-project-and-item-templates).  
  
## <a name="creating-the-projects"></a>Proje oluşturma  
 Bu izlenecek yolu tamamlamak için üç projeleri oluşturmanız gerekir:  
  
-   Bir VSIX proje. Bu proje site sütunu proje öğesi ve proje şablonu dağıtmak için VSIX paket oluşturur.  
  
-   Bir proje şablonu projesi. Bu proje site sütunu proje öğesi içeren yeni bir SharePoint projesi oluşturmak için kullanılan bir proje şablonu oluşturur.  
  
-   Bir sınıf kitaplığı proje. Site sütunu proje öğesi davranışını tanımlayan bir Visual Studio uzantısı uygulayan bu proje.  
  
 İzlenecek yol projeleri oluşturarak başlayın.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
3.  Üstündeki **yeni proje** iletişim kutusunda, olduğundan emin olun **.NET Framework 4.5** .NET Framework sürümleri listesinde seçilir.  
  
4.  Genişletme **Visual Basic** veya **Visual C#** düğümleri ve ardından **genişletilebilirlik** düğümü.  
  
    > [!NOTE]  
    >  **Genişletilebilirlik** düğümdür yalnızca Visual Studio SDK'sı yüklerseniz kullanılabilir. Daha fazla bilgi için bu konudaki Önkoşullar bölümüne bakın.  
  
5.  Proje şablonları listesinden seçip **VSIX proje**.  
  
6.  İçinde **adı** kutusuna **SiteColumnProjectItem**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **SiteColumnProjectItem** için proje **Çözüm Gezgini**.  
  
#### <a name="to-create-the-project-template-project"></a>Proje şablonu projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  Üstündeki **yeni proje** iletişim kutusunda, olduğundan emin olun **.NET Framework 4.5** .NET Framework sürümleri listesinde seçilir.  
  
3.  Genişletin **Visual C#** veya **Visual Basic** düğümünü ve ardından **genişletilebilirlik** düğümü.  
  
4.  Proje şablonları listesinden seçip **C# proje şablonu** veya **Visual Basic proje şablonu** şablonu.  
  
5.  İçinde **adı** kutusuna **SiteColumnProjectTemplate**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **SiteColumnProjectTemplate** çözüme proje.  
  
6.  Class1 kod dosyasının projeden silin.  
  
7.  Ayrıca Visual Basic projesinde oluşturduysanız, projeden aşağıdaki dosyaları silin:  
  
    -   MyApplication.Designer.vb  
  
    -   MyApplication.myapp  
  
    -   Resources.Designer.vb  
  
    -   Resources.resx  
  
    -   Settings.Designer.vb  
  
    -   Settings.Settings  
  
#### <a name="to-create-the-extension-project"></a>Uzantı projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  Üstündeki **yeni proje** iletişim kutusunda, olduğundan emin olun **.NET Framework 4.5** .NET Framework sürümleri listesinde seçilir.  
  
3.  Genişletin **Visual C#** veya **Visual Basic** düğümleri seçin **Windows** düğümünü ve ardından **sınıf kitaplığı** şablonu.  
  
4.  İçinde **adı** kutusuna **ProjectItemTypeDefinition** ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **ProjectItemTypeDefinition** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
5.  Class1 kod dosyasının projeden silin.  
  
## <a name="configuring-the-extension-project"></a>Uzantı projesi yapılandırma  
 Uzantı projesi yapılandırmak için derleme başvurusu ve kod dosyaları ekleyin.  
  
#### <a name="to-configure-the-project"></a>Projeyi yapılandırmak için  
  
1.  Adlı bir kod dosyası ProjectItemTypeDefinition projesinde ekleyin **SiteColumnProjectItemTypeProvider**.  
  
2.  Menü çubuğunda seçin **proje**, **Başvuru Ekle**.  
  
3.  İçinde **başvuru Yöneticisi - ProjectItemTypeDefinition** iletişim kutusunda, genişletin **derlemeler** düğümü seçin **Framework** düğümünü ve ardından seçin System.ComponentModel.Composition onay kutusunu seçin.  
  
4.  Seçin **uzantıları** düğümü Microsoft.VisualStudio.SharePoint derlemenin yanındaki onay kutusunu seçin ve ardından **Tamam** düğmesi.  
  
## <a name="defining-the-new-sharepoint-project-item-type"></a>Yeni SharePoint proje öğesi türü tanımlama  
 Arabirimini uygulayan bir sınıf oluşturun <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> yeni proje öğesi türünü davranışını tanımlamak için arabirim. Yeni bir proje öğesi türünü tanımlamak istediğiniz zaman bu arabirimi uygular.  
  
#### <a name="to-define-the-new-sharepoint-project-item-type"></a>Yeni SharePoint proje öğesi türünü tanımlamak için  
  
1.  İçinde **SiteColumnProjectItemTypeProvider** kod dosyası, varsayılan kodu aşağıdaki kodla değiştirin ve ardından dosyayı kaydedin.  
  
     [!code-csharp[SPExtensibility.ProjectItem.SiteColumn#1](../sharepoint/codesnippet/CSharp/sitecolumnprojectitem/projectitemtypedefinition/sitecolumnprojectitemtypeprovider.cs#1)]
     [!code-vb[SPExtensibility.ProjectItem.SiteColumn#1](../sharepoint/codesnippet/VisualBasic/sitecolumnprojectitem/projectitemtypedefinition/sitecolumnprojectitemtypeprovider.vb#1)]  
  
## <a name="creating-a-visual-studio-project-template"></a>Visual Studio Proje şablonu oluşturma  
 Bir proje şablonu oluşturarak, site sütunu proje öğelerini içeren SharePoint proje oluşturmak diğer geliştiriciler etkinleştirin. Bir SharePoint Proje şablonu .csproj veya .vbproj .vstemplate dosyaları ve SharePoint projelerine belirli dosyaları gibi Visual Studio'daki tüm projeleri için gerekli dosyaları içerir. Daha fazla bilgi için bkz: [öğe şablonları oluşturma ve SharePoint Proje öğeleri için proje şablonları](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Bu yordamda, SharePoint projelerine belirli dosyaları oluşturmak için boş bir SharePoint projesi oluşturun. Böylece bu projeden oluşturulan şablondaki dahil edildiklerini SiteColumnProjectTemplate projeye bu dosyaları ekleyin. Proje şablonu göründüğü belirtmek için SiteColumnProjectTemplate proje dosyası yapılandırmanız da **yeni proje** iletişim kutusu.  
  
#### <a name="to-create-the-files-for-the-project-template"></a>Proje şablonu dosyalarını oluşturmak için  
  
1.  İkinci bir örneğini Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] yönetici kimlik bilgilerine sahip.  
  
2.  Adlı bir SharePoint 2010 projesi oluşturma **BaseSharePointProject**.  
  
    > [!IMPORTANT]  
    >  İçinde **SharePoint Özelleştirme Sihirbazı'nı**, seçmeyin **Grup çözümü olarak dağıtma** seçenek düğmesi.  
  
3.  Boş öğe öğe projeye ekleyin ve ardından öğe adı **alan1**.  
  
4.  Projeyi kaydedin ve ardından ikinci bir örneğini kapatın [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
5.  Örneğindeki [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SiteColumnProjectItem çözüm açık olarak sahip **Çözüm Gezgini**, kısayol menüsünü açın **SiteColumnProjectTemplate** proje düğümünü, seçin **Ekleme**ve ardından **varolan öğeyi**.  
  
6.  İçinde **varolan öğeyi Ekle** iletişim kutusunda, dosya uzantıları listesini açın ve ardından **tüm dosyalar (\*.\*)** .  
  
7.  BaseSharePointProject projeyi içeren dizinde key.snk dosyasını seçin ve ardından **Ekle** düğmesi.  
  
    > [!NOTE]  
    >  Bu kılavuzda, oluşturduğunuz proje şablonu aynı key.snk dosyasını şablonu kullanılarak oluşturulan her proje imzalamak için kullanır. Her bir proje örneği için farklı key.snk dosyasını oluşturmak için bu örnek genişletmek öğrenmek için bkz: [izlenecek yol: bir proje şablonu, bölüm 2 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
8.  Aşağıdaki dosyalar BaseSharePointProject dizininde belirtilen klasörlerdeki eklemek için 5-8 adımları yineleyin:  
  
    -   \Field1\Elements.XML  
  
    -   \Field1\SharePointProjectItem.spdata  
  
    -   \Features\Feature1\Feature1.Feature  
  
    -   \Features\Feature1\Feature1.Template.XML  
  
    -   \Package\Package.Package  
  
    -   \Package\Package.Template.XML  
  
     Bu dosyaları doğrudan SiteColumnProjectTemplate projeye ekleyin; Proje alan1, özellikleri veya paket klasörlerdeki yeniden yok. Bu dosyalar hakkında daha fazla bilgi için bkz: [öğe şablonları oluşturma ve SharePoint Proje öğeleri için proje şablonları](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
#### <a name="to-configure-how-developers-discover-the-project-template-in-the-new-project-dialog-box"></a>Geliştiricilerin yeni proje iletişim kutusunda proje şablonu nasıl Bul yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SiteColumnProjectTemplate** proje düğümünü ve ardından **projeyi**. Değişiklikleri kaydetmek için tüm dosyaları istenirse seçin **Evet** düğmesi.  
  
2.  Kısayol menüsünü açın **SiteColumnProjectTemplate** düğümü yeniden ve ardından **Düzenle SiteColumnProjectTemplate.csproj** veya **SiteColumnProjectTemplate.vbprojDüzenle**.  
  
3.  Proje dosyasında aşağıdaki bulun `VSTemplate` öğesi.  
  
    ```  
    <VSTemplate Include="SiteColumnProjectTemplate.vstemplate">  
    ```  
  
4.  Bu öğe aşağıdaki XML ile değiştirin.  
  
    ```  
    <VSTemplate Include="SiteColumnProjectTemplate.vstemplate">  
      <OutputSubPath>SharePoint\SharePoint14</OutputSubPath>  
    </VSTemplate>  
    ```  
  
     `OutputSubPath` Öğesi ek klasörler altında proje şablonu oluşturulduğu projeyi derlerken yolu belirtir. Burada belirtilen klasörleri yalnızca Müşteriler açtığınızda proje şablonu kullanılabilir olacağından emin olmak **yeni proje** iletişim kutusunda, genişletin **SharePoint** düğümünü ve ardından **2010**  düğüm.  
  
5.  Dosyayı kaydedin ve kapatın.  
  
6.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SiteColumnProjectTemplate** proje ve ardından **projeyi yeniden yükle**.  
  
## <a name="editing-the-project-template-files"></a>Proje şablonu dosyalarını düzenleme  
 SiteColumnProjectTemplate projede Proje şablonu davranışını tanımlamak için aşağıdaki dosyaları düzenleyin:  
  
-   AssemblyInfo.cs veya AssemblyInfo.vb  
  
-   Elements.XML  
  
-   SharePointProjectItem.spdata  
  
-   Feature1.Feature  
  
-   Package.Package  
  
-   SiteColumnProjectTemplate.vstemplate  
  
-   ProjectTemplate.csproj veya ProjectTemplate.vbproj  
  
 Aşağıdaki yordamlarda, bu dosyaların bazıları için değiştirilebilir parametreler ekleyeceksiniz. Bir parametredir başlatır ve dolar işareti ($) karakteri ile biten bir belirteçtir. Bir kullanıcı bir proje oluşturmak için bu proje şablonu kullandığında, Visual Studio bu parametreler Yeni projedeki belirli değerlerle otomatik olarak değiştirir. Daha fazla bilgi için bkz: [değiştirilebilir parametreler](../sharepoint/replaceable-parameters.md).  
  
#### <a name="to-edit-the-assemblyinfocs-or-assemblyinfovb-file"></a>AssemblyInfo.cs veya AssemblyInfo.vb dosyayı düzenlemek için  
  
1.  SiteColumnProjectTemplate proje AssemblyInfo.cs veya AssemblyInfo.vb dosyasını açın ve ardından bunu en üstüne aşağıdaki deyim ekleyin:  
  
    ```vb  
    Imports System.Security  
    ```  
  
    ```csharp  
    using System.Security;  
    ```  
  
     Zaman **Korumalı çözüm** bir SharePoint proje özelliği ayarlanmış **True**, Visual Studio ekler <xref:System.Security.AllowPartiallyTrustedCallersAttribute> AssemblyInfo kod dosyası için. Ancak, proje şablonu AssemblyInfo kod dosyasını içe aktarmaz <xref:System.Security> varsayılan ad alanı. Bu eklemelisiniz **kullanarak** veya **içeri aktarmalar** önlemek için deyimi derleme hataları.  
  
2.  Dosyayı kaydedin ve kapatın.  
  
#### <a name="to-edit-the-elementsxml-file"></a>Elements.xml dosyayı düzenlemek için  
  
1.  SiteColumnProjectTemplate projesinde Elements.xml dosyasının içeriğini aşağıdaki XML ile değiştirin.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
      <Field ID="{$guid5$}"   
          Name="$safeprojectname$"   
          DisplayName="$projectname$"   
          Type="Text"   
          Group="Custom Columns">  
      </Field>  
    </Elements>  
    ```  
  
     Yeni XML ekler bir `Field` site sütunu, temel türünü ve site sütunu galerisinde listelemek üzere grubunun adını tanımlar öğesi. Bu dosya içeriği hakkında daha fazla bilgi için bkz: [alan Tanım Şeması](http://go.microsoft.com/fwlink/?LinkId=184290).  
  
2.  Dosyayı kaydedin ve kapatın.  
  
#### <a name="to-edit-the-sharepointprojectitemspdata-file"></a>SharePointProjectItem.spdata dosyayı düzenlemek için  
  
1.  SiteColumnProjectTemplate projesinde SharePointProjectItem.spdata dosyasının içeriğini aşağıdaki XML ile değiştirin.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ProjectItem Type="Contoso.SiteColumn" DefaultFile="Elements.xml"   
                 xmlns="http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel">  
      <Files>  
        <ProjectItemFile Source="Elements.xml" Target="$safeprojectname$\" Type="ElementManifest" />  
      </Files>   
    </ProjectItem>  
    ```  
  
     Yeni XML dosyasına aşağıdaki değişiklikleri yapar:  
  
    -   Değişiklikleri `Type` özniteliği `ProjectItem` geçirilir aynı dize öğesine <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute> proje öğesi açıklamasında ( `SiteColumnProjectItemTypeProvider` bu kılavuzda daha önce oluşturduğunuz sınıfı).  
  
    -   Kaldırır `SupportedTrustLevels` ve `SupportedDeploymentScopes` özniteliklerini `ProjectItem` öğesi. Güven düzeyleri ve dağıtım kapsamları belirtilen gerektiğinden bu öznitelik değerlerini gereksizdir `SiteColumnProjectItemTypeProvider` ProjectItemTypeDefinition projesinde sınıfı.  
  
     .Spdata dosyaları içeriği hakkında daha fazla bilgi için bkz: [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md).  
  
2.  Dosyayı kaydedin ve kapatın.  
  
#### <a name="to-edit-the-feature1feature-file"></a>Feature1.feature dosyayı düzenlemek için  
  
1.  SiteColumnProjectTemplate projesinde Feature1.feature dosyasının içeriğini aşağıdaki XML ile değiştirin.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <feature xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0" Id="$guid4$" featureId="$guid4$"   
             imageUrl="" solutionId="00000000-0000-0000-0000-000000000000" title="Site Column Feature1" version=""  
             deploymentPath="$SharePoint.Project.FileNameWithoutExtension$_$SharePoint.Feature.FileNameWithoutExtension$"  
             xmlns="http://schemas.microsoft.com/VisualStudio/2008/SharePointTools/FeatureModel">  
      <projectItems>  
        <projectItemReference itemId="$guid2$" />  
      </projectItems>  
    </feature>  
    ```  
  
     Yeni XML dosyasına aşağıdaki değişiklikleri yapar:  
  
    -   Değerlerini değiştirir `Id` ve `featureId` özniteliklerini `feature` öğesine `$guid4$`.  
  
    -   Değerlerini değiştirir `itemId` özniteliği `projectItemReference` öğesine `$guid2$`.  
  
     .Feature dosyaları hakkında daha fazla bilgi için bkz: [öğe şablonları oluşturma ve SharePoint Proje öğeleri için proje şablonları](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
2.  Dosyayı kaydedin ve kapatın.  
  
#### <a name="to-edit-the-packagepackage-file"></a>Package.package dosyayı düzenlemek için  
  
1.  SiteColumnProjectTemplate projesinde Package.package dosyasının içeriğini aşağıdaki XML ile değiştirin.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <package xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0"   
             Id="$guid3$" solutionId="$guid3$" resetWebServer="false" name="$safeprojectname$"   
             xmlns="http://schemas.microsoft.com/VisualStudio/2008/SharePointTools/PackageModel">  
      <features>  
        <featureReference itemId="$guid4$" />  
      </features>  
    </package>  
    ```  
  
     Yeni XML dosyasına aşağıdaki değişiklikleri yapar:  
  
    -   Değerlerini değiştirir `Id` ve `solutionId` özniteliklerini `package` öğesine `$guid3$`.  
  
    -   Değerlerini değiştirir `itemId` özniteliği `featureReference` öğesine `$guid4$`.  
  
     .Package dosyaları hakkında daha fazla bilgi için bkz: [öğe şablonları oluşturma ve SharePoint Proje öğeleri için proje şablonları](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
2.  Dosyayı kaydedin ve kapatın.  
  
#### <a name="to-edit-the-sitecolumnprojecttemplatevstemplate-file"></a>SiteColumnProjectTemplate.vstemplate dosyayı düzenlemek için  
  
1.  SiteColumnProjectTemplate projesinde SiteColumnProjectTemplate.vstemplate dosyasının içeriğini XML aşağıdaki bölümlerden biri ile değiştirin.  
  
    -   Visual C# proje şablonu oluşturuyorsanız, aşağıdaki XML kullanın.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Project">  
      <TemplateData>  
        <Name>Site Column</Name>  
        <Description>Creates a new site column in SharePoint</Description>  
        <FrameworkVersion>3.5</FrameworkVersion>  
        <ProjectType>CSharp</ProjectType>  
        <CreateNewFolder>true</CreateNewFolder>  
        <CreateInPlace>true</CreateInPlace>  
        <ProvideDefaultName>true</ProvideDefaultName>  
        <DefaultName>SiteColumn</DefaultName>  
        <LocationField>Enabled</LocationField>  
        <EnableLocationBrowseButton>true</EnableLocationBrowseButton>  
        <PromptForSaveOnCreation>true</PromptForSaveOnCreation>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <Icon>SiteColumnProjectTemplate.ico</Icon>  
        <SortOrder>1000</SortOrder>  
      </TemplateData>  
      <TemplateContent>  
        <Project TargetFileName="SharePointProject1.csproj" File="ProjectTemplate.csproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" TargetFileName="Properties\AssemblyInfo.cs">AssemblyInfo.cs</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.feature">Feature1.feature</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.Template.xml">Feature1.template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.package">Package.package</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.Template.xml">Package.Template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\SharePointProjectItem.spdata">SharePointProjectItem.spdata</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\Elements.xml" OpenInEditor="true">Elements.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
    -   Visual Basic proje şablonu oluşturuyorsanız, aşağıdaki XML kullanın.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Project">  
      <TemplateData>  
        <Name>Site Column</Name>  
        <Description>Creates a new site column in SharePoint</Description>  
        <FrameworkVersion>3.5</FrameworkVersion>  
        <ProjectType>VisualBasic</ProjectType>  
        <CreateNewFolder>true</CreateNewFolder>  
        <CreateInPlace>true</CreateInPlace>  
        <ProvideDefaultName>true</ProvideDefaultName>  
        <DefaultName>SiteColumn</DefaultName>  
        <LocationField>Enabled</LocationField>  
        <EnableLocationBrowseButton>true</EnableLocationBrowseButton>  
        <PromptForSaveOnCreation>true</PromptForSaveOnCreation>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <Icon>SiteColumnProjectTemplate.ico</Icon>  
        <SortOrder>1000</SortOrder>  
      </TemplateData>  
      <TemplateContent>  
        <Project TargetFileName="SharePointProject1.vbproj" File="ProjectTemplate.vbproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" TargetFileName="My Project\AssemblyInfo.vb">AssemblyInfo.vb</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.feature">Feature1.feature</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Features\Feature1\Feature1.Template.xml">Feature1.template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.package">Package.package</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Package\Package.Template.xml">Package.Template.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\SharePointProjectItem.spdata">SharePointProjectItem.spdata</ProjectItem>  
          <ProjectItem ReplaceParameters="true" TargetFileName="Field1\Elements.xml" OpenInEditor="true">Elements.xml</ProjectItem>  
          <ProjectItem ReplaceParameters="false" TargetFileName="key.snk">key.snk</ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
     Yeni XML dosyasına aşağıdaki değişiklikleri yapar:  
  
    -   Ayarlar `Name` değeri öğesine **Site sütunu**. (Bu ad görünür **yeni proje** iletişim kutusu).  
  
    -   Ekler `ProjectItem` her filethat için öğeleri her proje örnek dahil.  
  
    -   "Http://schemas.microsoft.com/developer/vstemplate/2005" ad alanı kullanır. Bu çözümdeki başka proje dosyalarına "http://schemas.microsoft.com/developer/msbuild/2003" ad alanını kullanın. Bu nedenle, XML Şeması uyarı iletilerini oluşturulur, ancak bu kılavuzda yoksayabilirsiniz.  
  
     .Vstemplate dosyaları içeriği hakkında daha fazla bilgi için bkz: [Visual Studio şablon şeması başvurusu](/visualstudio/extensibility/visual-studio-template-schema-reference).  
  
2.  Dosyayı kaydedin ve kapatın.  
  
#### <a name="to-edit-the-projecttemplatecsproj-or-projecttemplatevbproj-file"></a>ProjectTemplate.csproj veya ProjectTemplate.vbproj dosyayı düzenlemek için  
  
1.  SiteColumnProjectTemplate projesinde ProjectTemplate.csproj dosya veya ProjectTemplate.vbproj dosyanın içeriğini XML aşağıdaki bölümlerden biri ile değiştirin.  
  
    -   Visual C# proje şablonu oluşturuyorsanız, aşağıdaki XML kullanın.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <SchemaVersion>2.0</SchemaVersion>  
        <ProjectGuid>{$guid1$}</ProjectGuid>  
        <OutputType>Library</OutputType>  
        <AppDesignerFolder>Properties</AppDesignerFolder>  
        <RootNamespace>$safeprojectname$</RootNamespace>  
        <AssemblyName>$safeprojectname$</AssemblyName>  
        <TargetFrameworkVersion>v3.5</TargetFrameworkVersion>  
        <FileAlignment>512</FileAlignment>  
        <ProjectTypeGuids>{BB1F664B-9266-4fd6-B973-E1E44974B511};{14822709-B5A1-4724-98CA-57A101D1B079};{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}</ProjectTypeGuids>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineConstants>DEBUG;TRACE</DefineConstants>  
        <ErrorReport>prompt</ErrorReport>  
        <WarningLevel>4</WarningLevel>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">  
        <DebugType>pdbonly</DebugType>  
        <Optimize>true</Optimize>  
        <OutputPath>bin\Release\</OutputPath>  
        <DefineConstants>TRACE</DefineConstants>  
        <ErrorReport>prompt</ErrorReport>  
        <WarningLevel>4</WarningLevel>  
      </PropertyGroup>  
      <PropertyGroup>  
        <SignAssembly>true</SignAssembly>  
        <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="System" />  
        <Reference Include="System.Core" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Data.DataSetExtensions" />  
        <Reference Include="System.Web" />  
        <Reference Include="System.Xml" />  
        <Reference Include="System.Xml.Linq" />  
        <Reference Include="Microsoft.SharePoint" />  
        <Reference Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="Properties\AssemblyInfo.cs" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Field1\SharePointProjectItem.spdata">  
          <SharePointProjectItemId>{$guid2$}</SharePointProjectItemId>  
        </None>  
        <None Include="Field1\Elements.xml" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="key.snk" />  
        <None Include="Package\Package.package">  
          <PackageId>{$guid3$}</PackageId>  
        </None>  
        <None Include="Package\Package.Template.xml">  
          <DependentUpon>Package.package</DependentUpon>  
        </None>  
        <None Include="Features\Feature1\Feature1.feature">  
          <FeatureId>{$guid4$}</FeatureId>  
        </None>  
        <None Include="Features\Feature1\Feature1.Template.xml">  
          <DependentUpon>Feature1.feature</DependentUpon>  
        </None>  
      </ItemGroup>  
      <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />  
      <Import Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v10.0\SharePointTools\Microsoft.VisualStudio.SharePoint.targets" />  
    </Project>  
    ```  
  
    1.  Visual Basic proje şablonu oluşturuyorsanız, aşağıdaki XML kullanın.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <ProductVersion>  
        </ProductVersion>  
        <SchemaVersion>  
        </SchemaVersion>  
        <ProjectGuid>{$guid1$}</ProjectGuid>  
        <OutputType>Library</OutputType>  
        <RootNamespace>$safeprojectname$</RootNamespace>  
        <AssemblyName>$safeprojectname$</AssemblyName>  
        <TargetFrameworkVersion>v3.5</TargetFrameworkVersion>  
        <FileAlignment>512</FileAlignment>  
        <ProjectTypeGuids>{BB1F664B-9266-4fd6-B973-E1E44974B511};{D59BE175-2ED0-4C54-BE3D-CDAA9F3214C8};{F184B08F-C81C-45F6-A57F-5ABD9991F28F}</ProjectTypeGuids>  
        <OptionExplicit>On</OptionExplicit>  
        <OptionCompare>Binary</OptionCompare>  
        <OptionStrict>Off</OptionStrict>  
        <OptionInfer>On</OptionInfer>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <OutputPath>bin\Debug\</OutputPath>  
        <WarningLevel>4</WarningLevel>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">  
        <DebugType>pdbonly</DebugType>  
        <DefineDebug>false</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <Optimize>true</Optimize>  
        <OutputPath>bin\Release\</OutputPath>  
        <UseVSHostingProcess>false</UseVSHostingProcess>  
      </PropertyGroup>  
      <PropertyGroup>  
        <SignAssembly>true</SignAssembly>  
        <AssemblyOriginatorKeyFile>key.snk</AssemblyOriginatorKeyFile>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="System" />  
        <Reference Include="System.Core" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Data.DataSetExtensions" />  
        <Reference Include="System.Xml" />  
        <Reference Include="System.Xml.Linq" />  
        <Reference Include="Microsoft.SharePoint" />  
        <Reference Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Import Include="Microsoft.VisualBasic" />  
        <Import Include="System" />  
        <Import Include="System.Collections" />  
        <Import Include="System.Collections.Generic" />  
        <Import Include="System.Data" />  
        <Import Include="System.Diagnostics" />  
        <Import Include="System.Linq" />  
        <Import Include="System.Xml.Linq" />  
        <Import Include="Microsoft.SharePoint" />  
        <Import Include="Microsoft.SharePoint.Security" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="My Project\AssemblyInfo.vb" />  
      </ItemGroup>  
      <ItemGroup>  
        <AppDesigner Include="My Project\" />  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Features\Feature1\Feature1.feature">  
          <FeatureId>{$guid4$}</FeatureId>  
        </None>  
        <None Include="Field1\SharePointProjectItem.spdata">  
          <SharePointProjectItemId>{$guid2$}</SharePointProjectItemId>  
        </None>  
        <None Include="key.snk" />  
        <None Include="Package\Package.package">  
          <PackageId>{$guid3$}</PackageId>  
        </None>  
        <None Include="Package\Package.Template.xml">  
          <DependentUpon>Package.package</DependentUpon>  
        </None>  
      </ItemGroup>  
      <ItemGroup>  
        <None Include="Features\Feature1\Feature1.Template.xml">  
          <DependentUpon>Feature1.feature</DependentUpon>  
        </None>  
        <None Include="Field1\Elements.xml" />  
      </ItemGroup>  
      <Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />  
      <Import Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v10.0\SharePointTools\Microsoft.VisualStudio.SharePoint.targets" />  
    </Project>  
    ```  
  
     Yeni XML dosyasına aşağıdaki değişiklikleri yapar:  
  
    -   Kullanan `TargetFrameworkVersion` öğesi değil 4.5 .NET Framework 3.5 belirtin.  
  
    -   Ekler `SignAssembly` ve `AssemblyOriginatorKeyFile` proje çıktı imzalamak için öğeleri.  
  
    -   Ekler `Reference` derleme için öğeleri SharePoint projeleri kullanan başvuruyor.  
  
    -   Projedeki Elements.xml ve SharePointProjectItem.spdata gibi her varsayılan dosya için öğeleri ekler.  
  
2.  Dosyayı kaydedin ve kapatın.  
  
## <a name="creating-a-vsix-package-to-deploy-the-project-template"></a>Proje şablonu dağıtmak için VSIX paket oluşturma  
 Uzantıyı dağıtmak için VSIX projesinde kullanma **SiteColumnProjectItem** VSIX paketi oluşturmak için çözüm. İlk olarak VSIX paketi VSIX projeye dahil source.extension.vsixmanifest dosyasını değiştirerek yapılandırın. Çözümü derledikten sonra VSIX paketi oluşturun.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Yapılandırmak ve VSIX paketi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, **SiteColumnProjectItem** projesi, bildirim düzenleyicisinde source.extension.vsixmanifest dosyasını açın.  
  
     Source.extension.vsixmanifest dosyanın tüm VSIX paketi gerektirir extension.vsixmanifest dosya temelini oluşturur. Bu dosya hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  İçinde **ürün adı** kutusuna **Site sütunu**.  
  
3.  İçinde **Yazar** kutusuna **Contoso**.  
  
4.  İçinde **açıklama** kutusuna **site sütunları oluşturmak için bir SharePoint proje**.  
  
5.  Seçin **varlıklar** sekmesini ve ardından **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
6.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.ProjectTemplate**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `ProjectTemplate` extension.vsixmanifest dosyasındaki öğesi. Bu öğe alt proje şablonu içeren VSIX paketi klasöründe tanımlar. Daha fazla bilgi için bkz: [ProjectTemplate öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/87add64c-9dcd-495f-8815-209dab182cb1).  
  
7.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
8.  İçinde **proje** listesinde ve seçin **SiteColumnProjectTemplate**ve ardından **Tamam** düğmesi.  
  
9. Seçin **yeni** yeniden düğmesine tıklayın.  
  
     **Ekleme yeni varlık** iletişim kutusu açılır.  
  
10. İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `MefComponent` extension.vsixmanifest dosyasındaki öğesi. Bu öğe VSIX paketi bir uzantı bütünleştirilmiş kodun adını belirtir. Daha fazla bilgi için bkz: [MEFComponent öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
11. İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
12. İçinde **proje** listesinde, seçin **ProjectItemTypeDefinition**ve ardından **Tamam** düğmesi.  
  
13. Menü çubuğunda seçin **yapı**, **yapı çözümü**ve projeyi hatasız derlendiğinden emin olun.  
  
## <a name="testing-the-project-template"></a>Proje şablonu test etme  
 Şimdi proje şablonu test etmek hazırsınız. İlk olarak, Visual Studio'nun deneysel örneği SiteColumnProjectItem çözümde hata ayıklamayı Başlat. Ardından, test **Site sütunu** Visual Studio'nun deneysel örneği projesinde. Son olarak, yapı ve site sütunu beklendiği gibi çalıştığını doğrulamak için SharePoint Proje çalıştırın.  
  
#### <a name="to-start-debugging-the-solution"></a>Çözüm hata ayıklamayı başlatmak için  
  
1.  Yönetici kimlik bilgileriyle Visual Studio'yu yeniden başlatın ve ardından SiteColumnProjectItem çözümü açın.  
  
2.  
  
3.  SiteColumnProjectItemTypeProvider kod dosyasında kod ilk satırı bir kesme noktası eklemek `InitializeType` yöntemi ve ardından **F5** hata ayıklamayı başlatmak için anahtar.  
  
     Visual Studio %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\Site Column\1.0 uzantıyı yükleyen ve Visual Studio Deneysel bir örneğini başlatır. Proje öğesi Visual Studio'nun bu örnekte test edeceğiz.  
  
#### <a name="to-test-the-project-in-visual-studio"></a>Visual Studio'da projeyi test etmek için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **dosya**, **yeni**, **proje**.  
  
2.  Genişletin **Visual C#** veya **Visual Basic** düğümünü (bağlı olarak, proje şablonu destekleyen dil), **SharePoint** düğümünü ve ardından seçin**2010** düğümü.  
  
3.  Proje şablonları listesinden seçip **Site sütunu** şablonu.  
  
4.  İçinde **adı** kutusuna **SiteColumnTest** ve ardından **Tamam** düğmesi.  
  
     İçinde **Çözüm Gezgini**, yeni bir proje ile adlı bir proje öğesi görünür **alan1**.  
  
5.  Visual Studio'nun diğer örnek kodda, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `InitializeType` yöntemi ve ardından **F5** projede hataları ayıklamak devam etmek için anahtarı.  
  
6.  İçinde **Çözüm Gezgini**, seçin **alan1** düğümünü ve ardından **F4** anahtarı.  
  
     **Özellikleri** penceresi açılır.  
  
7.  Özellikler listesinde doğrulayın özelliği **örnek özellik** görüntülenir.  
  
#### <a name="to-test-the-site-column-in-sharepoint"></a>SharePoint site sütunu sınamak için  
  
1.  İçinde **Çözüm Gezgini**, seçin **SiteColumnTest** düğümü.  
  
2.  İçinde **özellikleri** penceresinde yanındaki metin kutusuna **Site URL'si** özelliği girin **http://localhost**.  
  
     Bu adım, hata ayıklama için kullanmak istediğiniz geliştirme bilgisayarındaki yerel SharePoint sitesini belirtir.  
  
    > [!NOTE]  
    >  **Site URL'si** Site sütunu proje şablonu proje oluşturulduğunda, bu değer toplanması için bir sihirbaz sağlamadığından özelliği varsayılan olarak boştur. Bu değer için geliştirici soran ve sonra bu özellik yeni projede yapılandırır Sihirbazı'nı eklemeyi öğrenmek için bkz: [izlenecek yol: bir proje şablonu, bölüm 2 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
3.  Seçin **F5** anahtarı.  
  
     Site sütunu paketlenir ve belirtilen SharePoint sitesi dağıtılan **Site URL'si** projesinin özelliği. Web tarayıcısı bu sitenin varsayılan sayfasını açar.  
  
    > [!NOTE]  
    >  Varsa **komut dosyası hata ayıklama devre dışı** seçin iletişim kutusu görüntülenirse, **Evet** projede hataları ayıklamak devam düğmesine.  
  
4.  Üzerinde **Site eylemleri** menüsünde seçin **Site Ayarları**.  
  
5.  Üzerinde **Site Ayarları** sayfasında **galerileri** listesinde, seçin **Site sütunları** bağlantı.  
  
6.  Site sütunları listesinde doğrulayın bir **özel sütunları** adlı bir sütun içeren grubu **SiteColumnTest**.  
  
7.  Web tarayıcısını kapatın.  
  
## <a name="cleaning-up-the-development-computer"></a>Geliştirme bilgisayarı temizleme  
 Proje testi tamamladıktan sonra proje şablonu Visual Studio Deneysel örnekten kaldırın.  
  
#### <a name="to-clean-up-the-development-computer"></a>Geliştirme bilgisayarı temizlemek için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantıları listesinden seçip **Site sütunu** uzantısı ve ardından **kaldırma** düğmesi.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** düğmesi uzantıyı kaldırmak istediğinizi onaylayın.  
  
4.  Seçin **Kapat** kaldırma işleminin tamamlanması için düğmesi.  
  
5.  Visual Studio (deneysel örneği ve Visual Studio SiteColumnProjectItem çözüm açıksa örneğini) hem örneklerini kapatın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuzu tamamladıktan sonra proje şablonu için bir sihirbaz ekleyebilirsiniz. Bir kullanıcı bir Site sütunu proje oluşturduğunda, kullanıcı hata ayıklama ve yeni bir çözüm korumalı olup için kullanmak üzere site URL'si için Sihirbazı'nı ister ve bu bilgilerle yeni proje Sihirbazı'nı yapılandırır. Sihirbaz ayrıca sütun (örneğin, temel türü ve grubun, site sütun galerisini sütununda listelemek) hakkında bilgi toplar ve bu bilgileri yeni proje Elements.xml dosyasında ekler. Daha fazla bilgi için bkz: [izlenecek yol: bir proje şablonu, bölüm 2 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: bir proje şablonu, bölüm 2 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint Proje öğeleri için öğe şablonları ve proje şablonları oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [SharePoint Proje sisteminin uzantılarında veri kaydetme](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [SharePoint Araç Uzantıları ile Özel Verileri İlişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
  