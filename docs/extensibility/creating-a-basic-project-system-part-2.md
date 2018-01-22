---
title: "Temel Proje sistem oluşturma, bölüm 2 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- writing a project system
- project system
- tutorial
ms.assetid: aee48fc6-a15f-4fd5-8420-7f18824de220
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 699f9176fd39cacaf2bb4f433cd9d2ceb8e326b5
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="creating-a-basic-project-system-part-2"></a>Temel Proje sistem oluşturma, bölüm 2
Bu serideki ilk izlenecek [temel bir proje sistem bölümü 1 oluşturma](../extensibility/creating-a-basic-project-system-part-1.md), temel proje sistem oluşturulacağını gösterir. Bu kılavuz, Visual Studio şablonu, bir özellik sayfası ve diğer özellikleri ekleyerek temel proje sistemde oluşturur. Bu yüklemeye başlamadan önce ilk izlenecek tamamlamanız gerekir.  
  
 Bu kılavuz, proje dosya adı uzantısı .myproj olan bir proje türü oluşturmak öğretir. İzlenecek yolu tamamlamak için Kılavuzu mevcut Visual C# proje sistemden taşır çünkü kendi dil oluşturmak zorunda değildir.  
  
 Bu kılavuzda, bu görevleri gerçekleştirmek üzere öğretir:  
  
-   Visual Studio şablonu oluşturun.  
  
-   Visual Studio şablon dağıtma.  
  
-   Proje türü alt düğümünde oluşturun **yeni proje** iletişim kutusu.  
  
-   Parametre değiştirme Visual Studio şablonunda etkinleştirin.  
  
-   Proje özellik sayfası oluşturun.  
  
> [!NOTE]
>  Bu izlenecek adımları bir C# proje üzerinde temel alır. Ancak, dosya adı uzantılarını ve kod gibi özellikleri dışında bir Visual Basic proje için aynı adımları kullanabilirsiniz.  
  
## <a name="creating-a-visual-studio-template"></a>Visual Studio şablon oluşturma  
 [Temel bir proje sistem bölümü 1 oluşturma](../extensibility/creating-a-basic-project-system-part-1.md) temel proje şablonu oluşturmak ve proje sistemine eklemek gösterilmektedir. Ayrıca bu şablonu kullanarak Visual Studio ile kaydetmek nasıl gösterir <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> sistem kayıt defterinde \Templates\Projects\SimpleProject\ klasörün tam yolunu Yazar özniteliği.  
  
 Visual Studio şablonu (.vstemplate dosyası) yerine temel proje şablonunu kullanarak, şablonun nasıl görünür denetleyebilirsiniz **yeni proje** iletişim kutusu ve şablon parametreleri nasıl değiştirilir.  .Vstemplate dosyasına nasıl kaynak dosyaları proje Sistem şablonu kullanarak bir proje oluşturduğunuzda eklenmesi gereken tanımlayan bir XML dosyasıdır. Proje sistemi .vstemplate dosyası ve bir .zip dosyası kaynak dosyalarında toplayarak yerleşik ve Visual Studio için bilinen bir konuma .zip dosyasını kopyalayarak dağıtılabilir. Bu işlem, daha sonra bu kılavuzda daha ayrıntılı açıklanmıştır.  
  
1.  İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], uygulayarak oluşturduğunuz SimpleProject çözümü açın [temel bir proje sistem bölümü 1 oluşturma](../extensibility/creating-a-basic-project-system-part-1.md).  
  
2.  SimpleProjectPackage.cs dosyasını bulun ProvideProjectFactory özniteliği. Null ile ikinci parametre (proje adı) ve dördüncü parametre (proje şablonu klasörün yolunu) yerine ". \\\NullPath "gibi.  
  
    ```  
    [ProvideProjectFactory(typeof(SimpleProjectFactory), null,  
        "Simple Project Files (*.myproj);*.myproj", "myproj", "myproj",  
        ".\\NullPath",  
    LanguageVsTemplate = "SimpleProject")]  
    ```  
  
