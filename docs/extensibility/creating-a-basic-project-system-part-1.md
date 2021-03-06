---
title: Temel Proje sistemi oluşturma, bölüm 1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- writing a project system
- project system
- tutorial
ms.assetid: 882a10fa-bb1c-4b01-943a-7a3c155286dd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2343218da765ad8bb9a10d585001c5f3321a0137
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902405"
---
# <a name="create-a-basic-project-system-part-1"></a>1. Bölüm temel proje sistemi oluşturma
Visual Studio'da projeler kaynak kodu dosyaları ve diğer varlıkları düzenlemek için geliştiricilerin kullanan kapsayıcılardır. Projeleri görünür çözümlerin alt öğeleri olarak **Çözüm Gezgini**. Projeleri, düzenleme, derleme, hata ayıklama ve kaynak kod dağıtma ve Web Hizmetleri, veritabanları ve diğer kaynaklara başvurular oluşturma olanak tanır.  
  
 Projeleri tanımlanmış proje dosyalarında, örneğin bir *.csproj* Visual C# proje dosyası. Kendi proje dosya adı uzantısına sahip kendi proje türünüzü oluşturabilirsiniz. Proje türleri hakkında daha fazla bilgi için bkz: [proje türleri](../extensibility/internals/project-types.md).  
  