3.  \Templates\Projects\SimpleProject\ klasörüne SimpleProject.vstemplate adlı bir XML dosyası ekleyin.  
  
4.  SimpleProject.vstemplate içeriğini aşağıdaki kodla değiştirin.  
  
    ```xml  
    <VSTemplate Version="2.0.0" Type="Project"  
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
      <TemplateData>  
        <Name>SimpleProject Application</Name>  
        <Description>  
            A project for creating a SimpleProject application  
         </Description>  
         <Icon>SimpleProject.ico</Icon>  
         <ProjectType>SimpleProject</ProjectType>  
      </TemplateData>  
      <TemplateContent>  
        <Project File="SimpleProject.myproj" ReplaceParameters="true">  
          <ProjectItem ReplaceParameters="true" OpenInEditor="true">  
              Program.cs  
          </ProjectItem>  
          <ProjectItem ReplaceParameters="true" OpenInEditor="false">  
             AssemblyInfo.cs  
          </ProjectItem>  
        </Project>  
      </TemplateContent>  
    </VSTemplate>  
    ```  
  
5.  İçinde **özellikleri** tüm beş dosyaları \Templates\Projects\SimpleProject\ klasör ve kümesi penceresinde, seçin **yapı eylemi** için **ZipProject**.  
  
 ![](../extensibility/media/simpproj2.png "SimpProj2")  
  
 \<TemplateData > bölümü, SimpleProject proje türü görünümünü ve konumunu belirler **yeni proje** iletişim kutusunda, aşağıdaki gibi:  
  
-   \<Adı > öğesi adları SimpleProject uygulama için proje şablonu.  
  
-   \<Açıklama > öğesi içeriyor görünür açıklama **yeni proje** proje şablonu seçildiğinde iletişim kutusu.  
  
-   \<Simgesi > öğesi SimpleProject proje türü ile birlikte görünen simgesini belirtir.  
  
-   \<ProjectType > öğesi adları proje türü **yeni proje** iletişim kutusu. Bu ad ProvideProjectFactory özniteliğinin proje adı parametresi değiştirir.  
  
    > [!NOTE]
    >  \<ProjectType > öğesi eşleşmelidir `LanguageVsTemplate` bağımsız değişkeni `ProvideProjectFactory` SimpleProjectPackage.cs dosya özniteliği.  
  
 \<TemplateContent > bölümüne yeni bir proje oluşturduğunuzda, oluşturulan bu dosyalar açıklanmaktadır:  
  
-   SimpleProject.myproj  
  
-   Program.cs  
  
-   AssemblyInfo.cs  
  
 Üç dosyalarının tümüne sahip `ReplaceParameters` parametre değiştirme sağlayan true olarak ayarlayın.  Program.cs dosyasının `OpenInEditor` bir proje oluşturduğunuzda Kod düzenleyicisinde açılması dosyanın neden true olarak ayarlayın.  
  
 Visual Studio şablon şeması öğeleri hakkında daha fazla bilgi için bkz: [Visual Studio şablon şeması başvurusu](../extensibility/visual-studio-template-schema-reference.md).  
  
> [!NOTE]
>  Bir projenin birden fazla Visual Studio şablon varsa, her ayrı bir klasörde şablonudur. O klasördeki her dosya olmalıdır **yapı eylemi** kümesine **ZipProject**.  
  
## <a name="adding-a-minimal-vsct-file"></a>En az .vsct dosya ekleme  
 Visual Studio yeni veya değiştirilmiş bir Visual Studio şablonu tanıyabilmesi için Kurulum modunda çalıştırılması gerekir. Kurulum modu bulunması için .vsct dosyası gerektirir. Bu nedenle, en az .vsct dosyayı projeye eklemeniz gerekir.  
  
1.  SimpleProject projeye SimpleProject.vsct adlı bir XML dosyası ekleyin.  
  