> [!NOTE]
>  Visual Studio bir özel proje türüyle genişletmeniz gerekiyorsa, yararlanarak öneririz [Visual Studio Proje sistemi](https://github.com/Microsoft/VSProjectSystem) (VSPS) birkaç sıfırdan bir proje sistemi oluşturmanın avantajları vardır:  
>   
>  -  Daha kolay ekleme.  On binlerce kod satırı bile temel proje sistemi gerektirir.  I ihtiyaçlarınıza göre özelleştirmek önce VSPS yararlanarak için birkaç tıklamayla ekleme maliyeti azaltır.  
>  -  Bakım daha kolay.  VSPS yararlanarak, yalnızca kendi senaryolarınızı sürdürmeniz gerekir.  Proje sistemi altyapısının sürdürülmesinden işleme.  
>   
>  Visual Studio'nun Visual Studio 2013'ten eski sürümlerini hedefleyen gerekiyorsa, bir Visual Studio Uzantısı'nda VSPS yararlanmasını mümkün olmayacaktır.  Bu durumda, bu izlenecek yolda kullanmaya başlamak için iyi bir yerdir.  
  
 Bu izlenecek yol, proje dosya adı uzantısına sahip bir proje türünün nasıl oluşturacağını gösterir *.myproj*. Bu izlenecek yol, mevcut Visual C# proje sistemi taşır.  
  
> [!NOTE]
>  Uzantı projelerinin daha fazla örnek için bkz. [VSSDK örnekleri](http://aka.ms/vs2015sdksamples).  
  
 Bu izlenecek yol aşağıdaki görevlerin nasıl yerine getirileceğini öğretir:  
  
-   Temel Proje türü oluşturun.  
  
-   Temel Proje şablonu oluşturun.  
  
-   Proje şablonu Visual Studio ile kaydedin.  
  
-   Bir proje örneği açarak oluşturma **yeni proje** iletişim kutusunu ve ardından, şablonunuzu kullanarak.  
  
-   Proje sistemi için bir proje fabrikası oluşturursunuz.  
  
-   Proje sistemi için bir proje düğümü oluşturun.  
  
-   Proje sistemi için özel simgeleri ekleyin.  
  
-   Temel Şablon parametre değiştirme uygulayın.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, size Visual Studio SDK İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yi daha sonra yükleyebilirsiniz. Daha fazla bilgi için [Visual Studio SDK'yı yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
 Ayrıca, kaynak kodu indirmeniz gerekir [projeleri için yönetilen paket çerçevesini](https://github.com/tunnelvisionlabs/MPFProj10). Çözümü oluşturmak için oluşturacağınız erişilebilir bir konuma ayıklayın.  
  
## <a name="create-a-basic-project-type"></a>Temel Proje türü oluştur  
 Adlı bir C# VSIX projesi oluşturun **SimpleProject**. (**Dosya** > **yeni** > **proje** ardından **Visual C#**  >   **Genişletilebilirlik** > **VSIX projesi**). Visual Studio Paket projesi öğe şablonu Ekle (üzerinde **Çözüm Gezgini**, proje düğümüne sağ tıklayıp **Ekle** > **yeni öğe**gidin **Genişletilebilirlik** > **Visual Studio paket**). Dosya adı *SimpleProjectPackage*.  
  
## <a name="creating-a-basic-project-template"></a>Temel Proje şablonu oluşturma  
 Şimdi, yeni uygulamak için bu temel VSPackage değiştirebilirsiniz *.myproj* proje türü. Temel alan bir proje oluşturmak için *.myproj* proje türü, Visual Studio hangi dosyaları, kaynaklar ve yeni projeye eklemek için başvurular bilmek sahiptir. Bu bilgiyi sağlamak için proje dosyaları bir proje şablonu klasörüne yerleştirin. Bir kullanıcı kullandığında *.myproj* bir proje oluşturmak için proje, projeye yeni dosyalar kopyalanır.  
  
### <a name="to-create-a-basic-project-template"></a>Temel Proje şablonu oluşturmak için  
  
1.  Üç klasör projesi altında başka bir tane ekleyin: *Templates\Projects\SimpleProject*. (İçinde **Çözüm Gezgini**, sağ **SimpleProject** proje düğümünü, işaret **Ekle**ve ardından **yeni klasör**. Klasör adı *şablonları*. İçinde *şablonları* klasör adında bir klasör ekleme *projeleri*. Buna *projeleri* klasör adında bir klasör Ekle *SimpleProject*.)  
  
2.  İçinde *Templates\Projects\SimpleProject* klasöründe adlı simge olarak kullanılacak bir bit eşlem resim dosyası eklemek *SimpleProject.ico*. Tıkladığınızda **Ekle**, simge Düzenleyicisi açılır.  
  
3.  Ayırıcı simgesi olun. Bu simge görünür **yeni proje** iletişim kutusunda daha sonra gözden geçirme.  
  
     ![Basit bir proje simgesi](../extensibility/media/simpleprojicon.png "SimpleProjIcon")  
  
4.  Kaydet simgesine ve simge Düzenleyicisi'ni kapatın.  
  
5.  İçinde *Templates\Projects\SimpleProject* klasör ekleme bir **sınıfı** adlı öğe *Program.cs*.  
  
6.  Varolan kodu aşağıdaki satırlarla değiştirin.  
  
    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Text;
  
    namespace $nameSpace$
    {  
        public class $className$
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Hello VSX!!!");
                Console.ReadKey();
            }
        }
    }
    ```
  
    > [!IMPORTANT]
    >  Bu son biçiminde değil *Program.cs* kodudur parametreler ele ile daha sonraki bir adımda değiştirme. Görebileceğiniz derleme hataları, ancak olduğu sürece dosyanın **BuildAction** olduğu **içerik**, oluşturun ve projeyi zamanki çalıştırmak mümkün olması gerekir.  
  
1.  Dosyayı kaydedin.  
  
2.  Kopyalama *AssemblyInfo.cs* dosya *özellikleri* klasörüne *Projects\SimpleProject* klasör.  
  
3.  İçinde *Projects\SimpleProject* klasörü Ekle adlı bir XML dosyası *SimpleProject.myproj*.  
  
    > [!NOTE]
    >  Bu türün tüm projeleri için dosya adı uzantısı *.myproj*. Bunu değiştirmek istiyorsanız, bu kılavuzda açıklanan her yerde değiştirmelisiniz.  
  
4.  Var olan içeriğin aşağıdaki satırlarla değiştirin.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <SchemaVersion>2.0</SchemaVersion>  
        <ProjectGuid></ProjectGuid>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>MyRootNamespace</RootNamespace>  
        <AssemblyName>MyAssemblyName</AssemblyName>  
        <EnableUnmanagedDebugging>false</EnableUnmanagedDebugging>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
        <DebugSymbols>true</DebugSymbols>  
        <OutputPath>bin\Debug\</OutputPath>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">  
        <DebugSymbols>false</DebugSymbols>  
        <OutputPath>bin\Release\</OutputPath>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="mscorlib" />  
        <Reference Include="System" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Xml" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="AssemblyInfo.cs">  
          <SubType>Code</SubType>  
        </Compile>  
        <Compile Include="Program.cs">  
          <SubType>Code</SubType>  
        </Compile>  
      </ItemGroup>  
      <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />  
    </Project>  
    ```  
  
5.  Dosyayı kaydedin.  
  
6.  İçinde **özellikleri** penceresinde **derleme eylemi** , *AssemblyInfo.cs*, *Program.cs*, *SimpleProject.ico* , ve *SimpleProject.myproj* için **içerik**ve bunların **VSIX Ekle** özelliklerine **True**.  
  
 Bu proje şablonu, hem hata ayıklama yapılandırmasının hem de yayın yapılandırması içeren bir temel Visual C# projesi açıklar. İki kaynak dosyaları, projeyi içeren *AssemblyInfo.cs* ve *Program.cs*ve birden çok bütünleştirilmiş kod başvuruları. Bir proje şablondan oluşturulduğunda ProjectGuid değeri otomatik olarak yeni bir GUID ile değiştirilir.  
  
 İçinde **Çözüm Gezgini**, Genişletilmiş **şablonları** klasörü aşağıdaki gibi görünmelidir:

```
Templates  
   Projects  
      SimpleProject  
         AssemblyInfo.cs  
         Program.cs  
         SimpleProject.ico  
         SimpleProject.myproj  
```

## <a name="create-a-basic-project-factory"></a>Temel Proje fabrikası oluşturma  
 Visual Studio Proje şablonu klasörünüzün konumu söylemeniz gerekir. Bunu yapmak için proje fabrikası uygular ve böylece VSPackage oluşturulduğunda şablon konumun sistem kayıt defterine yazılır VSPackage sınıfına bir öznitelik ekleyin. Proje fabrikası GUID tarafından tanımlanan bir temel proje fabrikası oluşturarak başlayın. Kullanım <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> proje factory öğesine bağlamak için öznitelik `SimpleProjectPackage` sınıfı.  
  
### <a name="to-create-a-basic-project-factory"></a>Temel Proje fabrikası oluşturmak için  
  
1.  GUID'leri için proje factory'nizi oluşturmak (üzerinde **Araçları** menüsünde tıklatın **GUID Oluştur**), veya aşağıdaki örnekte birini kullanın. GUID'lere ekleme `SimpleProjectPackage` sınıfı zaten tanımlanmış bir bölümle yakın `PackageGuidString`. GUID'ler, hem GUID ve dize formunda olmalıdır. Sonuç kodu, aşağıdaki örneğe benzemelidir.  
  
    ```csharp  
        public sealed class SimpleProjectPackage : Package
        {  
            ...
            public const string SimpleProjectPkgString = "96bf4c26-d94e-43bf-a56a-f8500b52bfad";  
            public const string SimpleProjectFactoryString = "471EC4BB-E47E-4229-A789-D1F5F83B52D4";  
    
            public static readonly Guid guidSimpleProjectFactory = new Guid(SimpleProjectFactoryString);  
        }  
    ```  
  
3.  Bir sınıfın en üstüne ekleyin *SimpleProject* adlı klasöre *SimpleProjectFactory.cs*.  
  
4.  Aşağıdaki using deyimlerini:  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
5.  Bir GUID özniteliğe eklemek `SimpleProjectFactory` sınıfı. Öznitelik yeni proje Üreteç GUID değeridir.  
  
    ```csharp  
    [Guid(SimpleProjectPackage.SimpleProjectFactoryString)]  
    class SimpleProjectFactory  
    {  
    }  
    ```  
  
 Şimdi, proje şablonu kaydedebilirsiniz.  
  
### <a name="to-register-the-project-template"></a>Proje şablonu kaydetmek için  
  
1.  İçinde *SimpleProjectPackage.cs*, ekleme bir <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> özniteliğini `SimpleProjectPackage` sınıfına aşağıdaki gibi.  
  
    ```csharp  
    [ProvideProjectFactory(    typeof(SimpleProjectFactory),     "Simple Project",   
        "Simple Project Files (*.myproj);*.myproj", "myproj", "myproj",   
        @"Templates\Projects\SimpleProject",     LanguageVsTemplate = "SimpleProject")]  
    [Guid(SimpleProjectPackage.PackageGuidString)]  
    public sealed class SimpleProjectPackage : Package  
    ```  
  
2.  Çözümü yeniden oluşturun ve hatasız oluşturulduğunu doğrulayın.  
  
     Yeniden oluşturma, proje şablonu kaydeder.  
  
 Parametreleri `defaultProjectExtension` ve `possibleProjectExtensions` proje dosya adı uzantısına ayarlayın (*.myproj*). `projectTemplatesDirectory` Parametresi göreli yoluna ayarlanmış *şablonları* klasör. Derleme sırasında bu yol için tam bir derleme dönüştürülür ve proje sistemi kaydetmek için kayıt defterine eklendi.  
  
## <a name="test-the-template-registration"></a>Şablonu kayıt testi  
 Şablonu kayıt Visual Studio şablon adını ve simgesini görüntüleyebilmesi bu Visual Studio Proje şablonu klasörünüzün konumu söyler **yeni proje** iletişim kutusu.  
  
### <a name="to-test-the-template-registration"></a>Şablonu kayıt test etmek için  
  
1.  Tuşuna **F5** Visual Studio'nun deneysel örneği hata ayıklama başlatılamıyor.  
  
2.  Deneysel örneğinde, yeni oluşturulan proje türünü yeni bir proje oluşturun. İçinde **yeni proje** iletişim kutusu görmeniz **SimpleProject** altında **yüklü şablonlar**.  
  
 Artık kayıtlı bir proje fabrikası var. Henüz de, bir proje oluşturulamıyor. Proje paket ve proje fabrikası oluşturma ve bir proje başlatmak için birlikte çalışır.  
  
## <a name="add-the-managed-package-framework-code"></a>Yönetilen paket çerçevesini kodu ekleyin  
 Proje paket proje fabrikası arasında bağlantı uygulayın.  
  
-   Kaynak kodu dosyaları için yönetilen paket çerçevesini alın.  
  
    1.  SimpleProject projeyi (içinde **Çözüm Gezgini**, proje düğümünü seçin ve bağlam menüsünde **projeyi**.) ve proje dosyasını XML düzenleyicisinde açın.  
  
    2.  Aşağıdaki blokları proje dosyasına ekleyin (yukarıdaki \<alma > blokları). Ayarlama `ProjectBasePath` konumunu *ProjectBase.files* az önce indirdiğiniz yönetilen paket çerçevesini kod dosyasında. Yol için bir ters eğik çizgi eklemeniz gerekebilir. Bunu yapmazsanız, proje yönetilen paket çerçevesini kaynak kodunu bulmak başarısız olabilir.  
  
        ```  
        <PropertyGroup>  
             <ProjectBasePath>your path here\</ProjectBasePath>  
             <RegisterWithCodebase>true</RegisterWithCodebase>  
          </PropertyGroup>  
          <Import Project="$(ProjectBasePath)\ProjectBase.Files" />  
        ```  
  
        > [!IMPORTANT]
        >  Yolun sonuna ters eğik çizgi unutmayın.  
  
    3.  Projeyi yeniden yükleyin.  
  
    4.  Aşağıdaki derlemelere başvurular ekleyin:  
  
        -   `Microsoft.VisualStudio.Designer.Interfaces` (içinde  *\<VSSDK yükleme > \VisualStudioIntegration\Common\Assemblies\v2.0*)  
  
        -   `WindowsBase`  
  
        -   `Microsoft.Build.Tasks.v4.0`  
  
### <a name="to-initialize-the-project-factory"></a>Proje fabrikası başlatılamadı  
  
1.  İçinde *SimpleProjectPackage.cs* dosyasında, aşağıdaki ekleyin `using` deyimi.  
  
    ```csharp  
    using Microsoft.VisualStudio.Project;  
    ```  
  
2.  Türetilen `SimpleProjectPackage` gelen sınıfı `Microsoft.VisualStudio.Package.ProjectPackage`.  
  
    ```csharp  
    public sealed class SimpleProjectPackage : ProjectPackage  
    ```  
  
3.  Proje üreteci kaydettirir. Aşağıdaki satırı ekleyin `SimpleProjectPackage.Initialize` yöntemi hemen sonrasına `base.Initialize`.  
  
    ```csharp  
    base.Initialize();  
    this.RegisterProjectFactory(new SimpleProjectFactory(this));  
    ```  
  
4.  Soyut özelliği uygulama `ProductUserContext`:  
  
    ```csharp  
    public override string ProductUserContext  
        {  
            get { return ""; }  
    }  
    ```  
  
5.  İçinde *SimpleProjectFactory.cs*, aşağıdaki `using` varolan sonra deyimi `using` deyimleri.  
  
    ```csharp  
    using Microsoft.VisualStudio.Project;  
    ```  
  
6.  Türetilen `SimpleProjectFactory` gelen sınıfı `ProjectFactory`.  
  
    ```csharp  
    class SimpleProjectFactory : ProjectFactory  
    ```  
  
7.  İşlevsiz aşağıdaki yöntemi ekleyin `SimpleProjectFactory` sınıfı. Bir sonraki bölümde bu yöntemi uygular.  
  
    ```csharp  
    protected override ProjectNode CreateProject()  
    {  
        return null;  
    }  
    ```  
  
8.  Aşağıdaki alan ve oluşturucuya ekleyin `SimpleProjectFactory` sınıfı. Bu `SimpleProjectPackage` başvuru bir hizmet sağlayıcı sitesi ayarı kullanılabilir olacak şekilde özel bir alanda önbelleğe alınır.  
  
    ```csharp  
    private SimpleProjectPackage package;  
  
    public SimpleProjectFactory(SimpleProjectPackage package)  
        : base(package)  
    {  
        this.package = package;  
    }  
    ```  
  
9. Çözümü yeniden oluşturun ve hatasız oluşturulduğunu doğrulayın.  
  
## <a name="test-the-project-factory-implementation"></a>Test projesi Üreteç uygulaması  
 Proje fabrikası uygulamanız için oluşturucu çağrılır olup olmadığını test edin.  
  
### <a name="to-test-the-project-factory-implementation"></a>Proje fabrikası uygulamasını test etmek için  
  
1.  İçinde *SimpleProjectFactory.cs* dosyasında, aşağıdaki satırında bir kesme noktası ayarlamak `SimpleProjectFactory` Oluşturucusu.  
  
    ```csharp  
    this.package = package;  
    ```  
  
2.  Tuşuna **F5** Visual Studio'nun deneysel örneği başlatmak için.  
  
3.  Yeni bir proje oluşturmak deneysel örneğinde başlatın. İçinde **yeni proje** iletişim kutusunda **SimpleProject** proje türü ve ardından **Tamam**. Yürütme kesme noktasında durur.  
  
4.  Kesme noktası temizleyin ve hata ayıklamayı durdurun. Biz bir proje düğümü oluşturmadınız olduğundan, proje oluşturma kodunu hala özel durum oluşturur.  
  
## <a name="extend-the-projectnode-class"></a>ProjectNode sınıfını genişletir  
 Şimdi, uygulayabileceğiniz `SimpleProjectNode` türetilen sınıf `ProjectNode` sınıfı. `ProjectNode` Temel sınıf projesi oluşturulurken aşağıdaki görevleri işler:  
  
-   Proje şablonu dosyası kopyalar *SimpleProject.myproj*, yeni proje klasörüne. Kopya girildiğini adına göre adlandırılır **yeni proje** iletişim kutusu. `ProjectGuid` Özellik değeri yeni bir GUID ile değiştirilir.  
  
-   MSBuild öğeleri proje şablonu dosyasının erişir *SimpleProject.myproj*ve arar `Compile` öğeleri. Her `Compile` hedef dosya, dosyanın yeni bir proje klasörüne kopyalar.  
  
 Türetilmiş `SimpleProjectNode` sınıfı bu görevleri işler:  
  
-   Proje ve dosya düğümler için simgeler sağlar **Çözüm Gezgini** seçili veya oluşturulacak.  
  
-   Ek proje şablonu parametresi değişimleri belirtilmesine olanak sağlar.  
  
### <a name="to-extend-the-projectnode-class"></a>ProjectNode sınıfı genişletmek için  
  
1.  Adlı bir sınıf ekleyin `SimpleProjectNode.cs`.  
  
2.  Varolan kodu aşağıdaki kodla değiştirin.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Project;  
  
    namespace SimpleProject  
    {  
        public class SimpleProjectNode : ProjectNode  
        {  
            private SimpleProjectPackage package;  
  
            public SimpleProjectNode(SimpleProjectPackage package)  
            {  
                this.package = package;  
            }  
            public override Guid ProjectGuid  
            {  
                get { return SimpleProjectPackage.guidSimpleProjectFactory; }  
            }  
            public override string ProjectType  
            {  
                get { return "SimpleProjectType"; }  
            }  
  
            public override void AddFileFromTemplate(  
                string source, string target)  
            {  
                this.FileTemplateProcessor.UntokenFile(source, target);  
                this.FileTemplateProcessor.Reset();  
            }  
        }  
    }  
    ```  
  
 Bu `SimpleProjectNode` sınıf uygulamasını bu geçersiz kılınan yöntemleri vardır:  
  
-   `ProjectGuid`, proje Üreteç GUID döndürür.  
  
-   `ProjectType`, yerelleştirilmiş adı proje türünü döndürür.  
  
-   `AddFileFromTemplate`, seçilen dosyaları kopyalayan şablon klasöründen hedef projeye. Bu yöntem, daha sonraki bir bölümde uygulanır.  
  
 `SimpleProjectNode` Oluşturucusu gibi `SimpleProjectFactory` oluşturucusu, önbelleğe alan bir `SimpleProjectPackage` daha sonra kullanmak için özel bir alan başvuru.  
  
 Bağlanmak için `SimpleProjectFactory` sınıfının `SimpleProjectNode` sınıfı gerekir örneği yeni bir `SimpleProjectNode` içinde `SimpleProjectFactory.CreateProject` yöntemi ve daha sonra kullanmak için özel bir alan olarak önbelleğe alır.  
  
### <a name="to-connect-the-project-factory-class-and-the-node-class"></a>Proje fabrikası sınıfı ve düğümü sınıfı bağlamak için  
  
1.  İçinde *SimpleProjectFactory.cs* dosyasında, aşağıdaki ekleyin `using` deyimi:  
  
    ```csharp  
    using IOleServiceProvider =    Microsoft.VisualStudio.OLE.Interop.IServiceProvider;  
    ```  
  
2.  Değiştirin `SimpleProjectFactory.CreateProject` aşağıdaki kodu kullanarak yöntemi.  
  
    ```csharp  
    protected override ProjectNode CreateProject()  
    {  
        SimpleProjectNode project = new SimpleProjectNode(this.package);  
  
        project.SetSite((IOleServiceProvider)        ((IServiceProvider)this.package).GetService(            typeof(IOleServiceProvider)));  
        return project;  
    }  
    ```  
  
3.  Çözümü yeniden oluşturun ve hatasız oluşturulduğunu doğrulayın.  
  
## <a name="test-the-projectnode-class"></a>Test ProjectNode sınıfı  
 Bir proje hiyerarşisi oluşturur olup olmadığını görmek için proje fabrikanızı test edin.  
  
### <a name="to-test-the-projectnode-class"></a>ProjectNode sınıfı test etmek için  
  
1.  Tuşuna **F5** hata ayıklama başlatılamıyor. Deneysel örneğinde yeni bir SimpleProject oluşturun.  
  
2.  Visual Studio bir proje oluşturmak için proje fabrikanızı çağırmalıdır.  
  
3.  Visual Studio'nun deneysel örneği kapatın.  
  
## <a name="add-a-custom-project-node-icon"></a>Özel proje düğümü simgesi Ekle  
 Önceki bölümdeki proje düğümü simgesi, varsayılan bir simge bulunuyor. Özel bir simge değiştirebilirsiniz.  
  
### <a name="to-add-a-custom-project-node-icon"></a>Özel proje düğümü simge eklemek için  
  
1.  İçinde **kaynakları** klasöründe adlı bir bit eşlem dosyası ekleme *SimpleProjectNode.bmp*.  
  
2.  İçinde **özellikleri** windows bit eşlem 16 x 16 piksel azaltır. Bit eşlem farklı olun.  
  
     ![Basit bir proje iletişimi](../extensibility/media/simpleprojprojectcomm.png "SimpleProjProjectComm")  
  
3.  İçinde **özellikleri** penceresinde değişiklik **derleme eylemi** için bit eşlemin **gömülü kaynak**.  
  
4.  İçinde *SimpleProjectNode.cs*, aşağıdaki `using` ifadeleri:  
  
    ```csharp  
    using System.Drawing;  
    using System.Windows.Forms;  
    ```  
  
5.  Aşağıdaki statik alan ekleyip oluşturucuya `SimpleProjectNode` sınıfı.  
  
    ```csharp  
    private static ImageList imageList;  
  
    static SimpleProjectNode()  
    {  
        imageList =        Utilities.GetImageList(            typeof(SimpleProjectNode).Assembly.GetManifestResourceStream(                "SimpleProject.Resources.SimpleProjectNode.bmp"));  
    }  
    ```  
  
6.  Başlangıcına aşağıdaki özelliği ekleyin `SimpleProjectNode` sınıfı.  
  
    ```csharp  
    internal static int imageIndex;  
       public override int ImageIndex  
       {  
           get { return imageIndex; }  
       }  
    ```  
  
7.  Örnek oluşturucusu aşağıdaki kodla değiştirin.  
  
    ```csharp  
    public SimpleProjectNode(SimpleProjectPackage package)  
    {  
        this.package = package;  
  
        imageIndex = this.ImageHandler.ImageList.Images.Count;  
  
        foreach (Image img in imageList.Images)  
        {  
            this.ImageHandler.AddImage(img);  
        }  
    }  
    ```  
  
 Statik oluşturma sırasında `SimpleProjectNode` proje düğümü bit eşlem derleme bildirimi kaynakları alır ve daha sonra kullanmak için özel bir alan olarak önbelleğe alır. Söz dizimi fark <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> görüntü yolu. Bir derlemede gömülü bildirim kaynakların adlarını görmek için <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> yöntemi. Ne zaman bu yöntem uygulanan `SimpleProject` derlemenin sonuçları şu şekilde olmalıdır:  
  
-   *SimpleProject.Resources.resources*  
  
-   *VisualStudio.Project.resources*  
  
-   *SimpleProject.VSPackage.resources*  
  
-   *Resources.imagelis.bmp*  
  
-   *Microsoft.VisualStudio.Project.DontShowAgainDialog.resources*  
  
-   *Microsoft.VisualStudio.Project.SecurityWarningDialog.resources*  
  
-   *SimpleProject.Resources.SimpleProjectNode.bmp*  
  
 Örnek oluşturma sırasında `ProjectNode` temel sınıf yükleri *Resources.imagelis.bmp*, gelen 16 x 16 bit eşlemler, yaygın olarak eklenen kullanılan *Resources\imagelis.bmp*. Bu bit eşlem listesi için kullanılabilir hale getirileceğini `SimpleProjectNode` olarak `ImageHandler.ImageList`. `SimpleProjectNode` Proje düğümü bit eşlem listesine ekler. Görüntü listesinde proje düğümü bit eşlemin uzaklık değeri genel olarak daha sonra kullanmak için önbelleğe alınmış `ImageIndex` özelliği. Visual Studio, proje düğümü simgesi olarak görüntülenmesini hangi bit eşlem belirlemek için bu özelliği kullanır.  
  
## <a name="test-the-custom-project-node-icon"></a>Özel proje düğümü simgesini test etme  
 Özel proje düğümü simge olan bir proje hiyerarşisi oluşturur olup olmadığını görmek için proje fabrikanızı test edin.  
  
### <a name="to-test-the-custom-project-node-icon"></a>Özel proje düğümü simgesi test etmek için  
  
1.  Hata ayıklamayı başlatmak ve deneysel örneğinde yeni bir SimpleProject oluşturun.  
  
2.  Yeni oluşturulan projeyi dikkat *SimpleProjectNode.bmp* proje düğümü simge olarak kullanılır.  
  
     ![Yeni proje düğümünü Basit Proje](../extensibility/media/simpleprojnewprojectnode.png "SimpleProjNewProjectNode")  
  
3.  Açık *Program.cs* Kod düzenleyicisinde. Aşağıdaki koda benzer kaynak kodu görmeniz gerekir.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace $nameSpace$  
    {  
        public class $className$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
     Şablon parametreleri $nameSpace$ ve $className$ yeni değerlere sahip olmayan dikkat edin. Sonraki bölümde şablon parametre değiştirme uygulamak öğreneceksiniz.  
  
## <a name="substitute-template-parameters"></a>Şablon parametreleri değiştirin  
 Bir önceki bölümde, proje şablonu ile Visual Studio kullanarak kaydettiğiniz `ProvideProjectFactory` özniteliği. Bu şekilde bir şablon klasörü yolunu kaydetme geçersiz kılma ve genişletme temel şablon parametre değiştirme etkinleştirme sağlar `ProjectNode.AddFileFromTemplate` sınıfı. Daha fazla bilgi için [yeni proje oluşturma: altyapı öğeleri, bölüm iki](../extensibility/internals/new-project-generation-under-the-hood-part-two.md).  
  
 Artık yeni kod ekleyin `AddFileFromTemplate` sınıfı.  
  
### <a name="to-substitute-template-parameters"></a>Şablon parametreleri değiştirmek için  
  
1.  İçinde *SimpleProjectNode.cs* dosyasında, aşağıdaki ekleyin `using` deyimi.  
  
    ```csharp  
    using System.IO;  
    ```  
  
2.  Değiştirin `AddFileFromTemplate` aşağıdaki kodu kullanarak yöntemi.  
  
    ```csharp  
    public override void AddFileFromTemplate(  
        string source, string target)  
    {  
        string nameSpace =   
            this.FileTemplateProcessor.GetFileNamespace(target, this);  
        string className = Path.GetFileNameWithoutExtension(target);  
  
        this.FileTemplateProcessor.AddReplace("$nameSpace$", nameSpace);  
        this.FileTemplateProcessor.AddReplace("$className$", className);  
  
        this.FileTemplateProcessor.UntokenFile(source, target);  
        this.FileTemplateProcessor.Reset();  
    }  
    ```  
  
3.  Hemen sonra yöntemde bir kesme noktası ayarlamak `className` atama ifadesi.  
  
 Atama deyimleri, bir ad alanı ve yeni bir sınıf adı için uygun değerleri belirler. İki `ProjectNode.FileTemplateProcessor.AddReplace` yöntem çağrılarını, bu yeni değerleri kullanarak karşılık gelen şablon parametre değerlerini değiştirin.  
  
## <a name="test-the-template-parameter-substitution"></a>Şablon parametre değiştirme test  
 Artık şablon parametre değiştirme test edebilirsiniz.  
  
### <a name="to-test-the-template-parameter-substitution"></a>Şablon parametre değiştirme test etmek için  
  
1.  Hata ayıklamayı başlatmak ve deneysel örneğinde yeni bir SimpleProject oluşturun.  
  
2.  Yürütmeyi durdurur kesme noktasında `AddFileFromTemplate` yöntemi.  
  
3.  Değerleri inceleyin `nameSpace` ve `className` parametreleri.  
  
    -   `nameSpace` değerini verilen \<RootNamespace > öğesinde *\Templates\Projects\SimpleProject\SimpleProject.myproj* projesi şablon dosyası. Bu durumda, değerdir `MyRootNamespace`.  
  
    -   `className` sınıf kaynak dosya adı, dosya adı uzantısı olmadan değeri verilir. Bu durumda, hedef klasöre kopyalanacak ilk dosyasıdır *AssemblyInfo.cs*; bu nedenle, className değeri `AssemblyInfo`.  
  
4.  Kesme noktası kaldırıp tuşuna **F5** yürütme devam etmek için.  
  
     Visual Studio, proje oluşturma tamamlanmalıdır.  
  
5.  Açık *Program.cs* Kod düzenleyicisinde. Aşağıdaki koda benzer kaynak kodu görmeniz gerekir.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace MyRootNamespace  
    {  
        public class Program  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
     Ad alanı artık olduğuna dikkat edin `MyRootNamespace` ve sınıf adları artık `Program`.  
  
6.  Projede hata ayıklamaya başlayın. Yeni Proje derlemek, çalıştırın ve "Hello VSX!!!" görüntüle Konsol penceresinde.  
  
     ![Basit bir proje komutu](../extensibility/media/simpleprojcommand.png "SimpleProjCommand")  
  
 Tebrikler! Yönetilen temel proje sistemi uyguladınız.