2.  SimpleProject.vsct dosyasının içeriğini aşağıdaki kodla değiştirin.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CommandTable  
      xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable">  
    </CommandTable>  
    ```  
  
3.  Ayarlama **yapı eylemi** bu dosyanın **VSCTCompile**. Bunu yalnızca .csproj dosyanızda de yapabilirsiniz **özellikleri** penceresi. Olduğundan emin olun **yapı eylemi** bu dosya kümesine **hiçbiri** bu noktada.  
  
    1.  SimpleProject düğümünü sağ tıklatın ve ardından **Düzenle SimpleProject.csproj**.  
  
    2.  .Csproj dosyanızda SimpleProject.vsct öğesini bulun.  
  
        ```  
        <None Include="SimpleProject.vsct" />  
        ```  
  
    3.  Yapı eylemini **VSCTCompile**.  
  
        ```  
        <VSCTCompile Include="SimpleProject.vsct" />  
        ```  
  
    4.  Proje dosyası ve Düzenleyicisi'ni kapatın.  
  
    5.  SimpleProject düğüm kaydedin ve ardından **Çözüm Gezgini** tıklatın **projeyi yeniden yükle**.  
  
## <a name="examining-the-visual-studio-template-build-steps"></a>Visual Studio şablon oluşturma adımlarının inceleniyor  
 VSPackage Proje yapı sistemi genellikle Visual Studio Kurulumu modunda .vstemplate dosya değiştirildi veya .vstemplate dosyasını içeren projeyi yeniden çalışır. Normal ya da daha yüksek MSBuild ayrıntı düzeyini ayarlayarak izleyebilirsiniz.  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.  
  
2.  Genişletme **projeler ve çözümler** düğümünü ve ardından **derleme ve çalıştırma**.  
  
3.  Ayarlama **MSBuild Proje yapı çıktı ayrıntı** için **Normal**. **Tamam**'ı tıklatın.  
  
4.  SimpleProject projeyi yeniden oluşturun.  
  
 Derleme adımı .zip proje dosyası oluşturmak için aşağıdaki örneğe benzemelidir.  
  
```  
ZipProjects:  
1>  Zipping ProjectTemplates  
1>  Zipping <path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip...  
1>  Copying file from "<path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip" to "<%LOCALAPPDATA%>\Microsoft\VisualStudio\14.0Exp\ProjectTemplates\\\\SimpleProject.zip".  
1>  Copying file from "<path>\SimpleProject\SimpleProject\obj\Debug\SimpleProject.zip" to "bin\Debug\\ProjectTemplates\\\\SimpleProject.zip".  
1>  SimpleProject -> <path>\SimpleProject\SimpleProject\bin\Debug\ProjectTemplates\SimpleProject.zip  
1>ZipItems:  
1>  Zipping ItemTemplates  
1>  SimpleProject ->  
```  
  
## <a name="deploying-a-visual-studio-template"></a>Visual Studio şablonu dağıtma  
 Visual Studio şablonları yol bilgisi içermez. Bu nedenle, şablon .zip dosyası Visual Studio için bilinen bir konuma dağıtılması gerekir. ProjectTemplates klasörü genellikle konumdur  **\<LOCALAPPDATA % > \Microsoft\VisualStudio\14.0Exp\ProjectTemplates**.  
  
 Proje Fabrikanızda dağıtmak için yükleme programını Yönetici ayrıcalıkları olmalıdır. Visual Studio yükleme düğümünde şablonları dağıtır: **...\Microsoft Visual Studio 14.0\Common7\IDE\ProjectTemplates**.  
  
## <a name="testing-a-visual-studio-template"></a>Visual Studio şablon test etme  
 Visual Studio şablonu kullanarak bir proje hiyerarşisi oluşturur olup olmadığını görmek için proje Fabrika sınayın.  
  
1.  Visual Studio SDK deneysel örneği sıfırlayın.  
  
     Üzerinde [!INCLUDE[win7](../debugger/includes/win7_md.md)]: Başlat menüsünde Bul **Microsoft Visual Studio/Microsoft Visual Studio SDK/Araçları** klasörünü ve ardından **Microsoft Visual Studio deneysel örneği sıfırlama**.  
  
     Windows'un sonraki sürümlerinde: Başlangıç ekranında, türü **Microsoft Visual Studio sıfırlama \<sürüm > deneysel örneği**.  
  
2.  Bir komut istemi penceresi görüntülenir. Sözcükleri gördüğünüzde `Press any key to continue`, ENTER tuşuna basın. Penceresi kapatıldıktan sonra Visual Studio'yu açın.  
  
3.  SimpleProject projeyi oluşturmak ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
4.  Deneysel örneğinde SimpleProject projesi oluşturun. İçinde **yeni proje** iletişim kutusunda **SimpleProject**.  
  
5.  SimpleProject yeni bir örneğini göreceksiniz.  
  
 ![](../extensibility/media/simpproj2_newproj.png "SimpProj2_NewProj")  
  
 ![](../extensibility/media/simpproj2_myproj.png "SimpProj2_MyProj")  
  
## <a name="creating-a-project-type-child-node"></a>Proje türü alt düğümü oluşturma  
 Proje türü düğümü için bir alt düğüm eklemek **yeni proje** iletişim kutusu.  Örneğin, SimpleProject proje türü için konsol uygulamaları, pencere uygulamaları, web uygulamaları ve benzeri için alt düğümleri olabilir.  
  
 Alt düğümler proje dosyası değiştirmeyi ve ekleyerek oluşturulur \<OutputSubPath > alt öğelerini \<ZipProject > öğeleri. Derleme veya dağıtım sırasında bir şablon kopyalandığında, her alt düğüm proje şablonları klasörünün bir alt haline gelir.  
  
 Bu bölümde SimpleProject proje türü için konsol alt düğümü oluşturulacağını gösterir.  
  
1.  \Templates\Projects\SimpleProject\ klasörü yeniden adlandırmak için \Templates\Projects\ConsoleApp\\.  
  
2.  İçinde **özellikleri** penceresinde \Templates\Projects\ConsoleApp\ klasördeki tüm beş dosyaları seçin ve emin olun **yapı eylemi** ayarlanır **ZipProject**.  
  
3.  SimpleProject.vstemplate dosyanın sonuna aşağıdaki satırı ekleyin \<TemplateData > bölümünde, kapanış etiketinin hemen önce.  
  
    ```  
    <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
    ```  
  
     Bu konsol alt düğüm hem alt düğüm üzerinde bir düzeyi SimpleProject üst düğümü görünmesi konsol uygulaması şablonu neden olur.  
  
4.  SimpleProject.vstemplate dosyasını kaydedin.  
  
5.  .Csproj dosyanızda şunları ekleyin \<OutputSubPath > ZipProject öğelerin her biri için. Proje olarak önce kaldırma ve proje dosyasını düzenleyin.  
  
6.  Bulun \<ZipProject > öğeleri. Her \<ZipProject > öğesi ekleme bir \<OutputSubPath > öğesi ve konsol değer verin. ZipProject  
  
    ```  
    <ZipProject Include="Templates\Projects\ConsoleApp\AssemblyInfo.cs">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\Program.cs">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.myproj">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.vstemplate">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>   
        <ZipProject Include="Templates\Projects\ConsoleApp\SimpleProject.ico">  
          <OutputSubPath>Console</OutputSubPath>  
        </ZipProject>  
    ```  
  
7.  Bu ekleme \<PropertyGroup > Proje dosyası için:  
  
    ```  
    <PropertyGroup>  
      <VsTemplateLanguage>SimpleProject</VsTemplateLanguage>  
    </PropertyGroup>  
    ```  
  
8.  Proje dosyasını kaydedin ve projeyi yeniden yükleyin.  
  
## <a name="testing-the-project-type-child-node"></a>Proje türü alt düğüm test etme  
 Test görmek için değiştirilmiş proje dosyası olup olmadığını **konsol** alt düğüm görünür **yeni proje** iletişim kutusu.  
  
1.  Çalıştırma **Microsoft Visual Studio deneysel örneği sıfırlama** aracı.  
  
2.  SimpleProject projeyi oluşturmak ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmelidir  
  
3.  İçinde **yeni proje** iletişim kutusunda, tıklatın **SimpleProject** düğümü. **Konsol uygulaması** şablonu görüntülenmedir **şablonları** bölmesi.  
  
4.  Genişletme **SimpleProject** düğümü. **Konsol** alt düğüm görünmelidir. **SimpleProject uygulama** şablonu devam görünmesi **şablonları** bölmesi.  
  
5.  biçimindeki telefon numarasıdır. Tıklatın **iptal** ve hata ayıklamayı durdurun  
  
 ![](../extensibility/media/simpproj2_rollup.png "SimpProj2_Rollup")  
  
 ![](../extensibility/media/simpproj2_subfolder.png "SimpProj2_Subfolder")  
  
## <a name="substituting-project-template-parameters"></a>Proje şablonu parametreleri değiştirme  
 [Temel bir proje sistem bölümü 1 oluşturma](../extensibility/creating-a-basic-project-system-part-1.md) üzerine yazmak nasıl oluşturulacağını gösterir `ProjectNode.AddFileFromTemplate` temel türde bir şablon parametresi değiştirme yapmak için yöntem. Bu bölümde daha karmaşık Visual Studio şablon parametreleri kullanmayı öğretir.  
  
 Bir Visual Studio şablonu kullanarak bir proje oluşturduğunuzda **yeni proje** iletişim kutusu, parametreleri ile değiştirilir şablon dizeleri proje özelleştirmek için. Şablon parametresi başlayıp bir dolar işareti, örneğin, $time$ biten özel bir belirteçtir. Aşağıdaki iki parametreyi şablonunu temel alan projeler özelleştirmesinde etkinleştirmek için özellikle yararlı olur:  
  
-   [1-10] $GUID$ yeni bir GUID ile değiştirilir. En fazla 10 benzersiz GUID, örneğin, $guid1$ belirtebilirsiniz.  
  
-   $safeprojectname$ olan bir kullanıcı tarafından sağlanan adı **yeni proje** iletişim kutusunda, tüm güvenli olmayan karakterleri ve boşlukları kaldırmak için değiştirdi.  
  
 Şablon parametreleri tam bir listesi için bkz: [şablon parametreleri](../ide/template-parameters.md).  
  
#### <a name="to-substitute-project-template-parameters"></a>Proje şablonu parametreleri değiştirmek için  
  
1.  SimpleProjectNode.cs dosyasında kaldırın `AddFileFromTemplate` yöntemi.  
  
2.  In the \Templates\Projects\ConsoleApp\SimpleProject.myproj file, locate the \<RootNamespace> property and change its value to $safeprojectname$.  
  
    ```  
    <RootNamespace>$safeprojectname$</RootNamespace>  
    ```  
  
3.  In the \Templates\Projects\SimpleProject\Program.cs file, replace the contents of the file with the following code:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Runtime.InteropServices;    // Guid  
  
    namespace $safeprojectname$  
    {  
        [Guid("$guid1$")]  
        public class $safeprojectname$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
4.  SimpleProject projeyi oluşturmak ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmesi gerekir.  
  
5.  Yeni bir SimpleProject konsol uygulaması oluşturun. (İçinde **proje türleri** bölmesinde, **SimpleProject**. Altında **Visual Studio yüklenmiş şablonlar**seçin **konsol uygulaması**.)  
  
6.  Yeni oluşturulan projesinde Program.cs açın. Aşağıdakine benzer görünmelidir (dosyanızdaki GUID değerlerini farklıdır.):  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Runtime.InteropServices;    // Guid  
  
    namespace Console_Application1  
    {  
        [Guid("00000000-0000-0000-00000000-00000000)"]  
        public class Console_Application1  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
## <a name="creating-a-project-property-page"></a>Proje özellik sayfası oluşturma  
 Böylece kullanıcılar görüntüleyebilir ve şablonunu temel alan projeler özelliklerini değiştirin, proje türü için özellik sayfası oluşturabilirsiniz. Bu bölümde bir yapılandırma bağımsız özellik sayfası oluşturulacağını gösterir. Bu temel özellik sayfası özellikleri ızgara özellik sayfası sınıfınızda kullanıma genel özelliklerini görüntülemek için kullanır.  
  
 Özellik sayfası sınıfından türetilen `SettingsPage` temel sınıfı. Tarafından sağlanan özellikleri ızgara `SettingsPage` sınıfı en temel veri türlerini farkındadır ve bunların nasıl görüntüleneceği bilir.  Ayrıca, `SettingsPage` sınıfı proje dosyasına özellik değerleri kalıcı hale getirmek nasıl bilir.  
  
 Bu bölümde oluşturduğunuz özellik sayfası alter ve bu proje özellikleri kaydetmenize olanak sağlar:  
  
-   AssemblyName  
  
-   OutputType  
  
-   RootNamespace.  
  
1.  Bu SimpleProjectPackage.cs dosyasına ekleyin `ProvideObject` özniteliğini `SimpleProjectPackage` sınıfı:  
  
    ```  
    [ProvideObject(typeof(GeneralPropertyPage))]  
    public sealed class SimpleProjectPackage : ProjectPackage  
    ```  
  
     Bu özellik sayfası sınıfı kaydeder `GeneralPropertyPage` com ile  
  
2.  Bu iki geçersiz kılınan yöntem SimpleProjectNode.cs dosyasına ekleyin `SimpleProjectNode` sınıfı:  
  
    ```  
    protected override Guid[] GetConfigurationIndependentPropertyPages()  
    {  
        Guid[] result = new Guid[1];  
        result[0] = typeof(GeneralPropertyPage).GUID;  
        return result;  
    }  
    protected override Guid[] GetPriorityProjectDesignerPages()  
    {  
        Guid[] result = new Guid[1];  
        result[0] = typeof(GeneralPropertyPage).GUID;  
         return result;  
    }  
    ```  
  
     Bu yöntemlerin her ikisi de GUID'ler özellik sayfasının bir dizi döndürür.  Dizideki, yalnızca öğe GeneralPropertyPage GUID'dir böylece **özellik sayfaları** iletişim kutusu, yalnızca bir sayfa gösterir.  
  
3.  SimpleProject projeye GeneralPropertyPage.cs adlı bir sınıf dosyası ekleyin.  
  
4.  Bu dosyanın içeriğini aşağıdaki kodla değiştirin:  
  
    ```  
    using System;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Project;  
    using System.ComponentModel;  
  
    namespace SimpleProject  
    {  
        [ComVisible(true)]  
        [Guid("6BC7046B-B110-40d8-9F23-34263D8D2936")]  
        public class GeneralPropertyPage : SettingsPage  
        {  
            private string assemblyName;  
            private OutputType outputType;  
            private string defaultNamespace;  
  
            public GeneralPropertyPage()  
            {  
                this.Name = "General";  
            }  
  
            [Category("AssemblyName")]  
            [DisplayName("AssemblyName")]  
            [Description("The output file holding assembly metadata.")]  
            public string AssemblyName  
            {  
                get { return this.assemblyName; }  
            }  
            [Category("Application")]  
            [DisplayName("OutputType")]  
            [Description("The type of application to build.")]  
            public OutputType OutputType  
            {  
                get { return this.outputType; }  
                set { this.outputType = value; this.IsDirty = true; }  
            }  
            [Category("Application")]  
            [DisplayName("DefaultNamespace")]  
            [Description("Specifies the default namespace for added items.")]  
            public string DefaultNamespace  
            {  
                get { return this.defaultNamespace; }  
                set { this.defaultNamespace = value; this.IsDirty = true; }  
            }  
  
            protected override void BindProperties()  
            {  
                this.assemblyName = this.ProjectMgr.GetProjectProperty(  
    "AssemblyName", true);  
                this.defaultNamespace = this.ProjectMgr.GetProjectProperty(  
    "RootNamespace", false);  
  
                string outputType = this.ProjectMgr.GetProjectProperty(  
    "OutputType", false);  
                this.outputType =   
    (OutputType)Enum.Parse(typeof(OutputType), outputType);  
            }  
  
            protected override int ApplyChanges()  
            {  
                this.ProjectMgr.SetProjectProperty(  
    "AssemblyName", this.assemblyName);  
                this.ProjectMgr.SetProjectProperty(  
    "OutputType", this.outputType.ToString());  
                this.ProjectMgr.SetProjectProperty(  
    "RootNamespace", this.defaultNamespace);  
                this.IsDirty = false;  
  
                return VSConstants.S_OK;  
            }  
        }  
    }  
    ```  
  
     `GeneralPropertyPage` Sınıfı AssemblyName, OutputType ve RootNamespace üç ortak özellikler sunar. Set yöntemi yok AssemblyName sahip olduğundan, salt okunur bir özellik olarak görüntülenir. OutputType numaralandırılmış bir sabiti olduğundan, aşağı açılan liste olarak görüntülenir.  
  
     `SettingsPage` Temel sınıf sağlar `ProjectMgr` özellikleri kalıcı hale getirmek için. `BindProperties` Yöntemi kullanan `ProjectMgr` kalıcı özellik değerlerini almak ve ilgili özellikleri ayarlayın.  `ApplyChanges` Yöntemi kullanan `ProjectMgr` özelliklerinin değerlerini almak ve bunları proje dosyasına kalıcı hale getirmek için. Özellik set yöntemi kümeleri `IsDirty` özellikleri kalıcı olduğunu belirtmek için true.  Proje ve çözüm kaydettiğinizde Kalıcılık oluşur.  
  
5.  SimpleProject çözümü yeniden derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmesi gerekir.  
  
6.  Deneysel örneğinde yeni bir SimpleProject uygulaması oluşturun.  
  
7.  Visual Studio Visual Studio şablonunu kullanarak bir proje oluşturmak için proje Fabrika çağırır. Kod Düzenleyicisi'nde Yeni Program.cs dosyasının açıldı.  
  
8.  Proje düğümüne sağ tıklayın **Çözüm Gezgini**ve ardından **özellikleri**. **Özellik sayfaları** iletişim kutusu görüntülenir.  
  
 ![](../extensibility/media/simpproj2_proppage.png "SimpProj2_PropPage")  
  
## <a name="testing-the-project-property-page"></a>Proje özellik sayfası test etme  
 Şimdi değiştirmek ve özellik değerlerini değiştirmek olup olmadığını sınayabilirsiniz.  
  
1.  İçinde **KonsolUygulamam özellik sayfaları** iletişim kutusu, değişiklik **DefaultNamespace** için **MyApplication**.  
  
2.  Seçin **OutputType** özelliği ve ardından **sınıf kitaplığı**.  
  
3.  Tıklatın **Uygula**ve ardından **Tamam**.  
  
4.  Yeniden **özellik sayfaları** iletişim kutusu ve değişikliklerinizi kalıcı doğrulayın.  
  
5.  Visual Studio Deneysel örneklerini kapatın.  
  
6.  Deneysel örneği yeniden açın.  
  
7.  Yeniden **özellik sayfaları** iletişim kutusu ve değişikliklerinizi kalıcı doğrulayın.  
  
8.  Visual Studio Deneysel örneklerini kapatın.  
  
 ![](../extensibility/media/simpproj2_proppage2.png "SimpProj2_PropPage2")